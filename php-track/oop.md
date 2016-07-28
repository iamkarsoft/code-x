### OOP

#####Vocabulary of OOP
What sometimes puts people off from working with objects is the tendency to use
big words to refer to perfectly ordinary concepts. So to avoid deterring you, we’ll begin with a short vocabulary list:

- class the recipe or blueprint for creating an object
- object a thing instantiate the action of creating an object from a class
- method a function that belongs to an object
- property a variable that belongs to an object

###### Defining a class 

```
class Recipe
{

}


//instantiating the class

$recipe1= new Recipe();


```

##### Functions

- is_float()
- is_int()
- in_array() //checking inside an array  ` !in_array($measure, $this->measurements) `
- empty()

##### Access modifiers

allows to control access to classes 

- public
- private
- protected

##### creating a property

properties are like variables

```
class Recipe
{
//properties
  public $title;
  public $ingredients=array();
  public $instructions=array();
  public $yield;
  public $tag=array();
  public $source="Alena Holligan";

}


$recipe1= new Recipe();

//instantiating the object 
echo $recipe->source;

//setting the property
$recipe1->source="Grandma Holligan";
echo $recipe->source;


$recipe2 = new Recipe();
$recipe2->source="Betty Crocker";
echo $recipe1->source;
echo $recipe2->source;

```

##### Adding methods

Methods are like functions for classes


```
class Recipe
{

//properties
  public $title;
  public $ingredients=array();
  public $instructions=array();
  public $yield;
  public $tag=array();
  public $source="Alena Holligan";

  //methods 

  public function displayRecipe()
  {
  return	$this->title. "by ". $this->source;

  }

}

$recipe1= new Recipe();

//instantiating the object 
echo $recipe->source;

//setting the property
$recipe1->source="Grandma Holligan";
$recipe1->title="Up";


$recipe2 = new Recipe();
$recipe2->source="Betty Crocker";
$recipe2->title="you know right";

//calling the method 

echo $recipe1->displayRecipe();

```

##### Access Modifiers for accessing classes

allows to control access to classes 

- getters
- setters

```
class Recipe
{

//properties
  private $title;
  public $ingredients=array();
  public $instructions=array();
  public $yield;
  public $tag=array();
  public $source="Alena Holligan";


  public function setTitle($title){
  	$this->title=ucwords($title);
  }  

  public function getTitle($title){
  	return $this->title;
  	}

  //methods 

  public function displayRecipe()
  {
  return	$this->title. "by ". $this->source;

  }

}

$recipe1= new Recipe();

//instantiating the object 
echo $recipe->source;

//setting the property
$recipe1->source="Grandma Holligan";
$recipe1->setTitle("up");


$recipe2 = new Recipe();
$recipe2->source="Betty Crocker";
$recipe2->title="you know right";

//calling the method 

echo $recipe1->displayRecipe();
echo $recipe2->getTitle();

```

###### Associative arrays 

```
public function addIngredient($item,$amou=null, $measure= null)
{
	$this->ingredients[]=array(
		"item"=> $item,
		"amount"=>$amount,
		"measure"=>$measure;
	)
}

```


##### Static Methods 


```
class render

{
		public static function displayRecipe($recipe)

		{

		return $recipe->getTitle() ."by". $recipe->getSource();
		}
}



echo Render::displayRecipe($recipe1);

```


##### Magic Methods 

they are methods that are triggered 

```

//adding magic method __CONSTRUCT

public function __construct($title==null){
	$this->setTitle($title);

}

// converting object to string 

public function __toString(){
	
	return $this ->getTitle();
}