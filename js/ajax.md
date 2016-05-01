#Lesson 1 : Basic Ajax

### 1 Create an XMLHTTP Request Object

```
	
//Tells browser to get ready for ajax
var xhr= new XMLHttpRequest();

```

### 2 Create a callback function

this is the function you want the server to run

 - onreadystatechange event

 ```
xhr.onreadystatechange = function(){
	//checking if server is done which readystate===4
	if(xhr.readyState===4){

		//response text is 
		document.getElementByClass("ajax").innerHTML =
		xhr.responseText
	}
};
```


### 3 Open a Request
 uses this to open a request
  - you use the http request type
  - and the 2nd is 

```
//OPENING  a request
xhr.open('GET','sidebar.html');
```

### 4 sending the request
```
//sending a request
xhr.send();

or using a function

function sendAjax(){
	xhr.send();
document.getElementById('load').style.display="none";
}
```


#### ready state

 -0  to 3 is before
 - 4 is receiving data from server

 #### status property

 - 200  = means ok
 - 404 = not found
 - 401 = not authorized
 - 500 = server error


# Lesson 2 : Introduction To Json
Javascript object notation

```
[
	{
	"name": "Ramos",
	"inoffice":false
	},
	{
	"name": "Noiro",
	"inoffice":true
	},

	{
	"name": "King",
	"inoffice":false
	},

	{
	"name": "Lyn",
	"inoffice":true
	},

]


```
- typeof use to know the type of data 
```
(typeof xhr.responseText);

```

- JSON.Parse takes strings and turns it into object 

```
var checkin= JSON.parse(xhr.responseText);
```

### Exercise using ajax and json

 - html 

 ```
 <!DOCTYPE html>
<html>
<head>
	<title>Ajax test</title>
	<style type="text/css">
	body{
		background: #fafafa;margin: 5% auto;
	}

	.bigger, .sidebar{
		background:#fafafa;
		border: 1px solid black;
		float: left;
	}

	.bigger{
		width: 700px;
		height: 500px;
		margin-left: 10%;
		padding:3%;
	}
	
	.sidebar{
		margin-left: 20px;
		width: 300px;
		height: 300px
	}
	

	.bulleted{
		list-style: none;

	}
	.bulleted li{
		margin: 14px;
	}

  .bulleted span{
  	width: 40px; 
  	height: 40px; 
  }

	.in span{
		background: green;
		color: #fafafa;
		padding:3px; 
			width: 40px; 
  	height: 40px; 

	}

		.out span{
		background: red;
		color: #fafafa;
		padding:3px; 
	width: 40px; 
  	height: 40px; 
	}
	</style>

<script type="text/javascript" src="widget.js"></script>

</head>
<body>

<div id="container">

	<div class="bigger">
		
		
			<div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non modi, exercitationem inventore voluptate explicabo praesentium, minus, nihil iste consectetur soluta, ducimus distinctio nam!

			</div>

			<div>Debitis eum autem voluptatem dolorum est culpa odio, voluptas illum aut beatae amet repellat quis ipsam, saepe, magnam eius, quod doloremque eligendi natus!</div>

			<div>Maiores molestias voluptate sunt eius illo doloribus hic voluptates officia labore nemo atque reprehenderit est omnis, corporis ab, voluptatum error quos aut nesciunt.</div>

			<div>Adipisci, laudantium, voluptatum. Alias provident incidunt, reiciendis reprehenderit libero unde asperiores. Unde obcaecati vitae non quos possimus consectetur tenetur, in animi praesentium natus!</div>
		
	</div>



	<div class="sidebar">
		

	</div>

</div>
</body>
</html>
```

- widget js 


```
<script>

var xhr = new  XMLHttpRequest();

xhr.onreadystatechange = function(){

	if(xhr.readyState===4){
// creating a variable for the json data
var checkin = JSON.parse(xhr.responseText);

var statusHTML='<ul class="bulleted">';
	for(var i=0; i<checkin.length;i+=1){
		if(checkin[i].inoffice===true){
			statusHTML+='<li class="in"> <span> In </span>  ';
		}else {
			statusHTML+='<li class="out"> <span> Out </span>  ';
		}
		statusHTML+= checkin[i].name;
		statusHTML+='</li>';
	}
	statusHTML+='</ul>';

	document.querySelector('.sidebar').innerHTML=statusHTML;


	}
};

xhr.open("GET",'checkin.js');

// send request
 xhr.send();

 </script>
 ```

 - checkin.js  for json data 

 ```
 <script>
[
	{
	"name": "Ramos",
	"inoffice":false
	},
	{
	"name": "Noiro",
	"inoffice":true
	},
	
	{
	"name": "King",
	"inoffice":false
	},

	{
	"name": "Lyn",
	"inoffice":true
	}

]


 </script>
 ```

