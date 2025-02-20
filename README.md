# Dev Container for Python-based AWS CDK Work

This is biased toward the VS Code IDE platform.

## Base
This repository provides a "base" directory with a `Dockerfile`.  The intention is to use the image built from this as the consistent envionmental basis for any Python-Poetry projects under development.

## Devcontainer
This repository provides a "dot-devcontainer" directory with `Dockerfile` and `devcontainer.json` files.  These files can be copied into the toplevel `.devcontainer` directory of a project.
These files add `AWS CLI` and `CDK` to the Python-Poetry base container for a full development environment.

## Vscode
This repository provides a "dot-vscode" directory with a `settings.json` file. This provides project-level settings values for a uniform editing experience across projects. Among other things, it sets `black-formatter`, `max-line-length 120`.  This file can be copied into the toplevel `.vscode` directory of a project.

### AWS Credentials
Notice devcontainer.json mounts $HOME/.aws in the home of the vscode user in the devcontainer.  This makes your AWS credentials available in the container.
