# DL with massively parallel acceleration – Course Materials

## 1. Using materials from this repository

### 1. Cloning the repository (first time only)

On the first class, clone the repository:

git clone <REPOSITORY_URL>
cd <REPOSITORY_NAME>

This will create a folder on your computer with the course materials.

---

### 2. Before pulling new updates

Before downloading new materials, **make a copy of your modified notebook**.

The easiest way is to rename your file, for example:

lab01.ipynb → lab01_yourname.ipynb

or create a copy:

cp lab01.ipynb lab01_yourname.ipynb

This ensures your solutions will not be overwritten.

---

### 3. Downloading updates

After making the copy, you can safely update the repository:

git pull

Git will download the latest version of the materials.

---

### Important

Always work on your own copy of the notebook (e.g. `*_yourname.ipynb`).  
Treat the notebooks in the repository as **templates with tasks**.


## 2. Setting Up the Environment

### 1.1. D10-204 room; using existing conda env (with CUDA)
```
source /home/staff/brachwal/public/set_conda.sh
conda activate monai_hface_accelerate
conda list | grep ipykernel
python -m ipykernel install --user --name myenv --display-name "monai_hface_accelerate"   <--- just once!
```
then:
```
jupyter notebook 
```
or
```
code .
```

VS Code helper (if Python interpreter/Kernel is not detected automatically)

- For scripts: ```Ctrl+Shift+P → Python: Select Interpreter → Enter Interpreter Path``` → paste the path:
``` /home/staff/brachwal/public/conda/miniconda3/envs/monai_hface_accelerate/bin/python```
- For notebooks: open ```.ipynb``` → top right Kernel → Select Another Kernel → Enter Interpreter Path → paste the path.
### 1.2. Installation on your own: Miniconda with CUDA 
⚠️ This setup may take ~1 GB of disk space. On university machines with limited home storage, install it only if you really need GPU/CUDA support. On your personal computer - feel free.

#### 1. Install Miniconda silently
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh
bash ~/miniconda.sh -b -p $HOME/miniconda3
rm ~/miniconda.sh
```
> Option 1 - temporary PATH:
Add conda to PATH for this terminal only:
```
export PATH="$HOME/miniconda3/bin:$PATH"
```
> Option 2 – source activate:
Activate base Conda environment, which automatically sets PATH:
source ~/miniconda3/bin/activate

#### 2. Check for NVIDIA GPU & CUDA
```
if command -v nvidia-smi &> /dev/null; then
    echo "NVIDIA GPU detected:"
    nvidia-smi
    CUDA_VERSION=$(nvidia-smi --query-gpu=driver_version --format=csv,noheader)
    echo "CUDA / driver version: $CUDA_VERSION"
```
#### 3. Create ML Course environment
```
conda create -y -n ml_course python=3.12 \
  pytorch torchvision torchaudio cudatoolkit=11.8 \
  jupyter ipykernel matplotlib numpy -c pytorch

```

#### 4. Register Jupyter kernel
```
conda activate ml_course
python -m ipykernel install --user --name ml_course --display-name "ML Course"
```

#### 5. Activate environment
```conda activate ml_course```

> Use this command in every terminal session before running Python scripts or notebooks.
If you used **temporary PATH**, you need to either repeat the export ```PATH=...``` or add it to``` ~/.bashrc``` for permanent access.

> For VS Code / Jupyter Notebook use the same 

### 1.3. Installation on your own with native Python and virtualenv


#### 1. Create and activate a virtual environment

```
python3 -m venv ml_course
source ml_course/bin/activate
```
### 2. Upgrade pip

```
pip install --upgrade pip
```
### 3. Install required packages

```
pip install torch torchvision numpy matplotlib jupyter ipykernel
```

### 4. Register the Jupyter kernel

```
python -m ipykernel install --user --name ml_course --display-name "ML Course"
```

### 5. Activate the environment
```
source ml_course/bin/activate
```
---

## 3. Structure of the Course

- The course is divided into **few main deep learning topics**.  
- The first 1-2 week(s) are reserved for **warm-up, environment setup, and PyTorch basics**.  
- After that we will start **Notebook 1**, the first of main notebooks.  

### Workshop Notebooks
- There will be **few (2-4) main notebooks counted toward your grade** in total.  
- Each notebook contains:
  - A **baseline implementation** for the topic.
  - Several **exploration directions**, each with **two levels**:
    - **Basic** – required for all students.  
    - **Deep** – choose **one favorite direction** to explore in depth.  
- Evaluation will be done through **short discussions** or **presentations**, where you present your findings and conclusions.

---

## 4. Projects
- Work in pairs
- Topics: 
    - Extend workshop work
    - Personal / research ideas
    - Thesis-related components
    - Instructor-proposed topics (if needed)

---

## 5. Working remotely

### Step 1.
``` 
ssh <login>@taurus.fis.agh.edu.pl 
```
### Step 2. 

a) D10-204 check 01 - 18 (at least one of them should work)
```
ssh <login>@stud204-16 
```

b) gpu-hub

```
ssh <login>@gpu-hub
```
⚠️ Skip Step 1. if you are inside AGH network!

#### Using classic jupyter-notebook (browser version)

1. Start Jupyter Notebook (no browser):

        jupyter notebook --no-browser --port=8888

2. Copy the URL with the token from the output.


3. Create SSH tunnel (run locally):

        ssh -L 8888:localhost:8888 username@server_ip

4. Open in browser:

      http://localhost:8888

4. Paste the token to log in.
5. Stop with `Ctrl+C`

---
## 5. Application for accounts on 4-gpu server & AGH Google accounts

https://forms.office.com/e/Kp2dBAy0Wr

---
