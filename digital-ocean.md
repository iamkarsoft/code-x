Creating A Lamp Stack

### 1- Creating a droplet

##### Give it a name 

##### choose server and add ssh key


###### Adding ssh key

1- Change into ssh directory
```
cd .ssh
```

2- Now let's generate the keygen

```
ssh-keygen -t rsa
```

Give it a name for example Kamal which will create a private key kamal and a public key kamal.pub

3- If you want to view your key

```
cat kamal.pub
```

### 2- Accessing server

1 - change into ssh directory to connect to our droplet server

```
ssh -i project root@serverip
```


2- making server ready for sql

`mysql_secure_installation ` and answer the questions

3-  remove info.php and index.html
`rm info.php`

- restarting apache
`service apache2 restart`

- finding php ini
`cd etc/php5/apache2`

### 3- Ftp into our own server using SFTP

- add private key to filezilla
` setting > Connection > Ftp > SFTP > choose your private key > convert > rename and resave`

- Now fill the host `sftp://ipaddress` `username:root`

### 4- Adding Domain Name to server

- `dns > add domain > enter domain name > chhose project and create`
- pick DO nameservers and change them in where you bought your domain name

### 5- Updating PhP configuration file

i.e to turn on displaying error

- `etc/php5/apache2` and edit php.ini file and turn on display errors
- restart apache `service apache2 restart`

### 6- Connecting to Mysql Server

- ssh into your server

- connect to server
`mysql -u root -p`
`enter password`

1- use heidi host or sequel pro

- fill in details 

### 7- Using Phpmyadmin

- go to [php my admin site](http//phpmyadmin.net) and download 
- create a phpmyadmin folder in html and copy to the folder
- 



