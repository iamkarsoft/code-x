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