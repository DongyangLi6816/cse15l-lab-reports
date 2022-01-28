# Lab report 2
## 1. File with two parenthesis
Code difference
![image](https://user-images.githubusercontent.com/97556577/151599564-602cd3eb-b18d-4215-94eb-3069c6a874c7.png)
Test file Used
```
[a link!](https://something.com)
[another link!](some-page.html)

[](hel)lo)
```
The error message

![image](https://user-images.githubusercontent.com/97556577/151599818-bd9fc599-a1b4-4c25-b331-67e0f842a018.png)

This symptom is caused by infinite loop bug. 
When you have a loop that neverd ends, it occupy too much memory space. That's why it cause out of memory error.
The failure-inducing input includes two right parenthesis at the end. It cause current index never update, so the current index is never going to equal to the length of markdown file.

## 2. File with no parenthesises
Code difference
![image](https://user-images.githubusercontent.com/97556577/151602534-54780c99-c321-4968-b891-d944d6f6ec3b.png)
Test file used
```
# title

[]link goes here!
```

The error message

![image](https://user-images.githubusercontent.com/97556577/151604131-1225cead-dc25-4ad9-aec1-2ef1ff3db7a5.png)

Since there is no parenthesis in this file. The ```indexOf()``` method will return -1, which cannot be a index. That's why it induce index out of bounds.

## 3. file with no links
Code difference
![image](https://user-images.githubusercontent.com/97556577/151602534-54780c99-c321-4968-b891-d944d6f6ec3b.png)
Test file used
```
adsadasd
asdasdasd
```

The error message

![image](https://user-images.githubusercontent.com/97556577/151605234-9d60276d-84b3-4644-a5b5-c73cad79267e.png)

Similar to previous one, the ```indexOf()```method cannot detect [] and (), so it returns -1, which cannot be an index, which induces index out of bounds.
