[home](../README.md)
# Installation Instructions

## Installation from precompiled packages [recommended]
- Download python 3.6>= using [anaconda](https://www.anaconda.com/download/) or [miniconda](https://conda.io/miniconda.html) if you prefer a lighter installation.
- Open a Terminal in OSX or Linux. In Windows you need to open the Anaconda Prompt.
- [Optional] I would highly recommend to create and activate an [enviroment](https://conda.io/docs/user-guide/tasks/manage-environments.html) as:

```bash

conda create -n tierpsy 

conda activate tierpsy #[Windows]
source activate tierpsy #[OSX or Linux]
```
- Finally, donwload the current package Tierpsy Tracker 1.5.1 from conda-forge
```
conda install tierpsy -c conda-forge
```
- After you can start tierpsy tracker by typing:
```bash
tierpsy_gui
``` 
Do not forget to activate the enviroment every time you start a new terminal session.

On OSX the first time `tierpsy_gui` is intialized it will create a file in the Desktop called tierpsy_gui.command. By double-cliking on this file tierpsy can be started without having to open a terminal.

#### Troubleshooting
 - We recommend that you always keep conda updated to the latest version. You can update conda by typing `conda update conda` on a terminal.

- When installing from `conda`, you may get an error while the package `conda-forge::cloudpickle...` is installed, stating that `python3.6` couldn't be found. In this case, make sure to first install python 3.6, and then tierpsy, by executing:
```bash
conda install -c conda-forge python=3.6
conda install -c conda-forge tierpsy
``` 
- It seems that there might be some problems with some `opencv` versions available through `conda`. If you have problems reading video files or encounter error related with `import cv2`, then you can try to install opencv using pip as:
```bash
pip install opencv-python-headless
```
or specify the `opencv` version via:
```bash
conda install opencv=3.4.2 #[tested on MacOS]
```
- In Windows, the default anaconda channel does not have a valid `ffmpeg` version. Activate the tierpsy enviroment and use the conda-forge channel instead as:
```bash
conda install -c conda-forge ffmpeg
```


## Installation from source [for development]
- Download Python >= 3.6 using [anaconda](https://www.anaconda.com/download/) or [miniconda](https://conda.io/miniconda.html).
- Install [git](https://git-scm.com/). [Here](https://gist.github.com/derhuerst/1b15ff4652a867391f03) are some instructions to install it.
- Install a [C compiler compatible with cython](http://cython.readthedocs.io/en/latest/src/quickstart/install.html). In Windows, you can use [Visual C++ 2015 Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/). In OSX, if you install [homebrew](https://brew.sh/) it will setup the C compiler without the need to download XCode from the appstore. 

- Open a Terminal or Anaconda prompt and type:

```bash
git clone https://github.com/Tierpsy/tierpsy-tracker
cd tierpsy-tracker
conda create -n tierpsy
source activate tierpsy
conda install --file requirements.txt
pip install -e .
```

# Batch processing from the command line.
The script `TierpsyTrackerConsole.py` was deprecated in favor of using the command `tierpsy_process`. Type `tierpsy_process -h` for help.

# Tests
After installing and activating the tierpsy environment, you can download the testing raw videos using the command `tierpsy_tests --download_files` on the terminal.  There are six sets of testing raw videos in total in the tests folder namely `GECKO_VIDEOS`,`AVI_VIDEOS`, `MANUAL_FEATS`, `RIG_HDF5_VIDEOS`, `WT2`, `WORM_MOTEL`.

To run the testing scripts, you can type `tierpsy_tests  AVI_VIDEOS`( tierpsy_tests followed by the name of any testing file) on the terminal.

Type `tierpsy_tests -h` for help. 
