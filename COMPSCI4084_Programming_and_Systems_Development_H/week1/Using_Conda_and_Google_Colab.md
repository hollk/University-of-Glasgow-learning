<h1 align="center">
Using Conda and Google Colab
</h1>

[TOC]

# 1. Setting Up Conda and Creating a New Environment

## 1.1 Setting Up Conda

### 1.1.1 Install Conda

In Moodle, there is a download link for Anaconda3. Just download the installer for your operating system, and once installed, Conda will be available.

![image-20250922181105684](./assets/image-20250922181105684.png)

### 1.1.2 Verify the installation

```shell
conda --version
```

![image-20250922181203464](./assets/image-20250922181203464.png)

The version of Conda downloaded from Anaconda 3 by default is Conda 25.5.1.

### 1.1.3 Update Conda tthe latest version

```shell
conda update conda
```

![image-20250922181350769](./assets/image-20250922181350769.png)

Here it requires running `conda update -n base -c defaults conda`, but after running it, the upgrade still fails. This may be because the defaults channel is not updated in time, so you can use `conda-forge` to update instead:

```shell
conda install -n base -c conda-forge conda
```

![image-20250922181951303](./assets/image-20250922181951303.png)

Rerun the following command:

```shell
conda update -n base -c defaults conda
```

![image-20250922182049819](./assets/image-20250922182049819.png)

Check it, the version has been upgraded from 25.5.1 to 25.7.0.

![image-20250922182132891](./assets/image-20250922182132891.png)

### 1.1.4 Create an environment with a specific Python version

I have to complain a bit: the course PPT here asks to create a Python 4.14 environment, which is an obvious trap. The latest preview version available is only 3.14.

```shell
conda create --name myenv python=3.8
```

![image-20250922182646310](./assets/image-20250922182646310.png)

### 1.1.5 Activate the environment

```shell
conda activate myenv
```

![image-20250922182738985](./assets/image-20250922182738985.png)

If the previous content changes, it means the startup was successful.

### 1.1.6 Deactivate the environment

```shell
conda deactivate
```

![image-20250922182919760](./assets/image-20250922182919760.png)

If the previous content changes, it means the deactivation was successful.

## 1.2 Managing Environments

### 1.2.1 Listing all environments

```shell
conda env list
```

![image-20250922183254965](./assets/image-20250922183254965.png)

![image-20250922190517398](./assets/image-20250922190517398.png)

This is the myenv we just created.

### 1.2.2 Removing an environment

```shell
conda remove --name myenv --all
```

![image-20250922183742661](./assets/image-20250922183742661.png)

Check again to confirm whether it has been successfully deleted.

![image-20250922183751880](./assets/image-20250922183751880.png)

### 1.2.3 Cloning an environment

It should be noted here that if you follow the order in the PPT, you need to recreate myenv. If myenv does not exist, newenv cannot find a source to clone from.

```shell
conda create --name myenv python=3.8
conda create --name newenv --clone myenv
```

![image-20250922184246970](./assets/image-20250922184246970.png)

Check whether it has been created successfully.

![image-20250922184317570](./assets/image-20250922184317570.png)

## 1.3 Installing and Managing Packages

### 1.3.1 Installing a package

```shell
conda install numpy
```

![image-20250922193456768](./assets/image-20250922193456768.png)

### 1.3.2 Updating a package

```shell
conda update numpy
```

![image-20250922193627969](./assets/image-20250922193627969.png)

### 1.3.3 Removing a package

```shell
conda remove numpy
```

![image-20250922193857285](./assets/image-20250922193857285.png)

## 1.4 Exporting and Sharing Environments

### 1.4.1 Exporting an environment ta YAML file

It should be noted here that if the -n parameter is not used to specify the environment, the currently activated environment will be exported by default.

![image-20250922194620063](./assets/image-20250922194620063.png)

If the -n parameter is added, it is not necessary to activate the environment.

![image-20250922195338265](./assets/image-20250922195338265.png)

### 1.4.2 Creating an environment from a YAML file

Previously, the yml file of myenv was exported. Now you can delete the myenv environment and recreate it using the yml file.

![image-20250922200459080](./assets/image-20250922200459080.png)

Check the list.

![image-20250922200517036](./assets/image-20250922200517036.png)

The myenv environment no longer exists.

```shell
conda env create -f environment.yml
```

![image-20250922200731185](./assets/image-20250922200731185.png)

Check the list again.

![image-20250922200753123](./assets/image-20250922200753123.png)

















