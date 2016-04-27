### Data types

1. Numbers
2. Strings
3. Booleans
4. Nulls
5. Undefined

### Useful Javascript Built-in Methods
  - Alert : alerting something to the user
   ```
 alert('Hello');
   ```

   - Showing something in the js console
   ```
   console.log('Hi');
   ```

   - getting data from user

   ```
   prompt(' WHat is your name?');
   ```

 ### The Boolean Logic
 ```
 > Greater Than
>= Greater than or equal
< less than
<= Less than or equal
== Equal
!= Not equal 
=== Equal value or type
!== Not equal value
```

### Logic Operators & Conditionals

	- logic operators
```
&& And
|| Or
! Not
```
	- Conditionals

```
If
 
Else IF

Else

```
 ### WHile loops in Js 

 - syntax
 ```
 while(condition){
   code to run
};
```

- example of while loops
```
// printing numbers from -10 to 19
var counter = -10

while(counter<19){
	console.log(counter);
	counter++;
}

//printing pair numbers between 10 and 50
console.log("printing pair numbers between 10 and 40");
var counter= 10;

while(counter<=40){
	console.log(counter);
	counter+=2;
}
//printing odd numbers from 300 to 333
console.log("printing odd numbers from 300 to 333");
var counter =300;
	while(counter <= 333){
			if(counter % 2 !==0){
			console.log(counter);
		}
		counter+=1;
	}


//printing odd numbers from 300 to 333
console.log("printing  numbers divisible by 5 and 3 between 5 to 50");
var counter =5;
	while(counter <= 50){
			if(counter % 5 === 0 && counter % 3 === 0){
			console.log(counter);
		}
		counter+=1;
	}
```

### For loops

- syntax

```
for(init; condition; step){
  code to run

}
```
- Example 
```
//printing all numbers between -10 and 19
console.log("printing all numbers between -10 and 19");

for(i = -10; i<19 ;i++){
	console.log(i);
}

//printing pair numbers between 10 and 50

console.log("printing all even numbers between 10 and 40");

for(i= 10; i <=40 ; i+=2){
	console.log(i);
}

//printing odd numbers from 300 to 333

console.log("printing odd numbers from 300 to 333");

for(i=300; i<=333; i++){
	if(i % 2 !== 0){
		console.log(i);
			}
}

//printing  numbers divisible by 5 and 3 between 5 to 50
console.log("printing  numbers divisible by 5 and 3 between 5 to 50");

for(i =5; i<=50; i++ ){

	if(i % 5 === 0 && i %3 === 0){
		console.log(i);
	}
}
```

### Functions

 - syntax
 ```
 function doSomething(){
console.log("hello world");
}

// calling the function
doSomething();

 ```

 - 2 types of functions
  -- Function Declarations
   ```
   function doSomething(){
console.log("hello world");
}
```

-- function expressions

```
var dosomething=function doSomething(){
console.log("hello world");
}
```

- example
```
function square(num){
console.log(num * num);
}
 square(10); //prints 100

```

### Console.log vrs Return

Console.log and Return are 2 different things. Console.log prints out the result of a function or a set of code which is only accessible in the javascript console, meanwhile Return actually returns the result of the code and is available in the program

 - Console.log
 ```
 var first_name = prompt("what is your first name?");
var last_name =prompt("what is your last name?");
var age= prompt("How old are you?");

console.log("Your full name is "+ first_name +" "+ last_name);
console.log("You are "+age+" years old");
```

- Return
```
function factorial(num){

	var result=1;
	for (var i=2; i<=num; i++){
		result *= i;
	}

	return result;
}
```

Ps:What you have to remember is that return only returns one result at a time, and will only return the first result and every time a function is returned, it stops the latter part of the code from executing.


### Replacing String in Js
 - Using replace() to replace strings
 ```
 function kebab(str){


	var newStr = str.replace(/-/g , "_"); //replaces - with _
 
	return newStr;
}

//calling it

kebab("hello-here"); //prints "hello_here"
```

### Arrays
I call them the big brother of variables, they let us group data into one single variable

- Example of an array

```
var friends= ["nana", "king", "noiro"];
Adding to array

friends[3]="ramos";
```
-- chaning a value in array

```
friends[1]="king faisal";
```

-- New or Empty array

```
var friends=[]; // popular
or
var friends= new array();
```

#### Array Methods
- Push vrs Pop

-- Push

The push method is used to add a value to an array.
it’s similar to friends[3]=”ramos”; which requires us knowing how many values we have in the array. Push gives us flexibility by just adding our value to the array as the last value.

```
friends.push("junior");
```
- Pop

Pop is the opposite of push, what it does is to delete the last value in the array, it also doesn’t require any parameters.

```
friends.pop();
```

#### Shift vrs Unshift

 - Unshift

Unshift adds a value in the first position in an array

```
friends.unshift["junior"];
```
 - shift

shift perform the same thing as pop but removes the first value.

```
friends.shift();
```

- index of

Used to find an item in an array

```
    friends.indexof("king");
```

- Slice

It is used to return parts of an array, it accepts to parameters the starting value and where the array will stop

```
var friends= ["nana", "king", "noiro"];

   var friends.slice(1,2);
```

- Array Iteration

Using for loop array.

```
var friends= ["nana", "king", "noiro"];


for(var i=0;i < friends.length;i++){
      console.log(friends[i]);
}


```

- Foreach with array

```

var friends = ["nana", "king", "noiro"];

friends.forEach(function(friends)){
             console.log(friends);
}

//splice is a function used to break down the array it takes 2 parameters, 
//the start point and how many values it should break by
friends.splice(friends,1)

An example of a javascript todo list

var Todo = ["buy car"];

var input = prompt("What would you like to do");




while(input!=="quit"){
if(input==="list"){
	
listTodos();
}else if(input ==="new"){
	
addTodo();
}else if(input==="delete"){
 deleteTodo();
}

//ask again for new input 
 input = prompt("What would you like to do");



}
console.log("ok, you quit");

function addTodo(){
	var newTodo = prompt("Enter new todo");
	Todo.push(newTodo);
	console.log("Added Todo");
}

function listTodos(){
	console.log("**********");
	Todo.forEach(function(todo, i){
	console.log(i+" : "+todo);

	});

	console.log("**********");

}

function deleteTodo(){
	var index=prompt("what is the index to delete");

 Todo.splice(index, 1);
 console.log("Deleted Todo");

}

```

### Objects
Unlike arrays that index it’s content, method sort of allows a free flow of data.

i.e Array

```
var person= ["kofi",13,"accra"];

//compared to object
var person={
  name:"kofi",
  age:13,
  city:"accra"
}
```
Example of creating an object and calling that object
```
Creating the object dog

var dog={
  name:"Bubba",
  bread:"Lab",
  age:3
}
```
- calling the object
```
//calling the object
dog["name"]; //prints Bubba which is the dog's name


//or we could do it the second and easy way
dog.name; //prints Bubba which is the dog's name
```

- Updating the object content

if we wanted to update the dog’s age we can do it in 2 different ways

```
//updating the dog
dog["age"]=6 ; //updates the dogs age from 3 to 6

//and the second way
dog.age=6; // also prints 
```
 - Example of object challenge

This is an exercise focused on arrays and objects, where we have arrays withing arrays and object within an array. This is possible because we nest arrays within array, objects within an object.

```
//example on movie database
var movies= [
{
	title:"In Bruges",
	rating:5,
	hasWatched:"watched"
},
{
	title:"Frozen",
	rating:4.5,
	hasWatched:"not seen"
},
{
	title:"Mad Max Fury Roads",
	rating:5,
	hasWatched:"seen"
},

{
	title:"Les Miserables",
	rating:3.5,
	hasWatched:" not seen"
}


	]    ;


	
		movies.forEach(function(movies){
		console.log("You have "+movies.hasWatched +" " + movies.title +" - " + movies.rating +" stars");
	});
```

### Methods
Methods are functions within objects

- calling a method in an object

```
person.total();
//examples
//methods into objecs
var person={ 
name: "Ramos",
math:5,
english:10,
total: function(x,y){
return x+y;

}
}

//calling the method 
person.total(person.math,person.english)
```
### DOM 
Every website has a DOM, I refer to it as the structure. We can use javascript to do tons of things thanks to the DOM. We can manipulate tags and do various stuff with it

- Select and Manipulate

Selecting and manipulating tags with js
```
var h1 = document.querySelector("h1");
h1.style.color="pink";
DOM selectors

document.getElementByID() // selects elemnt with an id
document.getElementByClassName()// selects element with class name
document.getElementByTagName() // selects tags
document.querySelector() // similar to css type of selection p.s: only returns the first result
document.querySelectorAll() // similar to the previous but returns all the matching one
var h1 = document.getElementByID("first");
h1= document.getElementByClass(".special");

document.querySelector(".special");
document.querySelectorAll("#first");
document.querySelector("h1 + p");
```
- Manipulating style with javascript

Using js to style a page
	```	
//we could add styles and remove styles existing in a stylesheet
tag.classList.add("navbar");
//removing style
tag.classList.remove("navbar");

//or we could just toggle
tag.classList.togglle("navbar");
```
- Manipulating Attributes

we can manipulate any attribute in the dom using getAttribute() and setAttribute()

we are going to manipulate the source of links on a page.
```	
Facebook
var link= document.querySelector("a"); // selects the first link
link.getAttribute("href"); // this gets the link address

link.setAtttribute("href","http://google.com");
```


### DOM events
Dom events are used to make cool stuff such as trigger things on click

Syntax

to do this we will have to choose an element and add the event listener to it
```
element.addEventListener("type",functiontocall(){})
```

-- I.e 1
```
//js script
var button = document.querySelector("button");
var isBlue=false;

button.addEventListener("click", function(){
if(isBlue){
	document.body.style.background="blue";
	document.body.style.color="white";
	isBlue=false;
}else{
	document.body.style.background="white";
	document.body.style.color="blue";
	isBlue=true;

	}
});
```

-- I.e 2

```
//javascript 


var p1= document.querySelector("#p1");

var p2= document.getElementById("p2");

var reset=document.getElementById("reset");

var p1display=document.querySelector("#p1score");

var p2display=document.querySelector("#p2score");

var resetButton= document.querySelector("#reset");

var input= document.querySelector("input");

var p=document.querySelector("p");

var winningSpan=document.querySelector("p span");

var p1score= 0;

var p2score= 0;

var gameover=false;

var winning=5;


p1.addEventListener("click", function(){

 if(!gameover){

	p1score++;

	if(p1score===winning){

	console.log("Player 1 won");

p1display.classList.add("green");

	gameover=true;}

	p1display.textContent = p1score;}

});


p2.addEventListener("click", function(){

 if(!gameover){

	p2score++;

	if(p2score===winning){

	console.log("Player 2 won");

p2display.classList.add("green");

gameover=true;

}

	p2display.textContent = p2score;}

});


resetButton.addEventListener("click",function(){

		p1score=0;

	p2score=0;


	p1display.textContent=0;

	p2display.textContent=0;


	p1display.classList.remove("green");

	p2display.classList.remove("green");

	gameover=false;


});


input.addEventListener("change",function(){

 winningSpan.textContent= this.value;

 winning=Number(this.value);

	p1score=0;

	p2score=0;


	p1display.textContent=0;

	p2display.textContent=0;


	p1display.classList.remove("green");

	p2display.classList.remove("green");

	gameover=false;

})

```