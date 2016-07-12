##### cloning the git file

```
git clone https://github.com/firebase/friendlychat
```

##### creating a firebase app

- go to [firebase](firebase.google.com)

- get started > new project > fill in details (using camel case for name)

- select web app > copy the snippet and paste it into your projet's footer

- enable google auth -> Auth > Sign-in-method

- install firebase console (cli)

- change into your project folder and start firebase
 
 ```
 // this lists all your firebase project stored on google servers
 firebase use --add
 ```

 - now run firebase

 ```
firebase serve

//changing port 

firebase serve -p 5000
 ```


- adding authentication to your server by adding the snippets to your main js file

- include the initial json file  db > import json from your project file

- pulling messages using event listeners 