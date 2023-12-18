
# Exercise session on POD and DMD

In this repository there are two Jupyter notebooks containing the tasks required to solve the exercise on Proper Orthogonal Decomposition (POD) and Dynamic Mode Decomposition (DMD).

## Dataset

The dataset consists of 1024 images (CH* intensity) of the BIMER flame [[1]](https://doi.org/10.1115/1.4044998). Each image has a 64x64 resolution. The flame is excited by modulating the air flow with a frequency equal to 100 Hz. The sampling frequency is equal to 2500 Hz.

## Python resources

The only libraries required to solve these exercises are Numpy and Matplotlib. Both are generally preinstalled with Python, so you should be able to solve the exercises without installing any new library.

There are several options to write and execute the code:

- If Python is already installed on your local machine, you can download this repo and start coding on your favorite IDE (Jupyter, Spyder, VScode etc.)

- If you don't have Python installed or you want to try use Marenostrum, there are two options available:
	- Connect to Marenostrum with a display software and use Spyder:
	    ```shell
        ssh -X nct01yyy@mn1.bsc.es
        GJDZFvH5.yyy
        salloc -J interactive --x11
        module load ANACONDA
        export XDG_RUNTIME_DIR="" 
        spyder
        ```
        Replace `yyy` with your account's number. The dataset con be found at ` /home/nct00/nct00006/ercoftac2023/X_100_r64.npy`.
    
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
        Replace `X` with the number that you got when creating the interactive session. Open the browser on your local machine and type `localhost:7077`. Insert the token that you received when starting the Jupyter session. The dataset con be found at ` /home/nct00/nct00006/ercoftac2023/X_100_r64.npy`

- Finally, the last option is to use [Colab](https://colab.google/). In this case, you will have to download the dataset from the repository and upload it on Colab.


If you are a beginner with Python, you can have a look at these introductions for [Numpy](https://numpy.org/doc/stable/user/absolute_beginners.html) and [Matplotlib](https://matplotlib.org/stable/tutorials/pyplot.html). Also, here you can find an introduction to [Spyder](https://docs.spyder-ide.org/current/videos/first-steps-with-spyder.html) and [Jupyter](https://realpython.com/jupyter-notebook-introduction/).


