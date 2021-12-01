# Autoencoder enabled global optimization
In this repository, the code and data used to generate the results from the paper "Fighting the curse of dimensionality: A machine learning approach to finding global optima" can be found. This should allow the reconstruction of the results visible in Figures 2, 3, 4, and 6.

# Figure 2
[Figure 2](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.pdf) shows the results of optimizing the benchmark functions, and can be produced with the code found in the subdirectories of [Benchmark_functions](https://github.com/julianschumann/ae-opt/blob/main/Benchmark_functions). When reproducing the results fro c2, c3 and c4, it should be enough to just run the repsective python files:
```
python benchmark_test_c2.py 
python benchmark_test_c3.py 
python benchmark_test_c4.py 
```

But due to the larger computational demands to optimize c1, 50 processors were used for this problem:
```
mpirun -n 50 python benchmark_test_c1.py
python results_benchmark_test_c1.py
```

# Figure 3
[Figure 3](https://github.com/julianschumann/ae-opt/blob/main/Figure_3.pdf) is produced, like c1 from Figure 2 with the help of multiple processors to decrease computation time:
```
mpirun -n 50 python visualization_1.py
python results_visulaization_1.py
```

# Figure 4
[Figure 4](https://github.com/julianschumann/ae-opt/blob/main/Figure_4.pdf)\\


# Figure 6
[Figure 6](https://github.com/julianschumann/ae-opt/blob/main/Figure_6.pdf)\\




# Software used
The result show in the paper have been produced using the following software implementation:
- Python: 3.7.9
  - Numpy: 1.18.5
  - Scipy: 1.4.1
  - Tensorflow: 2.3.0
  - Keras: 2.4.3
  - Mpi4py: 3.0.3
  - Pillow: 8.4.0
- Openmpi: 1.8.8

All commands to reproduce the results have to be run in the directory where the respective python files are found
