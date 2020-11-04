# AWK DataLab Stack
* Get your Data Analytics environment up and running in seconds
* Add and remove technology stacks as needed
* Collaborate and share your environment easily even years later - being sure that everything still runs
* Control your docker environment through a Jupyter notebook instead of command line arguments

You can safely ignore this warning:
```
WARNING: Found orphan containers
```

## How-to use the AWK DataLab
### Create a new directory for your project
* Create a dedicated directory for your source code
* Create another dedicated directory for your data (not within the source code directory ;-))
* Download this entire DataLab's sourcecode from GitHub and place it in a new directory `datalab` that you created within your source code directory (mind the case!)

Now if you publish your source code to GitHub, you will include your DataLab. And avoid publishing data to the whole world. 

### Set-up a few variables for your new project once
Change the values in the file `./datalab-stacks/environment.env.EXAMPLE`. Save the customized file as a new file `./datalab-stacks/environment.env`.
* `COMPOSE_PROJECT_NAME`: name of this project. Will show up in all container names associated with this project. No spaces or special characters allowed
* `DATALAB_SOURCECODE_DIR`: your Windows directory containing all your source code - including this datalab! Will appear as `/home/jovyan/work` in the Jupyter Notebook
* `DATALAB_DATA_DIR`: your Windows directory containing all data. Will be mounted as `/home/jovyan/data` in the Notebook


### Start a single Jupyter Notebook directly
Just run `run_jupyter_notebook.cmd` directly. Stop it again with `rm_jupyter_notebook.cmd`.


### Start the controlboard if it gets more complicated
Run `run_controlboard.cmd`. Once the controlboard is up, it will be opened within Chrome.
* In the controlboard, open the directory `datalab-stacks`
* Start the notebook `ControlBoard.ipynb`
* Follow the instructions in that notebook

### Stop the controlboard
Be sure to stop any other stacks you might have started from within the controlboard first. Then run `rm_controlboard.cmd`.

## Run several projects simultaneously
Easily run several projects at the same time. Make sure that you choose different project-names in `./datalab-stacks/environment.env` and also set different, **unique** values for all the ports.

If your head starts spinning because you don't know which project's container talks to which other project's container: set-up a dedicated network e.g. with `docker network create project-A-network` and replace **all** strings `datalab-network`  with  `project-A-network` in all files for project A. 


## Remarks
Docker containers such as this controlboard or the different stacks will keep on running forever, even if you restart your machine. So remember to stop them.

## Supported Stacks
Run the following stacks on your local machine or remote server:
* ["Vanilla" Jupyterlab](https://jupyterlab.readthedocs.io/en/stable/)
* [Elastic Stack (formerly ELK-Stack)](https://www.elastic.co/de/products/)
* [PostgreSQL Database](https://www.postgresql.org/)
* [MySQL Database](https://www.mysql.com/)
* [Neo4j](https://neo4j.com/)
