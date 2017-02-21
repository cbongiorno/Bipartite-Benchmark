# Bipartite-Tools
A tool for testing community detection algorithms on bipartite projected networks.

To install on Linux run:

```
sudo ./INSTALL
```

It is possible to use it as a python library:

```
import bipnet
```

or call the python code from bash, without install it. The code was tested only on Linux.

The module validate contains the functions for statistically validated networks. The module metrics contains other useful functions (for ex. the AWI). The code includes a wrapper to the louvain community detection method written by E. Lefebvre and released under GNU Licence. The louvain code is available separately [here](https://sourceforge.net/projects/louvain/)

## Dependencies

To install the dependencies un from bash

```
$ sudo pip install numpy pandas python-igraph matplotlib scipy
```

## How to use the code

### Statistical Validation
In the folder example there is the simple_example.py for the python usage. To use it from bash:

```
$ bipnet/Validate.py -i examples/bipartite_input.net -o proj.net --side 0 --thr 0.01
```

the option --side can assume value 0 or 1. If it is zero it will projected with respect to the first column, otherwise it will projected with respect the second column. The option --thr is the significance level of the statistical validation. It is suggested to use 0.01.

The code will produce three networks proj_full.net proj_bonf.net proj_fdr.net.

#### Adjusted Wallace Index

In the folder example there is the simple_example.py for the python usage. To use it from bash:

```
$ bipnet/metric.py examples/awi_input 
```
The code will check the first column respect to the second.

### Benchmark

In the folder example there is the simple_example.py for the python usage. To use it from bash:

```
$ bipnet/Benchmark.py -i examples/config_benchmark.cfg -o bipartite.net --noise 0.7 
```

## License
The code is released under GNU license. 


## Authors

* **Christian Bongiorno** - [PurpleBooth](https://github.com/PurpleBooth)\\

See also the list of contributors:\\
Andras London [andraslondon@gmail.com](andraslondon@gmail.com)\\
Salvatore Miccichè [salvatore.micciche@unipa.it](salvatore.micciche@unipa.it)\\
Rosario N Mantegna [rn.mantegna@gmail.com](rn.mantegna@gmail.com)

