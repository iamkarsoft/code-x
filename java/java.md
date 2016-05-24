### Data Types

#### Strings
 printing out Ramos

```
	System.out.println("Ramos");

```

#### Numbers

```
		System.out.println(1);

```

##### example in bluej

```
public class HelloPrinter
{
    public static void main(String[] args)
    {
    System.out.println("Hello, World!");
    }
    
}

```
#### explaining the whole line

- System.out is an object 
- .println is the method


#### Difference between print & println

- print prints result but without goint to the next line
- println on the other hand prints result on a new line everytime it runs 

```
//print 
System.out.print(1)

//println
System.out.println(1)

```

#### Errors

- compile-time error or system error 
- run-time error or logic error 


### Datatypes
- boolean true or false
- int 23
- char 'A'


### Booleans True or False

```
public class DataTypesB {
	public static void main(String[] args) {

		System.out.println(true);

	}
}

```


### Variables


 In java all variables must start with a specified data type

 ```
public class Variables {
	public static void main(String[] args) {

		int myNumber=42;
		boolean isFun=true; 
		char movieRating='A'; 

	}
}

```

### Arythmetics in java 

```
int sum = 34 + 113;
int difference = 91 - 205;
int product = 2 * 8; 
int quotient = 45 / 3;

```

### RElational operators

- < : less than.
- <=: less than or equal to.
- >: greater than.
- >=: greater than or equal to.


```
public class RelationalOperators {
	public static void main(String[] args) {

		System.out.println(6>3);

	}
}

```

### Equality operators
- == : equal to 
- != : not equal to 

```
public class Generalizations {
	public static void main(String[] args) {

//first comment
		boolean isComplete=true;
		int awesomeLevel=121;
    int epicLevel=awesomeLevel;	
		System.out.println(epicLevel);
		

	}
}

```