# CS15L Lab Report
In this lab report, I am going to show how to log into a course-specific account on ieng6 and run some command.
## 1. Installing VScode 
You can find it simply through Google.
![Image](https://user-images.githubusercontent.com/97556577/149047779-986bc715-dbbf-44eb-afcb-72abfde99c45.png)
 Find the approparite version for your pc system. I am using Mac, so i downloaded the mac version.
![Image](https://user-images.githubusercontent.com/97556577/149047978-795b4ea2-3b8c-42c4-b9ab-4d1f1ea11a03.png)
## 2. Remotely Connecting
Then, in the terminal, using ssh command to try to connect to your course specific account like this.
run command
```
ssh cs15lwi22akk@ieng6.ucsd.edu
```
![Image](https://user-images.githubusercontent.com/97556577/149048167-fdd9ecc7-16d2-4e7b-8e68-eeade6c98479.png)
 It will ask for your permission to connect to the server. Simply type yes.
![Image](https://user-images.githubusercontent.com/97556577/149048319-eaea85c0-c667-4ca1-85d1-636e3e110bc9.png)
 Then, copy and paste your passwords below. It is normal that it remain unchanged after you pasted the password.
![Image](https://user-images.githubusercontent.com/97556577/149048410-f4e5c91c-7b9b-44d8-b9b0-9ae38dfb2e71.png)
 If everything work, you should see this page.
![Image](https://user-images.githubusercontent.com/97556577/149048460-d988fd5e-545e-472c-a205-c9d81ec9b903.png)
 Now, you are on the server, type some command to see how it works.
## 3. Trying Some Commands
Let's try some command like this.
```
cd ~
cd
ls -lat
ls -a
```
![Image](https://user-images.githubusercontent.com/97556577/149048608-edcea8f0-e1fb-4063-8dca-0702a3afd8e7.png)
![Image](https://user-images.githubusercontent.com/97556577/149048622-c994a9de-03f3-4ae0-8bd0-a78248588685.png)
## 4. Moving Files with scp
 Specfically, scp command can copy the file on your pc to the server
 ```
 scp WhereAmI.java cs15lwi22akk@ieng6.ucsd.edu:~/
 ```
 This copies files on your pc to the server.
![Image](https://user-images.githubusercontent.com/97556577/149050776-a131446e-2733-4de8-a864-0985ec6e0d29.png)
## 5. Setting an SSH Key
Next, we want to set up an SSH key that simplify the login process.
 Firstly, use ssh-keygen command to create a pair of key that stores on your pc and server. 
 ```
 ssh-keygen
 ```
![Image](https://user-images.githubusercontent.com/97556577/149051053-ae7f3d13-324b-4153-b10c-dcf0fa9c3592.png)
 Then, log into your account and type command below
 ```
 ssh cs15lwi22akk@ieng6.ucsd.edu
 mkdir.ssh
 ```
![Image](https://user-images.githubusercontent.com/97556577/149051233-bded4c45-8e6c-48f8-80b6-557adc604c40.png)
 Finally, copy the key and update it to the server use scp command.
 ```
 scp /Users/lidongyang/.ssh/id_rsa.pub cs15lwi22akk@ieng6.ucsd.edu:~/.ssh/authorized_keys
 ```
![Image](https://user-images.githubusercontent.com/97556577/149051319-5eb11057-b864-452e-8c5e-f7d7e9ba43eb.png)
 Then, you can log into your account without password!
![Image](https://user-images.githubusercontent.com/97556577/149051400-3a38be83-d325-4681-818b-02588f273671.png)
## 6. Optimizing Remote Running
If we do not use keystroke, we have to type in password when every time we run the command,
however, now, we can simply run command remotely without wasting time on type password each time.
```
ssh cs15lwi22akk@ieng6.ucsd.edu "ls"
```
In this way, we can run command remotely without logging in to our account each time.
![Image](https://user-images.githubusercontent.com/97556577/149416655-234ee41a-c5f2-4c98-9bde-7267befa8dfa.png)
```
cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```
 Moreover, you can run many command in one line by using semicolons.
![Image](https://user-images.githubusercontent.com/97556577/149416712-0b8db7bf-4cab-412c-bf7f-6d0249a111b3.png)
