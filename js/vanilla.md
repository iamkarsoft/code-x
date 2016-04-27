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
var friends = ["nana", "king", "noiro"];

for(var i=0; i<friends.length ;i++){
      console.log(friends[i]);
};

// Foreach with array

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


