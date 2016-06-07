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

##### Element stats pseudo classes 

```
input:focus,textarea:focus{
	border-color:#52bab3;
}

:disabled{
	background:#ddd;
}