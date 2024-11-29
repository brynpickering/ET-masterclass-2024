# ET-Masterclass-2024

Energy Technologies MPhil ETB1 masterclass in Energy Systems Modelling.

This repository contains a subset of the [Euro-Calliope pre-built model](https://euro-calliope.readthedocs.io), containing two countries in the European energy system.
It is built for use in [_Calliope_ v0.7](https://calliope.readthedocs.io/en/latest/).
The model is available on the national spatial resolution and daily temporal resolution, with a subset of technologies available compared to the base Euro-Calliope.

Euro-Calliope models like this can be built manually, which adds more configuration options.
To learn how to build Euro-Calliope manually, head over to [Euro-Calliope's documentation](https://euro-calliope.readthedocs.io).

## At a glance

The base Euro-Calliope is a model of the European energy system, with each node representing an administrative unit.
It is built on three spatial resolutions: on the continental level as a single node, on the national level with 34 nodes, and on the regional level with 497 nodes.
At each spatial _node_, renewable generation capacities (wind, solar, bioenergy) and balancing capacities (battery, hydrogen) can be invested in to meet electricity demand, and heat pumps or conventional natural gas can be invested in to meet building heat demand.
In addition, a fixed amount of hydro electricity and pumped hydro storage is available, based on what already exists today.
Once invested in, technologies can satisfy energy demands at each node, where demand is based on historic data.
Nodes are connected through electricity transmission lines, which may have unrestricted capacity or be limited based on real data.
Using [Calliope](https://www.callio.pe), the model is solved as a linear optimisation problem with total monetary cost of all capacities and their operation as the minimisation objective.

## Prepare

First, you will need to install software on your device:

1. [The Gurobi solver license](https://www.gurobi.com/downloads/end-user-license-agreement-academic/).
This gives you access to a high-performance optimisation solver.
1. [VSCode](https://code.visualstudio.com/download).
This gives you access to an Interactive Development Environment (IDE) in which to edit code and to interact with your device's terminal.
1. [Miniconda](https://docs.anaconda.com/miniconda/install/).
This gives you access to `conda` in your device's terminal, with which you can create isolated Python environments to work in.

With this software installed, you can then set up VSCode to allow access to `conda` and `git` from the "terminal":

1. Open VSCode.
1. Open the `command palette` (Control-Shift-P, shows a bar at the top of the screen).
1. Search for `Terminal: Select Default Profile`.
1. Select `Command Prompt`.
1. Open a new terminal window (`Terminal` top-bar tab -> `New Terminal`, it will open at the bottom of the screen).
1. Run `conda install git` in the terminal.

With VSCode set up, you can "clone" (i.e. copy) this repository to your device:

1. In the VSCode terminal, call `git clone git@github.com:brynpickering/ET-masterclass-2024.git <output-directory>`.
`<output-directory>` should be a directory on your device where you want to store cloned GitHub repositories (often something like `%USERPROFILE%\Repositories` on Windows or `~/Repositories` on Linux/MacOS).
1. Then you can open that cloned repository (i.e. downloaded folder) in VSCode (`File` top-bar tab -> `Open Folder` -> navigate to `<output-directory>\ET-masterclass-2024`).

Finally, you can create the isolated Python working environment for this masterclass:

1. In your `<output-directory>\ET-masterclass-2024` VSCode session, open a new terminal.
1. Run the following two commands to create your working environment and then to _activate_ it:
    ```bash
    conda env create -f environment.yaml
    conda activate euro-calliope-et-masterclass
    ```

## Run

Although you can run the model from the command line, the best way to get to grips with the model is using the [Jupyter notebooks](https://jupyter.readthedocs.io/en/latest/running.html) found in this repository.
They will be available on your device after following the [preparation steps](#prepare), and visible in the VSCode `Explorer` when you have the `<output-directory>\ET-masterclass-2024` folder open in VSCode.
You can follow those and, when you want to go further, you can read more in the [Calliope documentation](https://calliope.readthedocs.io/en/latest).

## Customise

This pre-built model is a very simple example.
You can extend / amend it directly by modifying the YAML files.
You can also find more complete pre-built models [on Zenodo](https://zenodo.org/record/3949553).
You may find that even that needs customisation to fit your purpose.
Once you've managed to run them, it's a good point in time to learn about [model customisation options in Euro-Calliope](https://euro-calliope.readthedocs.io/en/latest/model/customisation/).

## More information

For more information on Euro-Calliope and how to use and modify the models, see [Euro-Calliope's documentation](https://euro-calliope.readthedocs.io).

## License and attribution

Euro-Calliope is developed and maintained within the [Calliope project](https://www.callio.pe).

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

Contains modified Copernicus Atmosphere Monitoring Service information 2020.
Neither the European Commission nor ECMWF is responsible for any use that may be made of the Copernicus information or data it contains.

Contains modified data from [Renewables.ninja](https://www.renewables.ninja/).

Contains modified data from [Open Power System Data](https://open-power-system-data.org).

For more details on sources, see the [Euro-Calliope GitHub repository](https://github.com/calliope-project/euro-calliope/tree/e9cb908a5b4c6274148a16b59e5dd0b412aaf560).