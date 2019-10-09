Install and setup ipyparallel
=============================================

**STEP 1: Istanll ipyparallel**

Ipyparallel can be installed using `pip`
```
$ pip install ipyparallel --user
```
The flag `--user` lets you install the package locally (in ~/.local by default) without requiring root permission.

Make sure the system knows where to find the executables just installed (ipcluster etc). 
If necessary, update the the shell config file (e.g. .bashrc) by appending the path to variable $PATH

```
export PATH=$PATH:$HOME/.local/bin
``` 
Use the following command to enable/disable the clusters tab in the Jupyter Notebook dashboard:

```
$ ipcluster nbextension enable (or disable) --user
```
Check the status of `nbextension`

```
$ jupyter nbextension list
```
You should see the message below if ipyparallel was installed successfully 
```
ipyparallel/main  enabled 
- Validating: OK
```
----

**STEP 2: Create IPython configuration file**

Use command `ipython` to create an configuration profile named `mpi`

```
$ ipython profile create --parallel --profile=mpi
```

And then add the following line in the file ipcluster_config.py located in `$IPYTHONDIR/profile_mpi/` (IPYTHONDIR=~/.ipython by default) to instruct ipcluster to use the MPI launchers:

```
c.IPClusterEngines.engine_launcher_class = 'MPIEngineSetLauncher'
```
---
**STEP 3: Use IPython Clusters in Jupyter**

Open Jupyter Notebook and the IPython Clusters tab should appear in the dashboard with the `default` and `mpi` profile.

  <img src="../images/pic_ipycluster.png" alt="ipy_cluster" width="800">

Say if we want to start the IPython controller on the current host and use mpiexec to start 4 engines, just enter '4' in the row of 'mpi' and click the `Start` button. This is the same as running the following command:

```
$ ipcluster start -n 4 --profile=mpi
```

You are now ready to use the controller and engines from Jupyter to execute commands in parallel.

---
Reference:  
https://ipyparallel.readthedocs.io/en/latest/

Go to:  
[Tutorial: Parallel computing in Jupyter Notebook](./Tutorial_parallel_computing.md)  
[Home](../README.md), [Software](./Software.md), [Tutorials](./Tutorials.md), [Examples](./Examples.md), [FAQ](./Faq.md)