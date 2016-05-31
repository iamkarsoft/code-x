### PDO (php data object);

An object is made of methods and properties
method are like functions and properties are like variables.

```
$mail = new PHPMailer();
$mail->from = "from@example.com";
$mail->to = "to@example.com";
$mail->message = "This is the email body";
$mail->send();
```


##### Connecting to database using PDO

```
<?php 
//sqlite
$db = new PDO("Sqlite:".__DIR__."/database.db");

// mysql
$db = new PDO("mysql:host=localhost;dbname=DATABASE_NAME;port=3306","USERNAME","PASSWORD");
```

##### Handling Exceptions

What happens when the system is unable to connect to the database? Whenever your code relies on an external system, there's always the chance that something could go wrong. These are known as exceptions and any code connecting to an external system needs to handle them.

```
try{
$db = new PDO("Sqlite:".__DIR__."/database.db");
$db->setAtrribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
}catch(Exception $e) {
	echo "Unable to connect";
	//echoing the exception message 

	echo $e->getMessage();
	exit;

}

echo "connection successful";

```

##### Querying db 

```
try{
	$resutls = $db->query("select * from movies");
	echo "Retrieved Results"
	
}catch(Exception $e){
	echo"failed";
	exit;
}
```

##### PDO statements

- fetchAll();

Returns an array containing all of the result set rows

```
$results->fetchAll(PDO::FETCH_ASSOC);
```
```
foreach($results as $result){
 $member_id = $result['member_id']; 
 $email = $result['email'];
  $fullname = $result['fullname']; 
  $level = $result['level']; 
  send_offer($member_id, $email, $fullname, $level);
   }

```


##### Improving with refactoring

```
function full_catalog_array($limit = null, $offset = 0) {
    include("connection.php");

    try {
        $results = $db->query("SELECT title, category,img FROM Media”);
    } catch (Exception $e) {
        echo "Unable to retrieved results";
        exit;
    }

    $catalog = $results->fetchAll(PDO::FETCH_ASSOC);
    return $catalog;

```

##### Querying multiple tables with join

```
try {
    $results = $db->query(
          "SELECT title, category, img, format, year, 
          publisher, isbn, genre
          FROM Media
          JOIN Genres ON Media.genre_id=Genres.genre_id
          LEFT OUTER JOIN Books 
          ON Media.media_id = Books.media_id
          WHERE Media.media_id = ?"
    );
} catch (Exception $e) {
    echo "bad query";
    echo $e;
}

$item = $results->fetch(PDO::FETCH_ASSOC);
```

##### Prepare method

```
try {
    $results = $db->prepare(
          "SELECT title, category, img, format, year, 
          publisher, isbn, genre
          FROM Media
          JOIN Genres ON Media.genre_id=Genres.genre_id
          LEFT OUTER JOIN Books 
          ON Media.media_id = Books.media_id
          WHERE Media.media_id = ?"
    );

    $results->bindParam(1,$id,PDO::PARAM_INT);
    $results->execute();
} catch (Exception $e) {
    echo "bad query";
    echo $e;
}
```


##### getting specific with query 

- Random() or Rand()

```
function random_catalog_array() {
    include("connection.php");

    try {
       $results = $db->query(
         "SELECT media_id, title, category,img 
         FROM Media
         ORDER BY RANDOM()
         LIMIT 4"
       );
    } catch (Exception $e) {
       echo "Unable to retrieved results";
       exit;
    }

    $catalog = $results->fetchAll();
    return $catalog;
```

##### Filtering data by category 


```
function category_catalog_array($category) {
    include("connection.php");
    $category = strtolower($category);
    try {
       $results = $db->prepare(
         "SELECT media_id, title, category,img 
         FROM Media
         WHERE LOWER(category) = ?
         ORDER BY 
         REPLACE(
           REPLACE(
              REPLACE(title,'The ',''),
              'An ',
              ''
           ),
           'A ',
           ''
         )"
       );
       $results->bindParam(1,$category,PDO::PARAM_STR);
       $results->execute();
    } catch (Exception $e) {
       echo "Unable to retrieved results";
       exit;
    }

    $catalog = $results->fetchAll();
    return $catalog;
}
```

##### setting up pagination variables 

- catalog 

```
$items_per_page = 8;

if (isset($_GET["pg"])) {
  $current_page = filter_input(INPUT_GET,"pg",FILTER_SANITIZE_NUMBER_INT);
}
if (empty($current_page)) {
  $current_page = 1;
}

$total_items = get_catalog_count($section);
```

- function 

```
function get_catalog_count($category = null) {
    $category = strtolower($category);
    include("connection.php");

    try {
        $sql = "SELECT COUNT(media_id) FROM Media";
        if (!empty($category)) {
          $result = $db->prepare(
            $sql
            . " WHERE LOWER(category) = ?"
          );
          $result->bindParam(1,$category,PDO::PARAM_STR);
        } else {
          $result = $db->prepare($sql);
        }
        $result->execute();
    } catch (Exception $e) {
      echo "bad query";
    }

  $count = $result->fetchColumn(0);// used to fetch column per column 
  return $count;
}
```

- calculations

```
$total_pages = ceil($total_items / $items_per_page);

//limit results in redirect
$limit_results = "";
if (!empty($section)) {
    $limit_results = "cat=" . $section . "&";
}

// redirect too-large page numbers to the last page
if ($current_page > $total_pages) {
    header("location:catalog.php?" 
        . $limit_results 
        . "pg=".$total_pages);
}
// redirect too-small page numbers to the first page
if ($current_page < 1) {
    header("location:catalog.php?"
        . $limit_results
        . "pg=1");
}

//determine the offset (number of items to skip) for the current page
//for example: on page 3 with 8 item per page, the offset would be 16
$offset = ($current_page - 1) * $items_per_page;
```

- limits 

```
function category_catalog_array($category, $limit = null, $offset = 0) {
    include("connection.php");
    $category = strtolower($category);
    try {
       $sql = "SELECT media_id, title, category,img 
         FROM Media
         WHERE LOWER(category) = ?
         ORDER BY 
         REPLACE(
           REPLACE(
              REPLACE(title,'The ',''),
              'An ',
              ''
           ),
           'A ',
           ''
         )";
       if (is_integer($limit)) {
          $results = $db->prepare($sql . " LIMIT ? OFFSET ?");
         $results->bindParam(1,$category,PDO::PARAM_STR);
          $results->bindParam(2,$limit,PDO::PARAM_INT);
          $results->bindParam(3,$offset,PDO::PARAM_INT);
       } else {
         $results = $db->prepare($sql);
         $results->bindParam(1,$category,PDO::PARAM_STR);
       }
       $results->execute();
    } catch (Exception $e) {
       echo "Unable to retrieved results";
       exit;
    }

    $catalog = $results->fetchAll();
    return $catalog;
}

```

##### PDO Filters 

- PDO::PARAM_STR for strings
- PDO::PARAM_INT for integers 


##### Fetching with PDO 

- $result->fetchAll()
- $result->fetch()
- PDO::FETCH_ASSOC
- PDO::FETCH_NUM


##### Search form 

- create a search form 
- get user input and paginate
- match search patterns
-  use bind value for searching using user data 

```
$result->bindValue(1,'%'.$search.'%',PDO::PARAM_STR);

```




