= Jupyter Setup =

    1. Install *Jupyter* in _base_ env with `conda install jupyter`.
    2. Create a desktop shortcut for _$HOME\miniconda3\Scripts\jupyter-notebook.exe_.
    3. Right click shortcut -> Properties -> Set Target as _$HOME\Documents\Data Analysis_.
    4. Pin shortcut to Start -> Delete shortcut
    5. _ipykernel_ package is buggy with python version >=3.7 (only in windows):
        a) Create a python3.6 environment _da36_ with `conda create -n da36 python=3.6 -y`.
        b) Install _ipykernel_ in _da36_ with `conda activate da36` -> `conda install ipykernel -y`.
        c) Add _da36_ kernel to *Jupyter* with `ipython kernel install --user --name=da36_py36`.
    6. To remove old kernel from *Jupyter*:
        a) List kernels with `jupyter kernelspec list`.
        b) Remove kernel with `jupyter kernelspec remove kernel-name`.

