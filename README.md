# graph steady state embedding
Learning Steady-States of Iterative Algorithms over Graphs (http://proceedings.mlr.press/v80/dai18a/dai18a.pdf)

#### 1. Setup the environment

##### 1) Download the repository

    git clone git@github.com:Hanjun-Dai/steady_state_embedding --recursive
    
##### 2) Build the dependency

This project depends on the graphnn library. The building instruction can be found here:

###### 2.1) Download and install cuda from https://developer.nvidia.com/cuda-toolkit

    wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/cuda-repo-ubuntu1404_8.0.44-1_amd64.deb
    sudo dpkg -i cuda-repo-ubuntu1404_8.0.44-1_amd64.deb
    sudo apt-get update
    sudo apt-get install cuda
    
  in .bashrc, add the following path (suppose you installed to the default path)
  
    export CUDA_HOME=/usr/local/cuda
    export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
    export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
    
###### 2.2) Download and install intel mkl

  in .bashrc, add the following path
  
    source {path_to_your_intel_root/name_of_parallel_tool_box}/bin/psxevars.sh

###### 2.3) Build static library

    cp make_common.example make_common
    modify configurations in make_common file
    make -j8
    
##### 3) Download the data
Use the following dropbox link:

    https://www.dropbox.com/sh/3gwr2wgh455q9pi/AAB0i6EQimVGslrqtsTIWsL0a?dl=0

Put everything under the 'data' folder, or create a symbolic link with name 'data':

    ln -s /path/to/your/downloaded/files data

Finally the folder structure should look like this:

    steady_state_embedding (project root)
    |__  README.md
    |__  code
    |__  graphnn
    |__  data
    |__  |__ algo_data
    |    |__ amazon
    |    |__ pagerank_ba
    |......
    
#### 2. Run the experiments

Most of the experiments are self-contained, where you need to build the code and then execute 
the script. For example:

    cd code/fit_algo/connectivity
    make
    ./connect.sh
    
The data is already cooked, so the ``code/data_process`` folder is for reference purpose. 

#### Reference

```bibtex
@inproceedings{dai2018learning,
  title={Learning Steady-States of Iterative Algorithms over Graphs},
  author={Dai, Hanjun and Kozareva, Zornitsa and Dai, Bo and Smola, Alex and Song, Le},
  booktitle={International Conference on Machine Learning},
  pages={1114--1122},
  year={2018}
}
```
