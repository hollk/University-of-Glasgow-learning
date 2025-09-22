<h1 align="center">
Conda Practical Exercises
</h1>
[TOC]
## Exercise 1: Setting Up Conda

Task: Install Miniconda or Anaconda on your system.

Task: Verify the installation

```shell
conda –version
```

![image-20250922181203464](./assets/image-20250922181203464.png)

Task: Update Conda to the latest version

```shell
conda update conda
```

![image-20250922182049819](./assets/image-20250922182049819.png)

![image-20250922182132891](./assets/image-20250922182132891.png)

## Exercise 2: Creating and Activating an Environment

Task: Create a new environment named data_science with Python 3.8

```shell
conda create --name data_science python=3.8
```

![image-20250922190405065](./assets/image-20250922190405065.png)

Task: Activate the data_science environment

```shell
conda activate data_science
```

![image-20250922190726705](./assets/image-20250922190726705.png)

Task: Deactivate the environment.

```shell
conda deactivate
```

![image-20250922190804596](./assets/image-20250922190804596.png)

## Exercise 3: Installing and Managing Packages

Task: Install the following packages in your data_science environment: NumPy, Pandas, and Matplotlib.

```shell
conda install numpy pandas matplotlib
```

![image-20250922193524917](./assets/image-20250922193524917.png)

Task: Update the Pandas package to the latest version

```shell
conda update pandas
```

![image-20250922193701701](./assets/image-20250922193701701.png)

Task: Remove the Matplotlib package

```shell
conda remove matplotlib
```

![image-20250922193959387](./assets/image-20250922193959387.png)

## Exercise 4: Exporting and Sharing Environments

Task: Export your data_science environment to a YAML file named data_science_env.yml.

```shell
conda env export > data_science_env.yml
```

![image-20250922201403365](./assets/image-20250922201403365.png)

Task: Create a new environment from the exported YAML file

```shell
conda env create -f data_science_env.yml
```

![image-20250922201500771](./assets/image-20250922201500771.png)

![image-20250922201524367](./assets/image-20250922201524367.png)

![image-20250922201605395](./assets/image-20250922201605395.png)

![image-20250922201625279](./assets/image-20250922201625279.png)

