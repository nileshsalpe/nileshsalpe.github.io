# mac-setup

List of  essential softwares for development on new mac book.

## Create bash profile file

```
touch ~/.bash_profile

```
You can add aliases, path in this file 

```
 source ~/.bash_profile
 
```


## List of essential softwares

* #### [HomeBrew](https://brew.sh/)

**Homebrew** is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system and Linux. 

Install using following command

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* #### [iTerm](https://www.iterm2.com/)

**iTerm2**  is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.12 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

```
brew cask install iterm2
```

* #### [Tree](https://rschu.me/list-a-directory-with-tree-command-on-mac-os-x-3b2d4c4a4827)
Tree command equivalent of linux is availble in Mac OS. It shows tree structure of directory.
```
brew install tree
```

```
brew install vim
```

```
brew install git
git --version
git config --global user.name "Your Name Here"
git config --global user.email "your_email@youremail.com"
```
Git ignore template for java projects.

[Sublime Text](https://www.sublimetext.com/3)

### Github Mac client

### Github pages

### Docker

https://docs.docker.com/docker-for-mac/install/

### Java

Install [Java ](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

#### Install Maven 

```

curl https://archive.apache.org/dist/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.tar.gz -o /Downloads/apache-maven-3.6.2-bin.tar.gz
tar -xvf ~/Downloads/apache-maven-3.6.3-bin.tar.gz -C ~/Downloads/
sudo mv ~/Downloads/apache-maven-3.6.3 /Library/apache-maven-3.6.3
 
 vi .bash_profile 
 
export MAVEN_HOME=/Library/apache-maven-3.6.3
export PATH=$MAVEN_HOME/bin:$PATH

```


[https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/)
[https://code.visualstudio.com](https://code.visualstudio.com)


### Pyhton 

Check if exists  python3

```
python3 --version 
```

Install [Install python 3](https://docs.python-guide.org/starting/install3/osx/)


### IDEs

All Languages (Java/Python/JS/Golang)

- [https://code.visualstudio.com](https://code.visualstudio.com)

For Python 
- Set up sublime for Python/Java Script
- [https://www.jetbrains.com/pycharm/](https://www.jetbrains.com/pycharm/)

For Java 
- [Intellij](https://www.jetbrains.com/idea/download/#section=mac)

### Golang
[https://code.visualstudio.com](https://code.visualstudio.com)
[https://www.jetbrains.com/go/](https://www.jetbrains.com/go/)


### Groovy
[https://code.visualstudio.com](https://code.visualstudio.com)

### Scala 

### Node JS
[https://code.visualstudio.com](https://code.visualstudio.com)




