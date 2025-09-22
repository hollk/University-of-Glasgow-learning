# 1. Using Git and gitHb
### 1.1 Initialise a new repository locally

Create a  new folder and initialize this folder with git

```shell
mkdir ~/github
cd ~/github
git init
```

![image-20250922093501216](./using_git_and_github.assets/image-20250922093501216.png)

After initalization, a hidden .git folder will be created in the current directory

![image-20250922093654562](./using_git_and_github.assets/image-20250922093654562.png)

### 1.2 Create a new repository on GitHub

Just click according to the steps

![image-20250922101301233](./using_git_and_github.assets/image-20250922101301233.png)

* Choose visibility

Public: anyone can see your repository

Private: only you and collaborators you invite can see it

* Add REDME

A README.md file explains your project

* Add .gitignore 

A .gitignore file tells Git which files not to track

* Add license

A license explains how others can use your code 

### 1.3 Connect the local repository to remote GitHub

```shell
git remote add origin https://github.com/hollk/your_repository_name.git
```

### 1.4 Generating SSH keys for secure communication

* Step 1: Generate an SSH private key and public key on my local

```shell
ssh-keygen -t rsa -b 4096 -C "your_enmail"
```

![image-20250921210531170](./using_git_and_github.assets/image-20250921210531170.png)

The private key and public key are saved in ~/.ssh/

![image-20250921210706103](./using_git_and_github.assets/image-20250921210706103.png)

* Step 2: upload public key content

```shell
cat ./id_rsa.pub
```

![image-20250921212402559](./using_git_and_github.assets/image-20250921212402559.png)

Copy the content of public key and go to github website.

The click sequence is: Avatar - Setting - SSH and GPC keys - New SSH key - Paste the public key information into the input box.

![image-20250921212045153](./using_git_and_github.assets/image-20250921212045153.png)

If the upload is successful, the web interface will look like this:

![image-20250921212721598](./using_git_and_github.assets/image-20250921212721598.png)

* Step 3: Check whether the SSH connection is successful.

Start the SSH proxy service

```ssh
ssh-agent -s
```

![image-20250921213141384](./using_git_and_github.assets/image-20250921213141384.png)

Add the private key to the SSH proxy

```shell
ssh-add ~/.ssh/id_rsa
```

![image-20250921213349391](./using_git_and_github.assets/image-20250921213349391.png)

Tests whether SSH key is correctly set up with GitHub

```shell
ssh -T  git@github
```

![image-20250921213705393](./using_git_and_github.assets/image-20250921213705393.png)

### 1.5 Push the initial commit to github







