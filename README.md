# Python base project

This is a basic python project that can be used as a starting point for any
data science python project.
Feel free to custroimize this project for your own needs by modifying all the defalt
files and folders.

## Environment setup

The project uses Docker to provide a reproducible environment for running
the code.

The docker environment can be configured by editing [Dockerfile](Dockerfile) to
include any additional Linux packages that you need for your project or even use
another base image if needed.
Configure [requirements.txt](requirements.txt) to include any additional python
packages that you need for your project.

To deploy the environment, run in the project home directory:
```bash
make build
```

Once the environment is built, you can start a container with:
```bash
make run
```

The container will have the project root directory mounted to `/workdir` inside,
so you can access all the data in the folder from within the container. Files saved
inside `/workdir` will be saved to your host machine.


## Pre-commit hooks

The project provides some basic pre-commit hooks, to help with the code
formatting and linting before committing. It is optional and just a helper,
but, please, ensure the final code is formatted correctly and follows pep8.

To install pre-commit hooks, run in the project home directory:
```bash
pip install pre-commit
pre-commit install
pre-commit install-hooks
```
