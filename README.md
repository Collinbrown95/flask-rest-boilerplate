# CDO Data Science Team Rest API Boilerplate

This repository is intended to act as a boilerplate for all CDO Data Science Team Python Rest APIs.

*TODO: Add note on how to bootstrap a Rest API project using custom CLI tool* 

**NOTE:** At this point, this project is intended to be fluid and up for discussion. The choices surrounding methodologies and technologies are not set in stone but are some initial recommendations. Feel free to open issues and add direct comments to code blocks.

## Bootstrap

Create a copy of `app/main/config/example.local.cfg`, change the name to `app/main/config/local.cfg` and update configuration variables as desired.

Run the following on the command line to generate application secrets:

```
python generate_secrets.py
```

*TODO: Could set up a bootstrap script that will automatically do the entire bootstrapping process via one command.*

## Conda Environment

To initialize the conda environment, run the following in the root project directory:

```
conda env create -f environment.yml --prefix ./api_env
```

Note the `--prefix ./api_env`. This creates the environment in the project directory in a folder called `api_env`.

This will result in a long prefix in your command prompt. To address this, run the following:

```
conda config --set env_prompt '({name})'
```

To activate the environment:

```
conda activate ./api_env
```

Deactivate:

```
conda deactivate
```

If you add any new packages via conda or pip, make sure to update the `environment.yml`:

```
conda env export > environment.yml
```

To ensure you have all the dependencies defined in the `environment.yml`, run:

```
conda env update -p ./api_env --file environment.yml
```