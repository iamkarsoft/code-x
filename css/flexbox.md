##### Flex containers

- sets the context for flexbox layout

- contains flex items, the actual elements you layout using flexbox 

- any block-level or inline element (div, ul, )

##### Flex items

- every direct child of flex container 

- unlimeited amount of items in flex container 


##### Flex Axes 

- Main Axis 

 Primary axis and defines the direction which is from left to right 

- Cross axis 
perpendicular and is from top to bottom

##### Defining the flex container 

```
.container{
	display:flex; <!--inits flex (flex,inline-flex) -->
	height:300px;
}
```

##### flexbox properties

- changing direction of flex direction 

p.s this applies to only flex containers


```
.container{
	display:flex; <!--inits flex (flex,inline-flex) -->
	height:300px;
	flex-direction:row-reverse <!--direction flex (row,row-reverse,column ,column-reverse) -->
}

```

##### Wrapping flex items 

dealing with overflow and responsiveness

p.s: applies to flex container only


```
.container{
	display:flex; <!--inits flex (flex,inline-flex) -->
flex-wrap:wrap;<!--gives it a multiline  -->
}

```

##### align flex items to cross axis 

p.s: workes with flex container 
```
.container{
	display:flex; <!--inits flex (flex,inline-flex) -->
flex-wrap:wrap;<!--gives it a multiline  -->
height:450px;
align-items:stretch;<!--stretch(fills);
flex-start(start from top), flex-end(starts from top);center(centers perfectly) -->


}

```

- self align 

```
.item-1{
	align-self:flex-start;<!--stretch(fills);
flex-start(start from top), flex-end(starts from top);center(centers perfectly) -->
}
```

##### Horizontal and Vertical 

```
.container{
	display:flex;
	min-height:50vh;
	justify-content:center;<!-- space-between -->
	align-items:center;
}

```

##### creating  columns 


- 2 colums 


```
.row{
	display:flex;
}

.col{
	flex:1;<!-- flex:1 makes it equal  -->
}
.primary{
	flex:2
}

.secondary{
	
}
```

- 3 columns 


```
.row{
	display:flex;
	flex-wrap:wrap;
}

.col{
	flex:1 50%;<!-- flex:1 makes it equal  -->
	flex-basis:0;<!-- makes columns not breat into new line  -->

}
.primary{
	flex:2;
	flex-grow:1.4 <!-- gets more space than others -->
}

.secondary{
	order:-1<!-- places the secondary first in column -->
}

.tertiary{
	
}

.button{
	margin-top:auto;
	align-self:flex-start;
}
```

##### Sticky footer 

```
body{
	display:flex;
	flex-direction:column;
	min-height:100vh;
}
.footer{
	display:flex;
	flex:1;
}

```