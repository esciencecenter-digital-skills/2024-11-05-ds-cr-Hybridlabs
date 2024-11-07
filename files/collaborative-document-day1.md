![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2024-11-05 HybridLabs - Good Practices in Research Software Development - **Day 1**

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](https://edu.nl/3wx8g)

Collaborative Document day 1: [link](https://edu.nl/3wx8g)

Collaborative Document day 2: [link](https://edu.nl/n43fa)


##  🫱🏽‍🫲🏻 Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, just raise your hand.

If you need help from a helper, place a pink post-it note on your laptop lid. A helper will come to assist you as soon as possible.

## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2024-11-05-ds-cr-Hybridlabs/)

🛠 Setup

[link](https://esciencecenter-digital-skills.github.io/2024-11-05-ds-cr-Hybridlabs/#setup)

## 👩‍🏫👩‍💻🎓 Instructors

Francesco Nattino, Djura Smits

## 🧑‍🙋 Helpers

Sarah Alidoost, Thijs van Lankveld  

## 🗓️ Agenda


| Time  | Topic                             |
|-------|-----------------------------------|
| 14:00 | Workshop Introduction             |
| 14:15 | Version control with Git          |
| 15:30 | *Afternoon break*                 |
| 15:45 | Collaboration with Git and Github |
| 17:00 | END                               |


## 🏢 Location logistics
* Coffee and toilets are in the hallway, just outside of the classroom.
* If you leave the building, 
  be sure to be accompanied by someone from the escience center to let you back in through the groundfloor door
* For access to this floor you might need to ring the doorbell so someone can let you in
* In case of an emergency, you can exit our floor using the main staircase.
  Or follow green light signs at the ceiling to the emergency staircase.
* **Wifi**: Eduroam should work. Otherwise use the 'matrixbuilding' network, password should be printed out and available somewhere in the room.

## 🎓 Certificate of attendance

If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl.
Please request your certificate within 8 months after the workshop, as we will delete all personal identifyable information after this period.

## 🔧 Exercises

## 🧠 Collaborative Notes

Test whether git works and you can reach your GitHub account.
```(bash)
git --version
ssh -T git@github.com
```

Setup git configuration.
```(bash)
git config -l
git config --global user.name "[your name]"
git config --global user.email "[your email]"
```

Create a new (local) repository.
```(bash)
cd Desktop/
mkdir planets
cd planets/
git init
```
> Note that creating this repository does not change anything else in the local directory.

Check that the .git directory was created.
```(bash)
ls -a
```
> this should show the `.git/` directory.

Change the default name of the main branch.
```(bash)
git switch -c "main"
```

Check the current status of the repository.
```(bash)
git status
```
> This should tell us on which branch we are and whether there are any changes ready to commit.

Create a new file.
```(bash)
nano mars.txt
```

Write some lines into the new file.
`Ctrl-O` to save the file.
`Ctrl-X` to close nano.

Check the current status of the repository.
```(bash)
git status
```
> This should tell us that there is a new file and that this file is not currently tracked.
 
Start tracking the new file.
```(bash)
git add mars.txt
```

Check the current status of the repository.
```(bash)
git status
```
> The new file is now green. 

Commit the staging area.
```(bash)
git commit -m "add note on mars"
```
> git tells us that the file is added to the repository.
 
Commit messages should be short (50 characters), imperative style, decriptive (what & why).

``` bash
git status
```
> it should show that nothing is there or to commit now. 

Inspect the history:
```bash
git log
```
> who, when and what are the changes can be seen by this command
> 

Let's add some more changes to the same file (you can use nano or other editor):
```bash
nano mars.txt
```
Add some lines into the file.
`Ctrl-O` to save the file.
`Ctrl-X` to close nano.

and then check the status:
```bash
git status
```
> Again the file is shown in red color, meaning this file has been changed. 

Inspect the changes:
```bash
git diff
```
> this shows the changes with respect to the last commit, green meaning changes are added. if something is removed/deleted, it would be in red color.

Add changes to staging area and commit:
```bash
git add mars.txt
git status
git commit -m "add note on moons"
```

Modify git commit message
```bash
git --amend
```
> this will open an editor to modify the commit message! To exit the editor, press Escp key, type :q or :wq to save changes

if you add another directory like:
```bash
mkdir spaceships
git status
```
> git does not see empty directories
To add/create a file:
```bash
touch spaceships/file.txt
git status
```
> now git says that directory "spaceships" is there, in red color.

To remove the directory:
```bash
rm -r spaceships
```

Let's add some more changes to file mars.txt (using nano or another editor):
```bash
nano mars.txt
```
Add some lines into the file.
`Ctrl-O` to save the file.
`Ctrl-X` to close nano.

To check the changes with respect to the last commit:
```bash
git diff
```
> it prints the new changes

The last commit is called "HEAD", see changes with respect to the last commit, we can do also:
```bash
git diff HEAD mars.txt
```

Going back in time (one more commit back):
```bash
git diff HEAD~1 mars.txt
```

You can use any other numbers to go back e.g. HEAD~2, or HEAD~3, ...

There are many options with "git log" command, for example:
```bash
git log --oneline
```
it summarize the log history in one line (shorter commit identifier)

Using git identifier:
```bash
git log
```
Copy one commit identifier and then use it after git diff:
```bash
git diff <commit id>
```
>it shows the changes in that specific commit.

When you use "git status", git shows some useful commands e.g. git add or git restore
```bash
git restore mars.txt
git status
```
> the last changes are discared.
> it is not possible to bring back the changes back at this moment, because we did not add them to the history.

```bash
git restore -s <commit id>
```
> this will bring the file to the status of the file before that commit. 

To go back to the last commit:
```bash
git restore mars.txt
```
> changes are back now.

With these commands, we navigated in history, going back and forth. 

Why to use gitignore:
- to tell git not track some files due to privacy
- some outputs that are not needed to be tracked
- some files in specific format that needs to be ignored

Add some csv files:
```bash
touch a.csv b.csv c.csv
```

```bash
nano .gitignore 
```
> you can add *.csv to the file 

```bash
git status
git add .gitignore
git commit -m "ignore csv files"
git status
```
> all csv files are ignored.

Go to github.com, you profile page. 
We want to create a remote repository:

- Click on "new repository": the ``+`` button next to your profile photo.
- Add a repository name
- Set "Public", others can see the repository
- Lets not add others files for this exercise.
- Click the button "Create repository"

Check the url next to the ssh, copy it.
Back to the terminal, we want to link our local repository with the remote one:
```bash
git remote add origin <paste the url here>
```
To check if it works:
```bash
git remote -v
```
> it shows the url one (fetch) and another (push), different git commands.

Now, we can push the repo and branch "main" to github:
```bash
git push origin main
```
> go back to your repo in the browser, you should see your local changes there.


### For tomorrow
Follow [setup instructions](https://esciencecenter-digital-skills.github.io/2024-11-05-ds-cr-Hybridlabs/#setup)

```bash
conda activate coderefinery
pytest --version
```

## 📚 Resources

How to add SHH key to GitHub account.
```(bash)
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
```

```(bash)
Get-Service ssh-agent | Set-Service -StartupType Automatic -PassThru | Start-Service
```