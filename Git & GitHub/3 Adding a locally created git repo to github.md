what i have :
* I have a project ***e-library*** which has a main branch name as : "main"
![5265980456aa1c9ee75410b1895ceb0a.png](../_resources/5265980456aa1c9ee75410b1895ceb0a.png)
 
 follow the instructions on github as follows:
 ![1dcf41b059d049e9089b091cfd22c657.png](../_resources/1dcf41b059d049e9089b091cfd22c657.png)

do these steps: 
step1:
get the link from the GitHub Repo in the Browser
```
git remote add origin https://github.com/adarsh27april/e-libray.git
```

`git remote`  will list all the remote sources
`git remote -v` lists all the remote sources url


step :
```
git push -u origin main
```
push `main` branch to the origin repository
![250961d472abc6ef7a1d65189aabfd08.png](../_resources/250961d472abc6ef7a1d65189aabfd08.png)

![672c12916f64e5cc1926a6c7955a3412.png](../_resources/672c12916f64e5cc1926a6c7955a3412.png)


Do not pay attention to below: 
***The errors that i was encountering***:
* ![a3b04bac72e0a29e8cd7caa8daf069c8.png](../_resources/a3b04bac72e0a29e8cd7caa8daf069c8.png)
* *`ssh-agent` is not recognised* in pwsh
my solution:
open pwsh
type `sh` and enter
now pwsh will work line git bash and it will look like that as well
enter the command: 
```
ssh-keygen -t ed25519 -C "adashkumar27april@gmail.com"
```
enter the passphrase and then good to go
