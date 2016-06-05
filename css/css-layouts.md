###### Css resets and normalize 

- normalize.css to remove browser default css  ` npm install normalize` or ` bower install normalize `

##### Centering layout wrapper 

```
#wrapper{
	width:70%;
	margin:0 auto;
}
```

##### Vertical margin : collapsing margin 


```
h1{
	margin-top:0;
}
//or 

.div{
	padding: 1em 0;
}

```

##### FUll-width header layout 

```
body{
	width:100%;
}
```

##### Mobile first approach

```
@media (min-width: 769px){
	
	.container{
		width:100%;
		max-width:1000px;

	}
}
```

##### Creating a sticky footer 

```

.wrapper {
	min-height:calc(100vh - 89px); //viewport height
}
footer{
	
}

```


##### Positioning 


- absolute positioning


they are neither affected or do not affect any element of the page. this positions relative to browser viewport if the parent doesn't have a relative positioning 

```
li{
	position:absolute
	top:0;
	left:0;
	right:10px;
	bottom:30px;
}
```

- relative  positioning

allows to position relative to a parent 
element 

```
.main-header{
	position:relative;
}
``` 

- fixed 

allows to position relative to browser and stay fixed no matter the width of the browser 

```
li{
	position:fixed;
}

```


##### z-index 

elements with higher z-index show on top with elements with a lower one.




- 