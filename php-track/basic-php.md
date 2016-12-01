### Array

```
$names= ['Kofi','billy','dale'];

echo $names[];

```

adding something to array `$names[]="josh"`

### functions

```
function fullName(){
   echo 'Kofi Ramos'; // or return 'Kofi Ramos' 
}
```

calling out the function `echo fullName()`


- constructing a value

```
function fullName($firstName, $lastName){
return  $firstName .''.$lastName;
}
```

invoking the function `echo fullName('Kofi', 'Ramos');`