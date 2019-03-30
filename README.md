# b00t2root-19

  
  
## Start :   
First of all we login to our ssh server
```
exec socat tcp-connect:18.217.123.244:2604 file:`tty`,raw,echo=0
```
So the task is saying that we need to become tony and if we do  
```
cat /etc/passwd
```
We find that tony is an user so we enter tony's home directory and in it we find a hidden file named flag and as you see we cant neither read it or modifiy it so the only way to get it is to become tony 
  
  ![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-31%2000-00-09.png)  
    
 So we gona try to become tony without any need for password authentification 
 So First to set up a passwordless SSH login in Linux all you need to do is to generate a public authentication key and append it to  
 ```
 .ssh/authorized_keys
 ```  
 Thats the key that i generated
  
 ![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-30%2022-21-35.png)
  
 and to be sure that the key is generated we check the :
 ```
 .ssh/id_rsa.pub
 ```  
 ![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-30%2022-24-42.png) 
  
so after we generated steve's key we need to copy it to tony's authorized_keys because we have to login to tony as steve    
but in tony we dont have a .ssh folder so we make it and then we create the authorized_keys file and copy the key in it   
  
![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-30%2022-34-00.png)

  and now we login to :  
  ```
    ssh tony@localhost
   ```
   and here we go no need for authentication now we got a shell as tony   
    
   ![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-30%2022-35-30.png)
    
  then we do :  
  ```
  ls -al
  ```
  and here is the file flag now we need to only give it permissions so i just gave it 777
  ```
  chmod 777 .flag
  ```
  then cat it 
  ```
  cat .flag
  ```
  ![alt tag](https://github.com/GodRagna/b00t2root-19/blob/master/Screenshot%20at%202019-03-30%2022-38-00.png)  
  
  ## and there is our flag 
  b00t2root{1_h0p3_ssh_15_th3_0nly_w4y}
