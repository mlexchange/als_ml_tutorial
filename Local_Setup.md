# Local Setup for use of the tutorial notebooks in JupyterLab

This document gives a brief overview on the process of 
creating a virtual Python environment, 
activating it, 
installing required packages within the newly created environment, 
and registering the environment as a new kernel for use in JupyterLab.

# Prerequisites

Before getting started, your device should be prepared with:

- an installation of Python 3,
- the tutorial notebooks, and
- the data used in the tutorial.

## Python installation
It is likely your device already has Python installed even if you have not installed Python yourself. See the [Python installation instructions](https://wiki.python.org/moin/BeginnersGuide/Download) for details on how to test if you have Python installed and how to install it.

## Download the tutorial materials
You can either download the tutorial materials as a .zip file from the [Github repository](https://github.com/mlexchange/als_ml_tutorial) and unzip the downloaded file in a folder of your choosing or clone the repository with git. 

For a manual download navigate to [https://github.com/mlexchange/als_ml_tutorial](https://github.com/mlexchange/als_ml_tutorial) in a browser, click on the green *Code* button &rarr; Select *Download zip*)

For retrieving the materials with git, open a terminal, navigate to a folder of your choosing and use the `git clone` command:

```bash
git clone https://github.com/mlexchange/als_ml_tutorial
```

## Download the data
- Download the file [`data_64x64_400.zip`](https://drive.google.com/uc?id=1RTObsZOHLS4RUnwCegoxXD5EktvrSeI5) and unzip it in the same folder (`als_ml_tutorial`) as the tutorial materials.

# Step 1: Create a Virtual Environment

Open your terminal and navigate to the directory where the tutorial materials are located (`cd als_ml_tutorial`). 
The following command creates a new virtual environment called `als-ml-tutorial-env`:

```bash
python3 -m venv als-ml-tutorial-env
```

# Step 2: Activate the Virtual Environment

This environment now needs to be activated to ensure all subsequent steps are executed *within* the environment. The exact command depends on the operating system

On Linux or macOS use:
```bash
source als-ml-tutorial-env/bin/activate
```
On Windows use:
```bash
als-ml-tutorial-env\Scripts\activate
```

After activating the virtual environment, your terminal prompt should change to reflect the environment has been acticated:

```bash
(als-ml-tutorial-env) $
```

# Step 3: Install the required Python packages

Use the package manager `pip` to install the Python packages for this tutorial:

```bash
pip install -r requirements.txt
```

# Step 4: Register your environment as a new Jupyter kernel

To be able to use these packages and our newly created environment, we need to register the environment as a new kernel:

```bash
python3 -m ipykernel install --user --name=als-ml-tutorial-kernel
```

# Step 5: Open Jupyterlab

```bash
als-ml-tutorial-env/bin/jupyter lab
```

You can now select any of the tutorial noteboks in the folder view. To execute the notebooks, make sure the kernel (on the top right) is set to `als-ml-tutorial-kernel`