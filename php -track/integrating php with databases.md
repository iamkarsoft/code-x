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