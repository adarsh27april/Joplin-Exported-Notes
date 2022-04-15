![1300eb3b695caa8eb8dd49c7c3098175.png](../_resources/1300eb3b695caa8eb8dd49c7c3098175.png)

`git status` command shows the status of all the files in the git initialized folder

![85f8ef39bc99ca856e79deaf916fba84.png](../_resources/85f8ef39bc99ca856e79deaf916fba84.png)

**Untracked** : git won't tract these files.These files are conciously told Git-Hub to untrack them. These type of files include like *log* files

**Staged** : इसमे हम वो चीज़े डालते है जो हमे commit करनी होती है commit is a snapshot of the project

कभी भी हमे अपने project की tracking को start करने के लिए एक commit करना पडता है और उसे हम initial commit कहते है

Earlier index.html was an untracked file after adding it to the **Staged** area by command `git add index.html` :
![6a13d6b833e2680f54156008ad68b0cb.png](../_resources/6a13d6b833e2680f54156008ad68b0cb.png)

After commit the file index.html moves to **Unmodified** area and git shows us `working tree clean` i.e., till now all the changes till now are commited
![bbefe4235c93cbb2cb645da42b57aa17.png](../_resources/bbefe4235c93cbb2cb645da42b57aa17.png)

After this if some changes is made in the index.html then it will move to **Modified** area

`touch about.html` will create a blank file `about.html`

`git add -A` will track all the untracked files

1.  ![db6f99b8763e78945aa6fd385ef81251.png](../_resources/db6f99b8763e78945aa6fd385ef81251.png)
    
2.  ![79aed13e62fcf502f8699fd2b0eeeb4f.png](../_resources/79aed13e62fcf502f8699fd2b0eeeb4f.png)
    
    - Here the empty version of all the files has been added to the **Staged area**
    - > On making changes in the `contact.html` file:
        > ![62c0229f8520df02479930101d824486.png](../_resources/62c0229f8520df02479930101d824486.png)
        
3.  ![2d0a29bbe816779c55add494bd7591be.png](../_resources/2d0a29bbe816779c55add494bd7591be.png)
    
    - Here `contact.html` is in both **Staged** and **Modified** area
        
    - In **Staged** area it's empty version is present
        
    - In the **Modified** area its new edited version is present.
        
    - ![4a82330f6e931e0b9eb62c9f068d917d.png](../_resources/4a82330f6e931e0b9eb62c9f068d917d.png)
        now the updated version of Contact.html is present
        

![d54e0e1f95d581543330bd7fb82b8f9e.png](../_resources/d54e0e1f95d581543330bd7fb82b8f9e.png)

`git checkout contact.html` का मतलब यह है की मेरे last commit मे जो contact.html है उस से match करा दो
ex:
initial contack.html:
![df7928ac31ede94d999f1ab2c0ba5f18.png](../_resources/df7928ac31ede94d999f1ab2c0ba5f18.png)
Final
![32e00bea4ea923b9f0b8af1162db877f.png](../_resources/32e00bea4ea923b9f0b8af1162db877f.png)

`git status` command
![4284fbf0f571cf28ba29a5a148a3ec91.png](../_resources/4284fbf0f571cf28ba29a5a148a3ec91.png)

`git checkout contact.html`
![69ae6dae79f0cd98c4814acf0d8511aa.png](../_resources/69ae6dae79f0cd98c4814acf0d8511aa.png)

`git checkout -f` to match all the changed files with the previous commit
![b2326bb3a51cbacabdf3c66c59a2a765.png](../_resources/b2326bb3a51cbacabdf3c66c59a2a765.png)

![e8059c6b29bdeb90678d418de6bda2fd.png](../_resources/e8059c6b29bdeb90678d418de6bda2fd.png)

`git log -p -1` will show last one change to see more replace 1 with some number.
![55cbea5ec7b63d83920b673cb398f278.png](../_resources/55cbea5ec7b63d83920b673cb398f278.png)

git diff shows the difference b/w the working directory and it's Staging area.
like:
![dded66dd7e8f10889a1be9769e21393a.png](../_resources/dded66dd7e8f10889a1be9769e21393a.png)

![6a16658ab473dd47003c8f83ecbeb375.png](../_resources/6a16658ab473dd47003c8f83ecbeb375.png)

if i add the files to the staging area by `git add -A` then if i run `git diff` it won't show any changes. Because the Stageing area and the working directorya are same.

![cad469bd0ce9656c2038d92b843a7d5a.png](../_resources/cad469bd0ce9656c2038d92b843a7d5a.png)

`git diff --staged` will compare the staging area with the last commit
![ec5b519cd46917258e4fb98c7538c5e8.png](../_resources/ec5b519cd46917258e4fb98c7538c5e8.png)

Try Avoiding it as much as possible: To directly commit without staging. Like:

- ![68ee3deba6583f106383f9d36e0b448f.png](../_resources/68ee3deba6583f106383f9d36e0b448f.png)
- ![1af154973d58cfca9b3372a9e75c4a94.png](../_resources/1af154973d58cfca9b3372a9e75c4a94.png)

> Removing some file from the commit:
> 
> ![efc5baf3c0e01f7d2454b00fa5fe74b9.png](../_resources/efc5baf3c0e01f7d2454b00fa5fe74b9.png)
> 
> ![4a5fe5b1abac78384ed2b537875b49c5.png](../_resources/4a5fe5b1abac78384ed2b537875b49c5.png)
> 
> `git rm --cached waste.html` will remove the file only from the staging area only, the file will remain in the directory. Useful if we want to Untrack a tracked file
> 
> ![6e2a8adfa57aef98c148047facd67907.png](../_resources/6e2a8adfa57aef98c148047facd67907.png)
> 
> `git rm -r --cached folderName/` will remove a folder *folderName* from being tracked
> 
> ![14d64732b255950f6d657ab3011c64fe.png](../_resources/14d64732b255950f6d657ab3011c64fe.png)
> 
> `git rm waste.html` will delete the file from the directory as well as also from the staging area, but before it we will have to add it to the staging area.
> ![9a0cb93fa3e310b92b2606abf31f3984.png](../_resources/9a0cb93fa3e310b92b2606abf31f3984.png)
> ![7023aa5a13b469da93139eebae0f629a.png](../_resources/7023aa5a13b469da93139eebae0f629a.png)

![d81385b8c5b03a557b06c0458dd74e3a.png](../_resources/d81385b8c5b03a557b06c0458dd74e3a.png)

- 1st डब्बा green → **Staging** area
- 2nd डब्बा red → **Working dir**

![99ef6f7d6991133be8e95e5a7b8c0b36.png](../_resources/99ef6f7d6991133be8e95e5a7b8c0b36.png)

`gitignore` command:
To untrack some files like: log files or some automatically generated output files of some programs which can be generated in any system.

> if `.gitignore` isn't present
> ![cc42b52c64d245042c2980910c533ad2.png](../_resources/cc42b52c64d245042c2980910c533ad2.png)
> create folder `.gitignore` by `touch .gitignore`
> the name of the files written in `.gitignore` file will be ignored from being tracked.
> inside `.gitignore` if we write:
> `/fileName.extension` then only the `/mylogs.log` in the dir same as that of `.gitignore` will be tracked if the file will be inside some other folder won't be tracked
> ![bc420cf2849a56ac7abd0c4a0e926077.png](../_resources/bc420cf2849a56ac7abd0c4a0e926077.png)
> ![123eae36b9d2a2d61ea610d7dab9a521.png](../_resources/123eae36b9d2a2d61ea610d7dab9a521.png)
> `*.log` will ignore all the files with `.log` extension
> 
> To ignore a directory

## Git Branches

default branch is `master`
![2d33ee7bfad3e6b976720c79274eca69.png](../_resources/2d33ee7bfad3e6b976720c79274eca69.png)

to move to branch `feature1`
![e5efd65aa975da5baddc06dc06331a31.png](../_resources/e5efd65aa975da5baddc06dc06331a31.png)

At this time if we check the **master** branch by: `git checkout` then nothing has been changed in it.

Merging the **feature1** branch into the **master** branch

1.  first checkout to master branch
2.  then run `git`
    ![d65510f9b8dd68befad0f7fc05f72268.png](../_resources/d65510f9b8dd68befad0f7fc05f72268.png)

To create a branch and switch to it by a single command:
![e6ac61fc6afeb335edbfd02c271b07d3.png](../_resources/e6ac61fc6afeb335edbfd02c271b07d3.png)

## Pushing into remote repo (GitHub)

![7c4de95b0ddcb5d8b2be13c52a76e7dd.png](../_resources/7c4de95b0ddcb5d8b2be13c52a76e7dd.png)

![766c26e5b8709a0082704ba2ba9466fc.png](../_resources/766c26e5b8709a0082704ba2ba9466fc.png)

![97a0e18434349c5566335f18fe69b116.png](../_resources/97a0e18434349c5566335f18fe69b116.png)

![5c91b91620368e605cbf797ac2e32c85.png](../_resources/5c91b91620368e605cbf797ac2e32c85.png)

![3e43c511a6255a03d3ccf91bdbd19d76.png](../_resources/3e43c511a6255a03d3ccf91bdbd19d76.png)

Remaining inside some branch of the Git Repo run commands if already have a SSH key:

- `git remote add origin https://github.com/adarsh27april/Git-in-One-Video.git`
- `git remote`
- `git remote -v`
- ``eval `ssh-agent -s` ``
- `ssh-add ~/.ssh/id_rsa`
- in video here the https url has been changed to ssh url at this point by:
    `git remote set-url origin git@github.com:adarsh27april/Git-in-One-Video.git`
- `git push -u origin master`
- to push flaskIntegration branch first checkout to that branch and run : `git push -u origin flaskIntegration`

![ea0a2a2a40a10c75b6de8b7ca1be94ed.png](../_resources/ea0a2a2a40a10c75b6de8b7ca1be94ed.png)

![81d5a78a11d72f2209970642d6fb80d3.png](../_resources/81d5a78a11d72f2209970642d6fb80d3.png)