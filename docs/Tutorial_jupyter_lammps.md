LAMMPS in Jupyter Notebook
=============================================




### LAMMPS Basic
----
#### Client object
In the Notebook, we first import the `ipyparallel` module followed by creating a `Client` object `rc` in the MPI mode to connect to the IPython cluster

```
In[1]: import ipyparallel as ipp
       rc = ipp.Client(profile='mpi')
```



More useful parallel magic commands can be found in the [ipyparallel documentation][ref-mpi4py].

[ref-mpi4py]:https://mpi4py.readthedocs.io/en/stable/index.html

#### Resources

Ipyparallel documentation:  
https://ipyparallel.readthedocs.io/en/latest/  

---

Go to: [Home](../README.md), [Software](./Software.md), [Tutorials](./Tutorials.md), [Examples](./Examples.md), [FAQ](./Faq.md)