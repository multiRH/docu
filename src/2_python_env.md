# B. How to create a Python environment

### 1. Creation of Python environment

First, download the latest (stable) distribution of [Python](https://www.python.org/downloads/)
Using a terminal (DOS for windows, otherwise just a Linux/Ubuntu terminal), change the directory to the path where the Python executable is (e.g., C:\Python312) and execute the command:

```
python -m venv [PATH]\venv_dl
```

Path is the location where the new environment will be created.

![img1](/src/img/venv/create__venv.png)

### 2. Activation of environment

Using a terminal, locate the path where the new Python environment #venv_dl# is: (e.g., D:\venv_dl). Change to the directory ..\venv_dl\Scripts and execute the command:

```
.\activate.ps1
```

![img2](/src/img/venv/activate__venv.png)

### 3. Installation of pip packages CPU

On the terminal execute the command:

```
pip install -r requirements_cpu.txt
```

![img3](/src/img/venv/pip__venv.png)



### 3. Installation of pip packages CPU

In case you have a GPU on your computer, use requirements_gpu.txt, and execute the command in the terminal:

```
pip install -r requirements_gpu.txt
```


In addition install the torch packages:

```
pip install torchvision torchaudio torch --index-url https://download.pytorch.org/whl/cu118
```

### 4. Launching the Tools

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

### 5. Testing the GPU

Execute the following lines of code either in spyder or in jupyter lab:

```
import torch
import time

start = time.time()
for i in range(100):
    torch.bmm(torch.rand(100,100,100),
              torch.rand(100,100,100))
print("cpu: %f"%(time.time()-start))
start = time.time()
for i in range(100):
    torch.bmm(torch.rand(100,100,100, device="cuda"),
              torch.rand(100,100,100, device="cuda"))
print("gpu: %f"%(time.time()-start))

```


