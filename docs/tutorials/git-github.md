# Complete Guide To Git and Github

<img src="../.vuepress/public/gitforblog.png" class='gitImg'/>

## what is git?

now we are in one of the most important topics for every programmer.
not just web developers.first i will explain git and github and their use cases in simple terms with real world exmples then i will teach both of them in action with code.
let's start :wink: . git is a version control system and it is a complete life saver.but what is a version control system ? :confused:
imagine that you have an application that you want to add a new feature to it let's name it feature-one after you completed feature-one you realised that you have a better idea and you don't want to go with feature-one so you delete the feature-one completely and start to make a new feature named feature-two after it completes you realize that actually feature-one was better than feature-two.so again :weary:
so have to write the feature-one from scratch. actuall these kind of confusions are so common specially in larger projects. and it is a complete waste of time to re-write the whole code for so many times.
so there should be some ways to switch between different versions of your code without writing it. and ta-da :grinning: this is where Git comes on the scene.

## what is github?

imagine that you are saving all of different versions of your app in your local computer after a while you will see something like this
<img src='../.vuepress/public/fulldrive (1).png'>
<br/>
in this case you will need somewhere to save different versions of your apps in elsewhere and this is where you should use github.
in another word github is a place in the cloud to save your code.
<br/>

## install git

:::tip
before we start the practical parts of git and github you have to install git on your computer.click the <a href='https://git-scm.com/downloads'>link</a> to install it.
:::
to make sure that git is installed on your computer open up your terminal and type the command below:

```sh
 git --version
```

if this command returns a version to you then everything is ok.
make an index.html and style.css in your folder and imagine this is the project that you want to initialize git in it and track your changes. if you want to initialize git in your project you have to run this command in that specific directory.

## git initialization

```sh
git init
```

this command will create a local repository in that specific folder and also it will create a <span class='highlight'>.git</span> folder inside your projects root but probably you can't see it because it is hidden you should enable showing hidden files and folders to see it but it is not necessary i just want to clear it for you that how it is working. we had made a css and html files so let's work with them. they are currently empty add this line to your index.html file.

```html
<h1>feature one</h1>
```

then lets run this command:

```sh
git status
```

this will show the files that are untracked or in another word files that are displaying in red color are untracked. each time that you are making a change to your files you should track them imagine that you want to track your feature-one or you want to say to git hey git this feature-one is really cool i want you to track or save the current situation of my projects in real world you don't have to track your files for small changes like this which is adding a single line of html in this case but imagine this one line as a complete feature to our app . you can do it with just two commands

## staging area

```sh
git add .
```

`git add .` command will add all of your files to staging area.
:::tip
when you are adding your files to staging area you are telling git that make all of my files ready to be tracked but there is another step to completely done this process or in a technical way to commit all of our files
:::

## commits

```sh
git commit -m "feature-one added"
```

`the text after -m is just a descriptive message to remind you what is each commit about`
with this command you have completed the process successfully and the current version of your code is saved.
but imagine you realized that actually feature-one is not that cool so you want to change it to feature-two.
in index.html file change the current h1 to this:

```html
<h1>feature-two</h1>
```

if you run `git status` command you will see that index.html is red and it is modified so we have to do the same things again first `git add .` to add it into staging area btw you can also do `git add index.html` because in this case we want to add just index.html to staging area. then just run `git commit -m "feature-two added"`. now you successfully commited your files.
imagine that after feature-two is completed you realized that feature-one was better so instead of re-writing all of your code (which is just one line in our case but it is not a real world example) you can easily switch between different versions of your code.if you want to check all of your commits do this:

```sh
git log
```

or if you want to see them in a more clear way you can simply do this

```sh
git log --oneline
```

## swtich between commits

now you can see all of your commits with their message and a unique id beside it you can easily switch between different commits with this command:

```sh
git checkout <unique id of that specific commit>
```

now if you check your html you can see it is feature-one. then if you want to return to the most recent commit you can simply run:

```sh
git checkout master
```

and you can easily switch between different commits.

## how github works

if you want to push your files to github first you have to make a github account.
<br/>
<img src='../.vuepress/public/githubRepo.png' alt='github repo'>
<br/>
after creating a new repository on github you can push your project to github but before that make sure that you have commited all of your changes first you have to run this command:

```sh
git remote add origin https://github.com/<PATH THAT GITHUB GIVES YOU>
```

as you know git is version control system that you can interact with it locally git provides `remotes` to comminucate with the outside world remotes actually are just repositories outside of your computer which you can push your changes into. the command `git remote add origin <path>` will create a remote repository called origin. after this command you have to actually push your project to that remote repo with this command:

```sh
git push origin master
```

with this command you will push your project to master branch of the origin repository.<br/>okeey this is the end of the git and github for begginers tutorial i'm planning to make a tutorial about more advanced topics in git and github like branching,merging,pull request,etc in the near future. hope you learned a lot. have a good day or night in where ever you are :v: :v:.
