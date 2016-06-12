[npm](https://www.npmjs.com/)


##### Install a package

```
npm install bcrypt
```

##### Managing dependencies with package.json 

```
npm install <pkg> --save 


name:
version:
description:
entry point:
test command:
git repository:
author: Kofi ramos
License:

```


##### Setting environment mode


```
NODE_ENV npm install <pkg>
```

##### Updating packages

- updating packages

```
//inside package.json 
"colors":"~0.8.4" //installs 0.8.4  ,0.8.5  but not 0.9.0 
"colors":"^1.8.4" //installs 1.2 ,1.3 but not 2.0 
```


to update 

```
npm update --save

```

- checking to see outdated packages 

```
npm outdated 

```

#####   Uninstalling packages 


```
npm uninstall colors 
```

to remove from dependencies as well 


```
npm uninstall colors --save 
```

 to remove from development 


```
npm unintsall mocha --save-dev 
```

 uninstall global packages 


```
npm unistall http-server -g 
```
