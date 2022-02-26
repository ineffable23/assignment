# Git Assignment

## Problem Statement: 
1.	Show an example of git rebase and how can it be used to resolve conflicts in a feature branch before merge
2.	Do cherry-pick a merge commit
3.	Show an example of git-bisect
4.	Recover an accidentally deleted a branch, and has already pushed the changes to the central git repo. There are no other git repos, and none of your other teammates had a local copy.
<br>

## Solution:
### 1.	An example of git rebase
 ![Screenshot (203)](https://user-images.githubusercontent.com/49369387/155843411-0ad7152a-4620-457e-8345-0ef6fb6cfa70.png)
Rebasing is used to integrate changes from one branch into another to resolve conflicts when multiple commits happen on the same file.
1.	Submit a change.
2.	Somebody else submits a change and that change merges. Now your change has a merge conflict.
3.	Update your local repository:<br>
   ```git remote update``` <br>
   ```git pull --ff-only origin master```
4.	Download your change:<br>
   ```git review -d <PARENT_CHANGE_NUMBER>```
5.	Rebase your change:<br>
   ```git rebase origin/master```
6.	Resolve conflicts manually:<br>
    Conflicts are marked in a file with clear line breaks:
    ```
      <<<<<<< HEAD
      Second line.
      =======
      Third line.
      >>>>>>> feature/topic branch.
    ```

    Here, <br>
    ```<<<<<<<```: Indicates the start of the lines that had a merge conflict.<br>
    ```=======```: Indicates separation of the two conflicting changes.<br>
    ```>>>>>>>```: Indicates the end of the lines that had a merge conflict.<br>
    You need to resolve a conflict by manually editing the file. You also need to delete the ```‘<<<<<<<’, ‘=======’, and ’>>>>>>>’``` in the file.
7.	Add the files to the stage:<br>
    ```git add <FILENAME>``` 
8.	Complete the rebase process:<br>
	  ```git rebase --continue``` 
9.	Send the rebased patch again for review:<br>
  	```git review``` 
### 2.	Cherry-pick a merge commit
![Screenshot (205)](https://user-images.githubusercontent.com/49369387/155843435-4bfa054b-c0b5-4d05-8973-b1b57602f9b6.png)

### 3.	An example of git-bisect
 ![Screenshot (206)](https://user-images.githubusercontent.com/49369387/155844052-b1c02181-fac7-4edb-908e-44c5e0fccb4f.png)


### 4.	Recover an accidentally deleted a branch, and has already pushed the changes to the central git repository.
![Screenshot (207)](https://user-images.githubusercontent.com/49369387/155843437-c9b5fd76-d052-4f5f-b8c5-c057dad52c52.png)
![Screenshot (208)](https://user-images.githubusercontent.com/49369387/155843438-6315c472-e073-4550-833e-6b430e6e0727.png)

### Graph
![Screenshot (209)](https://user-images.githubusercontent.com/49369387/155843441-1d8b2729-8254-4f21-a6e3-6b699611dc80.png)


 
 
