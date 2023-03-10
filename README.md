# dp-gen
A test to check if dp-gen can be used to generate force fields for MoS2. If successful this can be used to accelerate ab-inito simulations.

## Building the conda environment

All dependencies are included in `environment.yml` file. We can either have environment setup in our own project directory 
or in the envs directory of the miniconda folder. The advantage of installing in miniconda folder is that we can use same env
for different packages and it saves bandwidth and storage. The first method on the other hand is more robust. Procedure is as follows

First of all if mamba do not exists then install it via
```bash
conda activate base
conda install mamba -n base -c conda-forge
```

To setup env in project dir 
```bash
mamba env create --prefix ./env --file environment.yml --force
```
or to setup in miniconda envs dir
```bash
mamba env create --name TheProjectName --file environment.yml --force
```

## Update the conda env

If you add (remove) dependencies to (from) the environment.yml file or the requirements.Atxt file
after the environment has already been created, then you can re-create the environment with the
following command.

To update env in project `./env` dir
```bash
conda activate base
mamba env update --prefix ./env --file environment.yml  --prune
```

To update in Miniconda envs dir
```bash
conda actiavte base
mamba env update --name TheProjectName --file environment.yml  --prune
```

## Remove the conda env

If you are low on storage and want to completely remove the conda env. You can do it by 

```bash
conda deactivate
conda env remove --prefix ./env
# or to remove from conda env dirs
conda env remove --name TheProjectName
```
