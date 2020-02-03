## Notebook
> Programming notes, instructions, commands, snippets etc.

## Table of Contents
1. MongoDB
	* [Install MongoDB As A Service In Windows](#install-mongodb-as-a-service-in-windows)
2. Git
    * [Environment Configurations](#environment-configurations)
    * [Generate SSH Key](#generate-ssh-key)
    * [Repository](#repository)
    * [Manage Branch](#branch)
    * [Manage Tag](#tag)
    * [Log](#log)

## Install MongoDB As A Service In Windows

1. Download MongoDB from [https://www.mongodb.org/](https://www.mongodb.org/)

2. Extract the contents of the zip file into __C:\mongodb__

3. Add MongoDB in windows path. Edit your environment variable. Append this: __C:\mongodb\bin;__

4. Create a configuration file __C:\mongodb\mongod.conf__ and add these lines:

```
dbpath=C:\mongodb\data\db
logpath=C:\mongodb\log\mongo.log
verbose=vvvvv
```
> Note: you have to manually create both __c:\mongodb\data\db__ and __c:\mongodb\log__ directory.

5. Open commad prompt as administrator and run the following commands:

```bash
mongod -f c:\mongodb\mongod.conf
mongod -f c:\mongodb\mongod.conf --install
```

6. Start MongoDB

```bash
net start mongodb
```
> From now on mongodb service will run automatically every time the PC is restarted.

## Environment Configurations

```bash
$ git config --global user.name "<your_name>"
$ git config --global user.email "<your_email>"
$ git config --global core.editor "<e.g vim>"
$ git config --global core.ignorecase false
```

## Generate SSH Key

```bash
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# Copy SSH key into the clipboard
# For Windows: $ clip < ~/.ssh/id_rsa.pub
# For Linux: $ xclip -sel clip < ~/.ssh/id_rsa.pub
# For OSX: $ pbcopy < ~/.ssh/id_rsa.pub
```

## Repository

```bash
# Adding a remote
git remote add origin <remote_url>

#Updating a remote
git remote set-url origin <remote_url>

# Determine the url that a local git repo cloned from
git remote show origin

```

## Branch

```bash
# Create new branch and checkout
git checkout -b <branch_name>

#Delete a branch from local
git branch -d <branch_name>

#Delete a branch from remote origin
git push origin --delete <branch_name>

#Throw away local commits in Git
git reset --hard origin/<branch_name>
```

## Tag

```bash
# Adding & pushing a tag
git tag -a <tag_name> -m "<message>"
git push origin <tag_name>

# Deleting a tag
git tag -d <tag_name>
git push origin :refs/tags/<tag_name>
```

## Log

```bash
# History of a moved file
git log --follow <file_name>

# Show Log Graph
git log --oneline --graph
git reflog
```

## License
<a href="https://opensource.org/licenses/MIT">The MIT License</a> Copyright &copy; 2016 Shibbir Ahmed
