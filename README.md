## GIT - homework 1 - XML   
This is a part of GIT homework 1. To see all the GIT homeworks, click [here](https://github.com/ida-que/GIT-homeworks).</br>
_Note: To work with GIT repos, I used some of these necessary tools:_
- _a GitHub account_
- _GitBash (for Windows) to write commands_
- _Git installed to operate Git repos_
- _folders for keeping local repos (I used `mkdir` Bash command to create those in terminal)_

### Contents
1. [Create a remote repository called _XML_.]()
2. [Clone the XML repository to the local computer.]()
3. [Create a _new.xml_ file inside the local XML.]()
4. [Add the file to Git.]()
5. [Commit the file.]()
6. [Send the file to a remote GitHub repository.]()
7. [Edit the content of the file _new.xml_ - write information about yourself (full name, age, number of pets, future desired salary). Write everything in XML format.]()
8. [Send the changes to a remote repository.]()
9. [Create a _preferences.xml_ file.]()
10. [In the _preferences.xml_ file, add information about your preferences (favorite movie, favorite series, favorite food, favorite time of year, country you would like to visit) in XML format.]()
11. [Create a _skills.xml_ file, add information about skills that are going to be learned at the course in XML format.]()
12. [Send two files at once to remote repository.]()
13. [Create the _bug_report.xml_ file on the web interface.]()
14. [Save the changes at the web interface.]()
15. [At the web interface, modify the _bug_report.xml_ file and add the bug report in XML format.]()
16. [Save the changes at the web interface.]()
17. [Synchronize remote and local XML repository.]()

## STEPS
#### 1. Create a remote repository called _XML_.
To make this first step, I go to my GitHub account, then go to the _"Repositories"_ tab and click on _"New"_ button. Then add a name and click on _"Create repository"_.
#### 2. Clone the XML repository to the local computer.
To clone the repo XML, firstly I don't exit GitHub and copy the link to this repo to use with a command in terminal.</br>
Then I go to GitBash CLI and create a folder e.g. _GIT_ with `mkdir` command, this is where I'm going to clone the repo.</br>
I clone the remote repo to the working directory by typing a command and pasting the link:
```
$ git clone https://github.com/ida-que/XML.git
```
Now, we have a repository cloned locally and can add files.
_Note: this command creates a separate directory e.g. XML where keeps the local repo._ To go to XML folder with cloned repo, use `cd XML` command.
#### 3. Create a _new.xml_ file inside the local XML.
Just let's type in CLI:
```
$ touch new.xml
```
#### 4. Add the file to Git.
To prepare the content for the commit to the remote repo, I typed:
```
$ git add new.xml
```
and checked if the changes are added with a `git status` command. The terminal showed as follows:
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   new.xml

```
_Note: you can use either `git add .` (adding all the files) or `git add filename` (adding this particular file) here._
#### 5. Commit the file.
The next step is a commit. A commit is a kind of snapshot of changes, it has a special identifier, so you can come back and see.
When you commit (`git commit`), you also add a message that helps you to summarize the changes we added (`-m`).
```
$ git commit -m "blank new.xml added"
```
```
[main (root-commit) a770164] blank new.xml added               # here we can see the commit identifier a770164
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.xml
```
#### 5a. Modifying commit message.
What if we want to modify that _"blank new.xml added"_ message? Well, let's try to do it this way:
```
$ git commit --amend                                            # here, terminal opens vim editor, and you can modify your message
[main 96880c0] blank new.xml added                              # as we see in this line, the commit identifier also changed to 96880c0
 Date: Sun Apr 30 19:49:05 2023 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.xml

```
#### 6. Send the file to a remote GitHub repository.
We use `git push` command for sending the commit to the remote repo at GitHub and get the answer that the process is successfully done:
```
$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 224 bytes | 224.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/XML.git
 * [new branch]      main -> main
```
#### 7. Edit the content of the file _new.xml_ - write information about yourself (full name, age, number of pets, future desired salary). Write everything in XML format.
I am using here the `vim new.xml` to open vim editor and write the info e.g.:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<idaQue>
    <fullName>Ida Que</fullName>
    <age>25</age>
    <numberOfPets>0</numberOfPets>
    <futureDesiredSalary>10.000</futureDesiredSalary>
</idaQue>
```
_Note: The first line from the file above is called the **XML prolog**. Also, [here](https://google.github.io/styleguide/xmlstyle.html) you can find more about XML format styles._
#### 7a. Restoring previous version of the file.
Our file was empty. But what if we want to restore changes that we had before? It is possible:
```
$ git restore new.xml
```
After execution of this command, the file has state of our last commit. However, finally I want the info to be provided, so pasted the text one more time.
#### 8. Send the changes to a remote repository.
```
$ git add .                                                         # adding the changes to Git, preparing for the commit
```
Quickly checking this out:
```
$ git status
On branch main      
Your branch is up to date with 'origin/main'.               

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   new.xml                                        # notification about file modification
```
Then:
```
$ git commit -m "added information about myself to new.xml"        # committing with an appropriate message

[main c465ba7] added information about myself to new.xml
 1 file changed, 7 insertions(+)
```
Finally, uploading the changes to the remote repo:
```
$ git push                                                  

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 404 bytes | 202.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/XML.git
   96880c0..c465ba7  main -> main
```
#### 9. Create a _preferences.xml_ file.
As we put information in the file in the very next step, I straightly used `vim` to create the file and add info:
```
$ vim preferences.xml
```
Then press `Insert` to be able to modify our new xml.
#### 10. In the _preferences.xml_ file, add information about your preferences (favorite movie, favorite series, favorite food, favorite season, country you would like to visit) in XML format.
Here, we use _vim_ editor to type into a file:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<idaQuePreferences>
    <favouriteMovie>Inception</favouriteMovie>
    <favouriteSeries>Shameless</favouriteSeries>
    <favouriteFood>shakshuka</favouriteFood>
    <favouriteSeason>spring</favouriteSeason>
    <countryIWouldLikeToVisit>China</countryIWouldLikeToVisit>
</idaQuePreferences>
```
Then press `Esc` and `:wq` to save and quit.
#### 11. Create a _skills.xml_ file, add information about skills that are going to be learned at the course in XML format.
Let's try a `cat >` command here as an option to create a file and type info right in the terminal:
```
$ cat > skills.xml
```
```xml
<?xml version="1.0" encoding="UTF-8"?>
<courseSkills>
    <skill>Writing Bash commands and simple scripts</skill>
    <skill>Working with GitHub and Git</skill>
    <skill>Understanding the most popular test design techniques</skill>
    <skill>Understanding client-server architecture</skill>
    <skill>API testing with Postman</skill>
    <skill>Writing test documentation</skill>
    <skill>Web and mobile testing with devtools</skill>
    <skill>iOS/Android traffic monitoring with Charles and Fiddler</skill>
    <skill>SQL basics</skill>
    <skill>JMeter load testing basics</skill>
    <skill>Developing simple mobile apps with Xcode/Android Studio</skill>
</courseSkills>
```
After typing the last line, press `Enter` and `Ctrl+C` to save and quit.</br>
_Note: I would recommend using `spaces` not `Tabs` here to feel more confident with managing the file structure._
#### 12. Send two files at once to the remote repository.
As I already new some bash hacks, I can probably add, commit and push these new 2 files by one-line command using `&&` operator.</br>
_Note: `&&` operator means "if the previous command has been successfully executed"._
```
$ git add . && git commit -m "adding preferences.xml and skills.xml" && git push
```
As a result, we have all three commands successfully executed.
```
[main 343cd47] adding preferences.xml and skills.xml
 2 files changed, 22 insertions(+)
 create mode 100644 preferences.xml
 create mode 100644 skills.xml
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 825 bytes | 412.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ida-que/XML.git
   c465ba7..343cd47  main -> main
```
#### 13. Create the _bug_report.xml_ file at the web interface.
This step means going to GitHub page and creating the file from there. Just add a new xml file and write into the text editor:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<bugReportExample>
  <id>170</id>
  <severity>minor</severity>
  <priority>low</priority>
  <title>Space character in img src URL of the 'CFD vs Aktien' image of [CFD vs share trading] sidebar item</title>
  <environment>
    <value>Windows 10 Chrome 112</value>
    <value>iPhone 11 16.4.1 Safari</value>
  </environment>
  <stepsToReproduce>
    <step>1. Navigate to capital.com</step>
    <step>2. Choose language DE</step>
    <step>3. Hover on menu section [Schulung] (EN: Education)</step
    <step>4. Click menu item [CFD-Handel] (EN: CFD trading)</step>
    <step>5. Click sidebar item [Was ist der Unterschied zwischen Aktien und CFD?] (EN: CFDs vs share trading)</step>
    <step>6. Open devtools and look at the img src href</step>
  </stepsToReproduce>
  <precondition>none</precondition>
  <expectedResult>img src URL has no spaces so the image is displayed on the webpage</expectedResult>
  <actualResult>img src URL has a space so the image is not displayed on the webpage</actualResult>
  <attachment>(URL to the video)</attachment>
  <postcondition>none</postcondition>
  <reproducibility>n/a</reproducibility>
  <author>ida-que</author>
</bugReportExample>
```
#### 14. Save the changes at the web interface.
Under the editor section, we have a section called _"Commit new file"_ with a message and description input fields. I left the first input field as is, as it was proposed to have a message _"Create bug_report.xml"._</br>
I also left the second input field empty as it is an optional extended description.</br>
Finally, there are radio buttons representing options of committing the file to `main` branch directly or creating a new separate branch for the XML repo. I chose committing to the `main` branch.</br>
Then, just send this commit, and we're done :smile:
#### 15. At the web interface, modify the _bug_report.xml_ file and add the bug report in XML format.
What if I see that I provided an incorrect ID for this bug report? We can go to the file at GitHub and modify by opening the file and clicking on pencil icon :pencil::
```xml
<id>171</id>
```
#### 16. Save the changes at the web interface.
Here, we do similar to the step 14. Commit message is also proposed: _"Update bug_report.xml"_, let it be.
#### 17. Synchronize remote and local XML repository.
For this step, we go back to our terminal to type a `git pull` command. We mention which exact branch we want to be pulled to the local XML repo:
```
$ git pull origin main
```
As a result, we have command successfully executed, with a notification that our new file _bug_report.xml_ has been added.
```
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 1.89 KiB | 36.00 KiB/s, done.
From https://github.com/ida-que/XML
 * branch            main       -> FETCH_HEAD
   343cd47..beb0caf  main       -> origin/main
Updating 343cd47..beb0caf
Fast-forward
 bug_report.xml | 26 ++++++++++++++++++++++++++
 1 file changed, 26 insertions(+)
 create mode 100644 bug_report.xml

```
_Note: we can also make sure the file is added by using `ls` command (see the list of the files in working directory), or we can straightly open the new file by `cat` command.