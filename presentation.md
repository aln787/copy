## Unleashing Github
##### _(Unlocking the power of version control / distributed collaboration)_
<p>
	</br>
	<small><a href="https://twitter.com/alexniderberg">@AlexNiderberg</a></small><br/>
	<small>iOS and Android Reliability Engineering - Capital One</small>
</p>


### Presentation Objectives
<ul>
<li>Introduce version control using Git and Github.</li>
<li>Prepare you for your hackathon later this week.</li>
<li>Leave you excited to become a version control expert.</li>
</ul>
<br/><br/>
<p class="fragment">
[<u>Collaboration</u> is one of the top 3 skills that companies need.](https://learning.linkedin.com/blog/top-skills/the-skills-companies-need-most-in-2019--and-how-to-learn-them)
</p>


<img src="images/intro/Alex_and_Catelyn-CryatalMt-WA.png" height="600">


<img src="images/intro/CapitalOneLabs_Overview.png" height="600">
<br>
<small><a href="https://capitalonecareers.com/">Capital One</a></small>


<img src="images/intro/CapitalOneLabs_Work.png" height="600">
<br>
<small><a href="https://www.capitalonelabs.com/#/about">Capital One Labs</a></small>

---
## The Software Development Life Cycle


<img src="images/idea.jpeg" alt="idea" height="400">


<img src="images/BarnyChallengeAccepted.png" alt="Challenge Accepted" height="400">


### I did it!!!
<img src="https://giphygifs.s3.amazonaws.com/media/PzOm3LPWu7fJS/giphy.gif" width="680" height="567">
<!-- <iframe src="https://giphy.com/embed/PzOm3LPWu7fJS" width="680" height="567" frameBorder="0" class="giphy-embed" allowFullScreen></iframe> -->
<!-- victory-reaction-jennifer-lawrence-PzOm3LPWu7fJS -->


#### Joy turns to anger so quickly
![](images/Man_yelling_at_computer.JPG)


### How can I prevent this from happening again??
<iframe src="https://giphy.com/embed/FdvUazOcLjwzK?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- ConfusionCubsRunning-FdvUazOcLjwzK -->


## Living a version controlled lifestyle
- We could zip our project folders to make versioned backups?
```
myHackathonProject/
myHackathonProject_180930.zip
myHackathonProject_181003.zip
myHackathonProject_181031.zip
```
- Or we could copy individual files and send them to teammates?
```
core_ui.js
core_ui2.js
core_ui3.js
```

<h3 class="fragment">That sounds tedious...</h3>

Note: Off to a good start


<img src="images/gitLogo.jpg" height="400">


## What is Git?
```
GIT(1)                            Git Manual                            GIT(1)

NAME
       git - the stupid content tracker
```

- distributed version control system
- allows you to work off-line
- provides a collaboration framework


## Linus 2007 git overview
![Linus the value of distribution ](images/LinusViewDVCS.png)
</br>
<small>Source: <a href="https://www.youtube.com/watch?v=4XpnKHJAok8#t=819">Linus 2007 Git Introduction</a></small>
Note: Using CVCS penalizes you from committing and branching since it is so expensive.  This causes developers to have very large commits.


## Get Git Help
<pre><code>
#git [command] --help or man git
$ git diff --help
$ man git
# Then use / to search for --ca
</code></pre>


### Here we go!
<iframe src="https://giphy.com/embed/9UCStxAde7lK?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- RollAndSlide-XGHCQGcfyl6lW -->
<!-- penguinSlide_hereWeGo-9UCStxAde7lK -->


## Centralized VCS
![](images/CentralizedVCS.png)
</br>
<small>Source: <a href="https://betterexplained.com/articles/intro-to-distributed-version-control-illustrated/">Illustrated Distributed Version Control</a></small>


## Distributed VCS
![](images/DistributedVCD.png)
<small>Source: <a href="https://betterexplained.com/articles/intro-to-distributed-version-control-illustrated/">Illustrated Distributed Version Control</a></small>
Note: Every copy of a git branch becomes it's own branch when it falls off line or out of sync with origin. Git has a built in check for disk / file corruption since files are tracked using a hash.

---
### Setting up our <u>local</u> repository.
<p class="fragment" align="left">
1. Create a folder to store the project.</br>
&emsp;&emsp;`mkdir <folder>`</br>
&emsp;&emsp;`cd <folder>`
</p>

<p class="fragment" align="left">
2. Verify the folder is empty.<br/>
&emsp;&emsp;`ls -a`
</p>

<p class="fragment" align="left">
3. Initialize the git repository to track all changes.<br/>
&emsp;&emsp;`git init`
</p>

<p class="fragment" align="left">
4. Verify that the repository has been made by exploring the .git folder.<br/>
&emsp;&emsp;`ls -al .git`
</p>
<aside class="notes">
<li>To tell finder to show all hidden files and folders, use `defaults write com.apple.finder AppleShowAllFiles YES` and relaunch finder.</li>
<li>Git stores information about your project in the `.git` subfolder. This hidden .git folder in the root of your project is the git repository and keeps track of all versions of your files over time.</li>
<li>You can revert to any historic state of the files.</li>
<li>If you delete the .git folder... the only version will be the latest version as the files currently exist (the history will be wiped)</li>
</aside>


### Project Inspection: Changes and history
<p class="fragment" align="left">
1. Check the current status.<br/>
&emsp;&emsp;`git status`
</p>

<p class="fragment" align="left">
2. View previous commits.<br/>
&emsp;&emsp;`git log`
</p>

<br/>
<h3 class="fragment">Time to add some content...</h3>


### Project Update: Add a file
<p class="fragment" align="left">
1. Add a `README`.<br/>
&emsp;&emsp;`echo "# MyHackathonProject" >> README.md`<br/>
</p>

<p class="fragment" align="left">
2. Verify that it is [untracked](https://rogerdudler.github.io/git-guide/#workflow) and in the <u>working index</u>.<br/>
&emsp;&emsp;`git status`
</p>

<p class="fragment" align="left">
3. Add it to the <u>staging index</u>.<br/>
&emsp;&emsp;`git add README.md`
</p>

<p class="fragment" align="left">
4. Verify that it is now being tracked and in the <u>staging index</u>.<br/>
&emsp;&emsp;`git status`
</p>

<p class="fragment" align="left">
5. Visualize the staging vs working trees in `git gui`.<br/>
&emsp;&emsp;`git gui`
</p>


### Project Progress: first commit
<p class="fragment" align="left">
1. Commit the new file to the repository.<br/>
&emsp;&emsp;`git commit -m "Add the README"`
</p>

<p class="fragment" align="left">
2. Verify that the staging index is clean.<br/>
&emsp;&emsp;`git status`
</p>

<p class="fragment" align="left">
3. Look at the logs (there should now be 1 entry).<br/>
&emsp;&emsp;`git log`<br/>
&emsp;&emsp;`git log --oneline`<br/>
&emsp;&emsp;`git log -n 3`
</p>

<aside class="notes">
<p>
Note: When creating a new file or updating existing file and saving those changes, it will create a commit object
</p>
</aside>


### Project Progress: Viewing changes
<p class="fragment" align="left"><br/>
1.  Make some changes to the file<br/>
&emsp;&emsp;`echo 'adding a simple change' >> README.md`
</p>

<p class="fragment" align="left"><br/>
2. View the changes you made to the README file.<br/>
&emsp;&emsp;`git diff HEAD README.md`
</p>

<aside class="notes">
<li>For many git commands you can pass the option `--no-pager` to disable less-style viewing and print all contents</li>
<li>Compare <u>**git diff**</u> to <u>**git diff --staged**</u> by making more changes to the README.</li>
<li>Also compare these in the GUI (and undesired tmp folder)</li>
</aside>


### What does the commit object hold?
- reference to parent commit, if any
- tree - set of files conveying current state of the project
- author info, commiter info, commit message, etc.
Commit object is uniquely identified by a 40-character SHA1 hash


### Commit Object
![](https://git-scm.com/figures/18333fig0301-tn.png)

```
git cat-file -p master
git cat-file -p a7ba36a62d8d8a40d4d9bc4386cc1ae174aff555
git cat-file -p cfcae178cfcf1948c2aca252ebed8146c8aada4f
```


## Edit / Stage / Commit
<img src="images/gitStages.png" height="300px">
<p>
Note: What you are actually staging is a snapshot.  With every change you need to re-add it or stage it using git add.
</p>


### Key Git Concepts - Checkpoint 1
- Staging Area / Working Copy
- Commit Object
- .git repository
- Some initial commands (init, status, log, add, commit)


### Here we go now
<iframe src="https://giphy.com/embed/XGHCQGcfyl6lW?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- RollAndSlide-XGHCQGcfyl6lW -->
<!-- penguinSlide_hereWeGo-9UCStxAde7lK -->

---
## Key Git Concepts
- Local vs Remote
- Branches
- Stashing
- Usage Patterns
Note: Are git and github the same?


![](images/git_local_remote.png)


## Freedom and safety
#### Branches


### Branching
<p class="fragment" align="left">
1. List existing branches.<br/>
&emsp;&emsp;`git branch`
</p>

<p class="fragment" align="left">
2. Create a new branch and list again.<br/>
&emsp;&emsp;`git checkout -b mynewfeature`<br/>
&emsp;&emsp;`git branch`
</p>

<p class="fragment" align="left">
3. Switch branches and delete a branch.<br/>
&emsp;&emsp;`git checkout master`<br/>
&emsp;&emsp;`git branch -D mynewfeature`
</p>


### Branches are collections of commit objects
A git repo's default branch is called master
<pre><code>
    (1) -- (2) -- (3)
                   |
                 master
                   |
                  HEAD
</code></pre>
HEAD points to commit (3) on master branch


### Branches let me try new things!!
<iframe src="https://giphy.com/embed/tbAY4hlx9fzjy?hideSocial=true" width="400" height="400" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- Flying?-tbAY4hlx9fzjy -->


### Stashing
<img src="images/gitStash-SourceTree.png">


### Off to a good start
<iframe src="https://giphy.com/embed/l41lIioP4RFRmIVB6?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- dogRunning-afv-funny-fail-lol-l41lIioP4RFRmIVB6 -->


#### Visualize the state of different versions of the project
<img src="images/gitSourceTreeBranches-Small.png">


### Pull Requests
![](https://confluence.atlassian.com/bitbucket/files/304578655/945541427/1/1518542414564/review_process.png)


### Usage Patterns: e.g. Git-flow
<img src="images/gitflow.gif" height="600">


### Standards are important!
<iframe src="https://giphy.com/embed/3SCKnFChtClxK?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- MindyProjectI-HaveStandards-life-up-3SCKnFChtClxK -->

---
# Fork and Pull


<img src="images/socialGit/github-fork.png">


## [Fork Exercise](https://github.com/C1-SoftwareEngineeringSummit/GitExercise)
![](https://www.dalescott.net/wp-content/uploads/2012/09/centralized-github-4.png)

Note: https://github.com/aln787/git-collab/wiki#exercise https://github.com/aln787/GitExercise


### Not so bad!
<iframe src="https://giphy.com/embed/vBVCam8nE7uxy?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- GetTheBabby-vBVCam8nE7uxy -->


## Merge conflicts
While pulling or merging a branch merge conflicts can occur due to conflicting changes

---
## Tidying up


### Why so many commits??
<iframe src="https://giphy.com/embed/lYKvaJ8EQTzCU?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- jon-stewart-why-lYKvaJ8EQTzCU -->


### Rebasing
```
git rebase -i HEAD~3
git rebase -i master
```

### Amending
```
git commit --amend
git commit --amend --author="Your Name <yourEmail@email.com>"
```

### Gitignore
```
/.cache
node_modules
*.pyc
```
- [Gitignore Templates](https://github.com/github/gitignore)


## Break Changes into Smaller Pieces
<pre><code>
#git add --patch [file]
$ git add --patch
#Use s for smaller y, n, ...
</code></pre>


### Much better!!
<iframe src="https://giphy.com/embed/2ur8NS5TYQmK4?hideSocial=true" width="680" height="567" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
<!-- CuddleFest-2ur8NS5TYQmK4 -->


## Tagging
```
git tag v0.3.8
git tag v0.3.8 44a2a4a2bf8b852145a
git push --tags
git push origin v0.3.8
```

### Patching
```
git diff HEAD~1 README.md > diff.patch
git apply diff.patch

curl -O https://github.com/fastlane/fastlane/pull/14695.patch
git apply 14695.patch
```


### Reverting
```
git revert 44a2a4a2b
git revert --hard 44a2a4a2b
git revert HEAD~3
```


### Cherry-picking
```
git cherry-pick 44a2a4a2b
git cherry-pick --no-commit 44a2a4a2b
git cherry-pick -ff 44a2a4a2b
```

---
##Github Tools / Features


## GH-Pages


[![](images/newImages/gh-pagesToHostPresentations.png)](https://aln787.github.io/revealGhPages/#/1/1)

- [Reveal-MD/GH-Pages Overview](https://aln787.github.io/revealGhPages/#/1/1)
Note:Review the vertical section titled 'MAKING CREATING PRESENTATIONS FEEL MORE LIKE PROGRAMING' beginning with the slide 'TURNS THIS'.


## Reveal.js Resources
- [Theme Options](https://lab.hakim.se/reveal-js/?transition=convex#/themes)
- [GUI Editor](https://slides.com/)
- [Project repo and notes on external markdown](https://github.com/aln787/reveal.js#external-markdown)


### Optional Hands-on Exercise 

- [Full Instructions](https://github.com/aln787/revealMD-simpleStarter/blob/gh-pages/README.md#quick-start)
- Overview
  - From public github, fork my repository
  - Update the place holder values
  - Commit the changes
  - View your example presentation


## Aside on Markdown
![](images/newImages/markdownCheatSheet.png)


### Markdown Resources
- [Docs](https://daringfireball.net/projects/markdown/syntax)
- [Great blog post on mastering markdown](https://designshack.net/articles/html/mastering-markdown-30-resources-apps-and-tutorials-to-get-you-started/)


## Wiki


![](images/newImages/gh-Wiki.png)


## Wiki examples
- [Guard](https://github.com/guard/guard/wiki)
- [Titan](https://github.com/thinkaurelius/titan/wiki)
- [SnowPlow](https://github.com/snowplow/snowplow/wiki)
- [Hystrix](https://github.com/Netflix/Hystrix/wiki)
- [d3](https://github.com/mbostock/d3/wiki)
- [Github's list of great wiki's](https://github.com/showcases/projects-with-great-wikis)


## Issues


![](images/newImages/gh_issues.png)
<!-- Add a link to open nucleus issues -->

---
# Tips and Tricks


## [Hub](https://github.com/github/hub)
- Extend git with additional aliases/functions
<pre><code>
hub ci-status
hub pull-request
hub pr checkout
hub pr list
hub-api
</code></pre>


<img src="images/safe.jpg" height="400">


#### If you are ever unsure what to do when using Git, copy your project directory.


## Setting Up SSH Keys
<pre><code>
$ ls -al ~/.ssh
$ ssh-keygen -t rsa -b 4096 -C "youremail@email.com"
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_summit2016
$ cat ~/.ssh/id_summit2016.pub 
</code></pre>
Then add the output of the cat to your list of github ssh keys on the github site.  
<pre><code>$ ssh -T git@github.com</code></pre>
</br>
<a href="https://help.github.com/articles/generating-ssh-keys">Full Set-up details</a>


## Additional Git Commands
<pre><code>
$ git diff HEAD^ --word-diff
$ git config --global help.autocorrect1
$ git config --global color.ui 1
$ git commit --amend -C HEAD
</code></pre>

---
## 3 Things 
- Power / responsibility associated with Git / Github
- Advanced features
- Portable skill, so be come an expert

---
### Thank you!!! 
![](images/newImages/FrozenVictory.jpg)

---
### References
- https://git-scm.com/
- [SO git questions](https://stackoverflow.com/questions/tagged/git)
- https://help.github.com/
- [May 3rd, 2007 - Linus Torvalds Git Talk](https://www.youtube.com/watch?v=4XpnKHJAok8)
- [Great git talk from one of the git scm writers](https://www.youtube.com/watch?v=ZDR433b0HJY)
- [Git History](https://www.atlassian.com/git/articles/10-years-of-git/)
- [Original Presentation](https://github.com/vmaliwal/git-collab)
Note: https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control

---
## Appendix

---
## Additional Git Concepts
- git config
- vim .gitignore
- git diff [ --staged | --cached ]
- git add --patch
- git [command] --help or man git


## Git Config
- git config --list
- git config --global user.name "Your Name"
- git config --global user.email yourEmail@gmail.com
- git config --global push.default simple #remove verbose messaging about the git 2.0 change
- git config --global core.editor "subl -n -w" #editor for commit messages
- git commit -a #will bring up sublimetext so you can enter you commit message


<img src="images/supper-man.jpg" height="200">
<h2><span style="text-transform: lowercase;">.gitignore</span> the unsung hero</h2>
- It is very important to have this file in your project root directory to avoid merge conflicts from auto-generated code from VM, IDE, etc.
- Google for gitignore nodejs/golang/java/android/iOS


## Diff Options
<pre><code>
#git diff [ --staged | --cached ]
$ git status
# At least 1 file is staged
$ git diff --staged
# Reveals the staged changes
$ git reset #to push those changes back to the working copy
</code></pre>

---
## Collaboration
- Distributed version control model to collaborate between multiple developers.

  - Remote repository
  - Pull remote changes
  - Push local changes to remote


![](images/socialGit/bitbucket_github.png)


![](images/socialGit/github.png)


![](images/socialGit/github-branches.png)


![](images/socialGit/github-mybranches.png)


![](images/socialGit/github-PR-collaboration.png)


## Remote repository
- Remote repositories are versions of your project that are hosted on the Internet or network somewhere.
  
  - Create a new remote repository(on github, bitbucket, etc.) and clone to your local machine. Or,
  - Add existing git repo from your local machine to remote


## Multiple Remotes
<pre><code>
origin  https://github.com/aln787/git-collab.git (fetch)
origin  https://github.com/aln787/git-collab.git (push)
14109fd767af:git-collab $ git remote -v
other /git-collab.git (fetch)
other /git-collab.git (push)
origin  https://github.com/aln787/git-collab.git (fetch)
origin  https://github.com/aln787/git-collab.git (push)
</code></pre>


## Create a new remote repo and clone to your local machine
- Create new remote repository on github or bitbucket
<pre><code>$ git clone [git-remote-repo-url].git</code></pre>
- As name suggests <span style="color: #1b91ff">clone</span> command can be used to clone any remote repository 


## Add existing git repo from local machine to remote
Create new repository on <a href="https://help.github.com/articles/creating-a-new-repository/" title="">github</a> or bitbucket
On your local machine..
<pre><code>
$ git remote add origin [git-remote-repo-url].git
$ git push -u origin master
</code></pre>
<p><span style="color: #1b91ff">origin</span> is a remote repository reference that git uses</p>


## Pulling remote changes
<pre><code>
$ git pull [remote-repo-reference] [remote-branch-name]
$ git pull origin master
</code></pre>


## Pushing changes to remote
<pre><code>
$ git push [remote-repo-reference] [remote-branch-name]
$ git push origin master
</code></pre>

---
## Alternatives / Outstanding Issues for designers


## Outstanding Issues
- 100MB file limit
- Git / Git-hub specialty is text or non-binary files
- Git has a bit of a learning curve that scares some people off


## Alternatives


#### [Pixelapse](https://www.pixelapse.com/)
![](images/newImages/pixelapse.png)
- (Y-Combinator project acquired by Drop Box)


#### [Pixelapse - Fast-co article](https://www.fastcodesign.com/3038135/ex-googler-builds-a-github-for-designers/3 )
![](images/newImages/pixelapse2.jpg)


#### [Proofhub](https://www.proofhub.com)
![](images/newImages/proofHub.png)


### Other useful links I came across while creating this presentation
- https://www.freeimages.com/
- https://dribbble.com/
- https://www.google.com/fonts/
- https://www.deviantart.com/

<!-- - https://www.computerworld.com/article/2875451/dropbox-buys-pixelapse-to-add-version-control-for-visual-designers.html
- https://www.lynda.com/GitHub-tutorials/GitHub-Web-Designers/162276-2.html
- https://blog.teamtreehouse.com/git-for-designers-part-1
- https://www.designernews.co/stories/25506-ask-dn-do-you-use-github-for-design-assets
- https://www.quora.com/Is-there-something-like-Github-for-graphic-design
- https://venturebeat.com/2014/06/05/for-designers-version-control-is-a-big-problem-but-github-is-close-to-solving-it/
- https://github.com/blog/392-intro-to-git-for-designers
- https://www.fastcodesign.com/3038135/ex-googler-builds-a-github-for-designers/3 -->
<!-- ![](images/newImages/gh_for_designers.png) -->
