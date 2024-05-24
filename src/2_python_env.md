# 2. How to create a Python environment

### 1. Creation of Python environment

First, download the latest (stable) distribution of [Python](https://www.python.org/downloads/)
Using a terminal (DOS for windows, otherwise just a Linux/Ubuntu terminal), change the directory to the path where the Python executable is (e.g., C:\Python312) and execute the command:

```
python -m venv [PATH]\venv_dl
```

Path is the location where the new environment will be created.

![img1](/src/img/venv/create__venv.png)

### 2. Installation of pip packages

Using a terminal, locate the path where the new Python environment #venv_dl# is: (e.g., D:\venv_dl). Change to the directory ..\venv_dl\Scripts and execute the command:

```
.\activate.ps1
```

![img2](/src/img/venv/activate__venv.png)

### 3. Installation of pip packages

On the terminal execute the command:

```
pip install -r requirements_cpu.txt
```

in case you have a GPU on your computer, use requirements_gpu.txt

![img3](/src/img/venv/pip__venv.png)

To launch Spyder execute in the terminal the command:

```
spyder
```

To launch Jupyter Lab execute in the terminal the command:

```
jupyter lab
```

To launch mlflow execute in the terminal the command:

```
mlflow ui
```

![img4](/src/img/venv/spyder_jupyter_mlflow.png)
