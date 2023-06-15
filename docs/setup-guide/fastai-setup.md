# Install FastAI

Let's learn how to install FastAI in local `Ubuntu` machine, if you are using `WSL` then the instructions will be same.

* **Step 1** First step is to install Python using Mambaforge, its super fast compared to the other options.

    Mambaforge works interchangeably with Conda, here is a link to the [Github repository](https://github.com/conda-forge/miniforge), make sure to download from `Mambaforge` table.


* **Step 2:** Next go to official [Pytorch](https://pytorch.org/) website and select toggles as per your need. 
In my case I've selected the below toggles.

    ```
        PyTorch Build: stable
        Your OS: Linux
        Package: conda - If you are into Data Science then Conda works better
        Language: python
        Compute Platform: 11.7 (in general most packages work better if you select one version below latest) 
    ```

* **Step 3:** Next copy suggested command as per your selections and then open your terminal and run it

    ```mamba install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia```

    !!! tip  "Make sure to replace `conda` with `mamba`"

* **Step 4:** Now install `FastAi` using the below command, here is a link to FastAi [documentation](https://docs.fast.ai/).
    
    ```mamba install -c fastchan fastai```

* **Step 5:** Instal Jupyter Notebook using the below command.
    
    ```mamba install -c conda-forge jupyterlab```

