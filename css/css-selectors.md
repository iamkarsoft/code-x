##### attribute selectors

```
//styling class attributes
[class]{
	color:red;
}

[class="form-control"]{
	color:red;
	padding:20px 24px;
}


form[class="form-control"]{
	color:red;
	padding:20px 24px;
}


div[id="container"]{
	color:red;
	padding:20px 24px;
}

input[type="text"]{
	background:fgfee6;
	color:f4f7f8;
}


```

###### Beyond DRY CSS 

this a concept to create classes that we will often use to style elements

```
<!-- dry css i.e -->
<!-- border radius -->
.br{
	border-radius: .5em;
}

<!-- button style -->
.btn{
	cursor:pointer;
	font-size: .875em;
	font-weight:400;
	color:#fff;
	padding-left:20px;
	padding-right:20px;
	text-transform:uppercase;
}

.btn:hover{
	opacity:.75;z
}

.inln{
	width:auto;
	display:inline-block;
}
```

##### Combinators

- (>) child combinator ( child selectors)

 this style directly nested from the parent

```
 form > a{
 font-size: .7em;
 }
```

- (+) adjacent siblings selectors 

targets and styles immediate siblings element 


```

 .btn + .btn {

 margin-left: 20px;
 }
```


 - (~) general sibling selector 


 targets every sibling element 


 ```
 h1 ~ label{
background:tomato;

 }

 ```

###### form & links attributes 


```
input [type="button"],
input [type="reset"],
input [type="submit"]{
	cursor:pointer;
}

a[target="_blanck"]{
	color:red;
}
```

##### Pseudo Classes 

- First and last child elements


```

<!-- first child -->
li:first-child{
	background:#52bab3;
}

<!-- last  child -->
li:last-child{
	background:#52bab3;
}
```

- Only child and empty elements 

```
<!-- only child -->
span:only-child{
	background:#52bab3;
}

<!-- empty -->
li:empty{
	background:#52bab3;
}
```

##### Substring matching attribute selectors 

- (^) begins with attribute  selector

```
a[href^="http://"]{
	font-size:300px;
}


```

- ($) ends with attribute selector 

```
a[href$=".pdf"]{
	font-size:300px;
	background-repeat:no-repeat;
	background-size:18px 18px;
}

```

- (*) contains attribute selector 

```
a[href*="downloads"]{
	text-decoration:none;
}
```

##### Element stats pseudo classes 

```
input:focus,textarea:focus{
	border-color:#52bab3;
}

:disabled{
	background:#ddd;
}

input[type="checkbox"]:checked+label{
	
	font-weight:bold;
}
```

###### nth-of-type


targets an element based on it's position inside a parent 

- nth-child()


```
div:nth-child(4){
	background:blue;
}

<!-- even goes from 2,4,6,8 -->
div:nth-child(even){
	background:blue;
}

<!-- odd goes from 1,3,5,7 -->
div:nth-child(odd){
	background:blue;
}

<!-- using expressions uses formul an+b or an ,n or -an+b;

where a is cycle and b starting point -->
div:nth-child(2n+3){
	background:blue;
}

div:nth-child(-2n+3){
	background:blue;
}
```

- nth-of-type()

```
div:nth-of-type(4){
	background:blue;
}
```


- nth-of-type(even)

```
div:nth-of-type(even){
	background:blue;
}
```


- nth-last-of-type(even)

selects from the bottom 


```
div:nth-last-of-type(3){
	background:blue;
}
```

##### Pseudo elements 

- :first-line


```
.intro::first-line{
	font-size:1.4em;
}
```

- :first-letter


```
.intro::first-letter{
	font-size:1.4em;
}
```

- ::before 

```
.intro::before{
content:url(../img/isc.png);
	font-size:1.4em;
}
```


- ::after 

```
.intro::after{
content:"i know";
	font-size:1.4em;
}
```

- attr()

```
.intro::after{
content:attr(title);
	font-size:1.4em;
}
```

##### negation pseudo class 

selects everything that does not have the id of column a 

```
div:not(#col-a){
	border-color:red;
}

input:not([type="submit"]){
	box-shadow: inset 0 2px 0 rgba(0,0,0, .15);
}
```

##### ::root and :target 


- ::root 

```
:root{
	background:#52bab3;
}
```

- :target

```
:target{
background:#384047;	
}

#col-c:target{
background:#eff1f2;	
}
```