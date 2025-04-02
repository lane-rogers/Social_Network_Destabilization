# Readme for task4 repository 

This code base uses both python and julia. Each have different requirements for set up.


## Repository Setup 

### Setting up Julia

This project requires julia 1.10.4+. To install the correct version of julia, follow the steps at [julialang.org/downloads](https://julialang.org/downloads/#current_stable_release) for your specific system.

We only call julia from python.

**Important Note:** One of the julia packages has python has a dependency which causes an error when loading packages. This error can be **ignored**.


### Setting up Python

We used pyenv for managing different versions of python and venv for our python virtual envrionment.
 
Quick background and useful commands appear at the bottom of this readme.
 
The setup follows reference: https://www.freecodecamp.org/news/manage-multiple-python-versions-and-virtual-environments-venv-pyenv-pyvenv-a29fb00c296f/
 
Steps: 
1. Install python 3.12.0  via pyenv using `pyenv install 3.12.0`)
2. Set pyenv envrionment to python 3.12.0 using  `pyenv local 3.12.0`    
3.  Initialize virtual envrionment in the .venv folder `python3 -m venv .venv`. Now, in the new folder `.venv/bin` should be a copy of python 3.12.0
 
    Note that the `.venv` folder is gitignored and should not ship with the repo.

4. Start virtual envrionment: `source .venv/bin/activate`
 
    At this point running `which pip` and `which python` should produce a path to the `pip` and `python` instances in `.venv/bin/`.
 
    Running `python --version` should produce 3.12.0.
 
    VS Code and Jupyter users may need to point their environment to the right Python interpreter. (`.vinv/bin/python`)
 
5. We shipped our `pip freeze` output as the `requirements_*.txt` files file, so one can (try to) install all packages with `pip install -r requirements.txt`. If that is problematic, one can try `cat requirements.txt | xargs -n 1 pip install` following https://stackoverflow.com/questions/22250483/stop-pip-from-failing-on-single-package-when-installing-with-requirements-txt (For some reason to install scikit requires: `python3 -m pip install scikit-learn`)

## citations
We are planning to use Python Control Systems Library which requires citation

    @inproceedings{python-control2021,
        title={The Python Control Systems Library (python-control)},
        author={Fuller, Sawyer and Greiner, Ben and Moore, Jason and
                Murray, Richard and van Paassen, Ren{\'e} and Yorke, Rory},
        booktitle={60th IEEE Conference on Decision and Control (CDC)},
        pages={4875--4881},
        year={2021},
        organization={IEEE}
      }
