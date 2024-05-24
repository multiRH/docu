# 1. How to create a Python environment

First install the latest distribution of git: [git](https://git-scm.com/)


### 1. Configuration of SSH keys 

SSH configuration (in the git bash console), and create the keys in the origin pc (win) executing the command in the terminal:

```
$ssh-keygen
```

the terminal shows the output:

```
Enter passphrase:
enter file location: 
/c/Users/username/.ssh/
```

and it creastes the keys: id_rsa and id_rsa.pub

Execute in the terminal:

```
$eval $(ssh-agent)
```

which outputs the agent pid: 

```
Agent pid  2441
```

Execute in the terminal:

```
$ssh-add ~/.ssh/id_rsa
enter passphrase:
```
the terminal shows the output:

```
identity added
```

To add the SSH key to the git platform (e.g., bitbucket), execute the command in the terminal:

```
$ssh -T git@bitbucket.org
```

the terminal shows the output:

```
You can use git to connect to Bitbucket. Shell access is disabled.
```

### 2. Changing the https to ssh in the repo
Change to repo location in the terminal and execute the commands:

```
$git remote -v
```
the terminal shows the output:

```
origin (fetch)
origin (push)
```

Execute the command:

```
$git remote set-url origin git@bitbucket.org:user_name/repo_name.git
```

### 3. Configuring the SSH key in an additional PC
Copy the public ssh key to the location of the folder .ssh, and execute the following commands:

```
$chmod 400 /home/user_name/.ssh/id_rsa
$ssh-add /home/user_name/.ssh/id_rsa
```

### 4. Useful commands for git

To clone a repo:

```
git clone <repo>
```

To check the status of a repo, if there are changes:
```
git status
```

To add changes in a file to the repo:
```
gid add FILE
```

To add all the files that have changes to the repo:
```
git add -A
```

To commit the changes to the repo:
```
git commit -m "commit message"
```

To first pull the actual status of the remote repo, and update the local repo:
```
git pull --rebase origin main
```

To push the commit to the remote repo:
```
git push
```

For more information check the website: [Getting started](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)
