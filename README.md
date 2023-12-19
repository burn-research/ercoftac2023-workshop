
# Exercise sessions ERCOFTAC 2023

In this repository you can find the resources for the exercise sessions of the 2023 ERCOFTAC workshop in Barcelona.

## Python resources

There are two options to use a Python IDE on Marenostrum:

- Connect to Marenostrum with a display software and use Spyder:
    ```shell
    ssh -X nct01yyy@mn1.bsc.es
    GJDZFvH5.yyy
    salloc -J interactive --x11
    module load ANACONDA
    export XDG_RUNTIME_DIR="" 
    spyder
    ```
    Replace `yyy` with your account's number.
    
- If you don't have a display software like XQuartz, it is possible to use Jupyter notebook by ssh tunnel (this procedure is bit more complex):
    ```shell
    ssh nct01yyy@mn1.bsc.es
    GJDZFvH5.yyy
    salloc --partition=interactive
    module load ANACONDA
    export XDG_RUNTIME_DIR="" 
    jupyter notebook --no-browser --ip=127.0.0.1 --port=9yyy
    ```
    Replace `yyy` with your account's number. As output of the last command you should receive a token for your Jupyter session of the type `http://127.0.0.1:9yyy/?token=xxx…`.
    
    In another terminal on your local machine input:
    ```shell
    ssh -t -t nct01yyy@mn1.bsc.es -L 7077:localhost:8088 ssh loginX -L 8088:localhost:9yyy
    ```
    Replace `X` with the number that you got when creating the interactive session. Open the browser on your local machine and type `localhost:7077`. Insert the token that you received when starting the Jupyter session.

Here you can find an introduction to [Spyder](https://docs.spyder-ide.org/current/videos/first-steps-with-spyder.html) and [Jupyter](https://realpython.com/jupyter-notebook-introduction/).


