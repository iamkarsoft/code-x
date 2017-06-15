Creating Awesome labels following the tutorial travis nielson on devtips


##### Html structure

```
<form class="awesome-form">

<div class="input-group">
<input type="text">
<label> Your Full Name</label>
</div>


<div class="input-group">
<input type="email">
<label >Your Email</label>
</div>


<input type="submit">





</form>
```

###### Sass for styling

```

//basic styling
body
    padding: 100px
    -webkit-font-smoothing: antialiased

input
    background: none
    border: solid 2px #21a1e1
    color:  #21a1e1
    padding:    25px 40px
    display:    block

    &:focus,
    &:active
        outline:    none

    &[type="text"],
    &[type="email"]
        border: none
        border-bottom:  solid 2px #21a1e1

    &[type="submit"]
        &:active
            color:  white
            background: #21a1e1

    .input-group
        display:    inline-block
        margin-right:   20px;
        position: relative


        input 
            padding:    15px 0px


    label
        +position(absolute, 50% null null 0%)
        +transform(translateY(-50%))
        font:
            family: $georgia
            style: italic
            size:   18px
        color: #999
        pointer-events: none
        +transition


    input:focus + label,
    input.has-value + label
        top:    -10px
        font-size:  12px
        color:  #aaa

```



### Javascript

```
//to keep label there using jquer

$(function(){
    $('.awesome-form .input-group input').focusout(function(){
        var text_val=$(this).val();
        if(text_val==""){
            $(this).removeClass('has-value');
        }else{
            $(this).addClass('has-value');
        }
        })

    })

```