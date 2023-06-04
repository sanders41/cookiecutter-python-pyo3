# Python Cookiecutter Template

[![Tests Status](https://github.com/sanders41/cookiecutter-python-pyo3/workflows/Testing/badge.svg?branch=main&event=push)](https://github.com/sanders41/cookiecutter-python-pyo3/actions?query=workflow%3ATesting+branch%3Amain+event%3Apush)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/sanders41/cookiecutter-python-pyo3/main.svg)](https://results.pre-commit.ci/latest/github/sanders41/cookiecutter-python-pyo3/main)

Generates a structure for Python packages built with Rust using [pyo3](https://github.com/PyO3/pyo3).
[Maturin](https://github.com/PyO3/maturin) is used for builds and publishing, and GitHub Actions is
used for continuous integration and continuous deployment. [Just](https://github.com/casey/just)
is used for managing installing dependencies, building, testing, and, linting.

## Dev dependencies that are included

- black
- maturin
- mypy
- pre-commit
- pytest
- pytest-cov
- ruff

## How to use

First make sure you have cookiecutter installed. Instructions for installing can be found
[here](https://cookiecutter.readthedocs.io/en/1.7.2/installation.html).

Once cookiecutter is installed go to the directory where you want to create the project and run:

```sh
cookiecutter https://github.com/sanders41/cookiecutter-python-pyo3
```

You will be asked to fill in the following information:

- project_name: The name of the project
- project_slug: The development friendly name of the project.
- source_dir: The name name of the source directory for the project.
- project_description: A short discription of the purpose of the project [Optional]
- creator: The full name of the project creator
- creator_email: The email address for the creator
- license: The license to use for the project. Select "No license" if no license should be included
- copyright_year: The year to use for the copyright year in the license file. Required for MIT
- python_version: The default version of Python that can be used for the project.
- min_python_version:  The lowest supported version of Python for the project.
- github_action_python_test_versions: The versions of Python that should be used in the CI tests.
- max_line_length: The maximum allowed line length for Python.
- use_dependabot: Adds a GitHub action for dependabot.
- use_continuous_deployment: Adds a workflow for continous deployment to pypi.
- multi_os_ci: If True then CI is setup to run tests on Windows, Mac, and Linux. If False tests
are only run on Linux.

Next change to your newly created directry.

```sh
cd project_slug  # replace project_slug with the name you used at creation
```

Create a virtual environment and activate it.

Create a virtual environment (optional)

```sh
python3 -m venv .venv
```

Activate the virtual environment

```sh
. .venv/bin/activate
```

Install the dependencies

```sh
just install
```

Create a git repositry

```sh
git init
```

Install the pre-commit hooks

```sh
pre-commit install
```

Commit the files to git

```sh
git add .
git commit -am 'Inital commit'
```

Now the project is ready to use.
