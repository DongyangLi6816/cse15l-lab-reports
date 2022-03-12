# lab report 5
## Part 1: Difference
First of all, I used ```bash script.sh > results.txt``` command to generate a ``results.txt`` file in both implementations' repository.
![image](https://user-images.githubusercontent.com/97556577/157992167-2de3a601-f3ef-4db9-9e72-c41180d69b96.png)
![image](https://user-images.githubusercontent.com/97556577/157992346-5149b51c-753b-4d0a-8722-66165c4cc967.png)
Then, I use ```diff``` command with the path of two ``results.txt``` files to find out the different output.

```diff /Users/lidongyang/Documents/GitHub/markdown-parse2/results.txt /Users/lidongyang/Documents/GitHub/markdown-parse/results.txt```
![image](https://user-images.githubusercontent.com/97556577/157992855-c974b9c8-fc09-416e-bd4f-d88ca051316a.png)
## Part 2: specific differences and fix
In line 230 of both ```results.txt``` file, which is test201
![image](https://user-images.githubusercontent.com/97556577/157994153-43b748b2-6a09-4142-a5c2-ba0227ec265d.png)
Implementation from class output result as ```[baz]```, in contrast, my implementation does not print out anything.
According to VS Code preview, there should not be a link.
![image](https://user-images.githubusercontent.com/97556577/157994397-e6db34e9-23b9-488b-89cc-b5a7dfd5786d.png)
At this point, my implementation is correct.
I think this bug is caused by the forgetting the insertion of ```<>```.
![image](https://user-images.githubusercontent.com/97556577/157995388-f09346c9-b2cd-4a08-b0c4-793ec86f43f1.png)
The fix is to add a if statement to detect the index of ```<>``` and compare them with the index of brackets and parens.

In line 862 of the ```results.txt``` file which is test 487, implementation from class output nothing, while my implementation prints ```/my uri```

![image](https://user-images.githubusercontent.com/97556577/157995745-5bdd1174-d626-446d-b830-fa1961398885.png)

According to the VS code preview, my implmentation is incorrect, becasue there should not be any link.

![image](https://user-images.githubusercontent.com/97556577/157995834-d5f98a47-2ede-43d5-a40b-caa2e2dc799e.png)

This bug is casued by i did not include any detections for blank in my implementation

![image](https://user-images.githubusercontent.com/97556577/157995920-22bec5e6-eb79-4815-8cbc-ccf0c2c08d62.png)

The fix is to add a if statement and detect to see if the black is in the bracket.
