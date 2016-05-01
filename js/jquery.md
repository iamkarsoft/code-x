
Still on my programming journey which of course will never come to an end. There are always new technologies coming up, better ways to write code and easier or efficient ways to write code.


### jQuery

jQuery is a Javascript library, it allow’s us to simplify some code which will take long using vanilla Javascript. jQuery is Javascript but much simpler.

 - jQuery Selectors

Selecting element on the DOM using jQuery is much simpler and easier than using Vanilla Js

i.e: selecting a div using vanilla js
```
var div=getElementbyTagName("div");
compare to jQuery

$('div').dosomething()
i.e: applying css to the div special in the dom using jQuery

$('#special).css("color","yellow");
```
//i.e 2

```
$('#special')css({
     fontSize:"10px",
     border:"3px dashed purple'});
jQuery Methos

.text()
```
 - lets js print all text

it can also used to add text to DOm
i.e
```
.text("Beer")
.html()
```

- similar to .text() but can take html attributes.

i.e
```
.html("
New Song
“);

.Attr()
```
used to get or set attributes of a particular element

i.e getting attribute of img or setting
```
$('img').attr()
or
$('img').attr({
src:"/big.jpg",
title:"Jimmy Big"})
i.e setting attribute of a link to direct to google

$('a').attr('href','http://google.com');
.val()
```

this is used to set the value of an element
i.e
```
$('input').val("Ramos");
Adding and removing css classes using jQuery

$('div').addClass("collapse");
$('div').removeClass("collapse");
//toggle between add and remove class
$('div').toggleClass("collapse");
```
 - jQuery Events

 -- click()

This is fired when you click on something in the DOm

i.e Clicking a submit button
```
$("#submit').click(function(){
   alert('you submitted your form')
})
```

-- keypress()

This is triggered when you press a key on the keyboard i.e alert when you press the enter key

```
$('input["text"]').keypress(function(event){
   if(event.which===13){
alert("You hit enter");
});
ps see javascript character key codes to know the key codes of each key
```

-- on()

This is the most useful one because it takes many events as it’s functions

i.e on using the click() function.
```
$('#submit').on('click',function(){
 alert('you submitted your form')
})
```

### jQuery Effects

this are various effect or animations that are easy to complete compared to using vanilla js.
Following are a few of them

--- fadeOut()
--- fadeIn()
--- fadeToggle()
--- slideDown()
--- slideUp()
--- slideToggle()


Syntax
```
effect(duration,function(){dosomething})
i.e example using fadeOut

fadeOut(1000,function(){})
```

### Focus
focusing on specific element 

i.e example of showing error message 
```
$("#password").focus(function(){
	if($(this).val().length > 8){
    	$(this).next().hide();
	}else{
		$(this).next().show();
	}
}).keyup(
function(){
	if($(this).val().length > 8){
    	$(this).next().hide();
	}else{
		$(this).next().show();
	}
}
)
