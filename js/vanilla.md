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




