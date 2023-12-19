# Installing paraview

* Visit https://www.paraview.org 
* Click on download
* Choose 5.11 (any of the python versions work)
  
## Windows
Download installer (Either MPI or not, but if you choose MPI install https://docs.microsoft.com/en-us/message-passing-interface/microsoft-mpi previously)

## Mac OS
Download .pkg file and install

## Linux
Download tar.gz file
Extract at desired location

```
cd path/to/desired/location
sudo tar -xzvf ParaView-5.11.0-MPI-Linux-Python...
```

Add paraview to bashrc
```
vi ~/.bashrc
ADD LINE: alias paraview="path/to/desired/location/bin/paraview"
```

Test:
On the same terminal do `source ~/.bashrc` (or open a new one), then
`paraview`

See if it runs, else send us an email with the exact error (you can try fixing yourself first)

### Ubuntu
There's a package on the apt-get store for paraview. (NOT RECOMMENDED)
