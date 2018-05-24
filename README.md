# One-Word-Apt
### Bash autocomplete for install/uninstall alias for apt package manager
(For Easily installing/removing packages on Debian based Linux (like Ubuntu) ) 

#### Installation
Firstly, add alias for installing and removing packages into your *.bash_alias* file.

```bash
#Add alias to file
echo "alias ai='sudo apt install'" >> ~/.bash_alias
echo "alias ar='sudo apt remove'" >> ~/.bash_alias
```

Then copy the files named 'get' and 'remove' into */etc/bash_completion.d* folder. (You can also copy it to */usr/share/bash-completion/completions/* folder.) Chmod these files to \[-rw-r--r--\] (644) (which is usually the default for most system files)

Assuming that Working Directory of your terminal is the root folder of this cloned repository, the following should word fine -

```bash
#Copy Files
sudo cp ai /etc/bash_completion.d/
sudo cp ar /etc/bash_completion.d/
```
```bash
#Set Permissions
sudo chmod 644 /etc/bash_completion.d/ai
sudo chmod 644 /etc/bash_completion.d/ar
```

Now, open up a terminal and test this command (just download any package and then try to remove it)

#### Usage

Just use it as an abbrevation of normal apt commands.

```bash
ai PACKAGE_NAME #install a package
#just like sudo apt install PACKAGE_NAME
ar PACKAGE_NAME #remove a package
```

###### This can also use all arguments that are supported by *apt* (like -d,-s,-t,--purge).
