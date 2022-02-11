# Lab Report 3
## Streamling ssh Configuration
1. The first thing to do is open the ~/.ssh file. For Mac, you can simply open VS code and click open folder.
![image](https://user-images.githubusercontent.com/97556577/153668420-7954ca05-f56c-4ff8-82e9-8097bd7e17b8.png)
Then, use ```command+ shift + G```to search for ```~/.ssh```folder.
![image](https://user-images.githubusercontent.com/97556577/153668665-40cc5c78-a8ef-4320-b6c3-540226173931.png)
You will see a folder like this.
![image](https://user-images.githubusercontent.com/97556577/153668775-75780a4f-6387-47b4-8a0b-b681c44d0656.png)
2. Open the config file in the folder in vs colde and write down several lines of command
```
Host ieng6
  HostName ieng6.ucsd.edu
  User cs15lwi22akk
```
![image](https://user-images.githubusercontent.com/97556577/153668957-1c340890-1006-4e22-b753-ce5a32109f56.png)
Host stands for alias that you choose for ssh to interpret.
HostName is the name of server.
User is simply your username.

3. Then, try ```ssh``` and ```scp``` command with terminal.
```
ssh ieng6
```
![image](https://user-images.githubusercontent.com/97556577/153669480-d47699d5-2280-488b-9923-1f9c84126383.png)
We successfully log in to the server without typing username and password!
Same thing with ```scp```command.
There is a file name hello.java in my local.
Use``` scp hello.java ieng6:~/```tkcopy this file to server.
![image](https://user-images.githubusercontent.com/97556577/153670018-059f10e9-d126-412b-a501-f297c657f908.png)
We can see the file is there by using ```ls``` command.
![image](https://user-images.githubusercontent.com/97556577/153670297-ca5f35b2-4695-4608-8a64-9a96376d6cc2.png)
