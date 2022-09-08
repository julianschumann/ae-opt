# Autoencoder enabled global optimization
In this repository, the code and data used to generate the results from the paper "A machine learning approach for fighting the curse of dimensionality in optimization" can be found. This should allow the reconstruction of the results visible in Figures 2, 3, 4, and 6.

# Figure 2
[Figure 2](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.pdf) shows the results of optimizing the benchmark functions, and can be produced with the code found in the subdirectories of [Benchmark_functions](https://github.com/julianschumann/ae-opt/blob/main/Benchmark_functions). When reproducing the results fro c2, c3 and c4, it should be enough to just run the repsective python files:
```
python benchmark_test_c1.py
python benchmark_test_c2.py 
python benchmark_test_c3.py 
python benchmark_test_c4.py 
```

The Figure can then be reproduced by runing [Figure_2.tex](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.tex).


# Figure 3
[Figure 3](https://github.com/julianschumann/ae-opt/blob/main/Figure_3.pdf) is produced by running the [code](https://github.com/julianschumann/ae-opt/blob/main/Compliance_minimization/Figure_3), as in the case of c1 from Figure 2, on multiple processors to decrease computation time:
```
mpirun -n 100 python visualization_1.py
```
The upper file agenerates the required data, while the following one only analyzes the data.
```
python results_visulaization_1.py
```


The Figure can then be reproduced by runing [Figure_3.tex](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.tex).

# Figure 4
[Figure 4](https://github.com/julianschumann/ae-opt/blob/main/Figure_4.pdf) is produced by running the [code](https://github.com/julianschumann/ae-opt/blob/main/Compliance_minimization/Figure_4) on multiple processors to decrease computation time:

```
mpirun -n 50 generate_training_samples.py
mpirun -n 100 training_and_optimization.py
mpirun -n 100 training_and_optimization_bayesian_otpimization.py
```
These three files are necessary to generate the required data, while the following two are only used to analyze the data.
```
python results.py
python results_bayesian_optimization.py
```
It has to be noted here that due to memory constraints, the data generated by us could not be added to the github repository directly. Instead, a [Sample_data_4.zip](https://figshare.com/s/ffec7ed3d2deb9f69c39?file=31640465) has to be downloaded, added to folder [Sample_data](https://github.com/julianschumann/ae-opt/blob/main/Compliance_minimization/Figure_4/Sample_data) and extracted there.


The Figure can then be reproduced by runing [Figure_4.tex](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.tex).

# Figure 6
[Figure 6](https://github.com/julianschumann/ae-opt/blob/main/Figure_6.pdf) is produced by running the [code](https://github.com/julianschumann/ae-opt/blob/main/Compliance_minimization/Figure_4) on multiple processors to decrease computation time:

```
mpirun -n 100 visualization_2_design_space.py
mpirun -n 100 training_visulaization_2.py
mpirun -n 100 visualization_2_latent_space.py
```
These three files are necessary to generate the required data, while the following one only analyzes the data.
```
python results_visulaization_2.py
```
t has to be noted here that due to memory constraints, the data generated by us could not be added to the github repository directly. Instead, a [Sample_data_6.zip](https://figshare.com/s/ffec7ed3d2deb9f69c39?file=31640474) has to be downloaded, added to folder [Sample_data](https://github.com/julianschumann/ae-opt/blob/main/Compliance_minimization/Figure_6/Sample_data) and extracted there.

The Figure can then be reproduced by runing [Figure_6.tex](https://github.com/julianschumann/ae-opt/blob/main/Figure_2.tex).

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

All commands to reproduce the results have to be run in the directory where the respective python files are found.

It also has to be noted that it on other operating systems, the command mpirun might have to be replaced with mpiexec.
