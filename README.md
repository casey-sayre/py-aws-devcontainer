# Dev Container for Python-based AWS CDK Work

The presumed IDE platform for devcontainers is Visual Studio Code.

## Base
This repository provides a "base" directory with a `Dockerfile`.  The intention is to used the image built from this as the consistent envionmental basis for any Python-Poetry projects under development.

## Devcontainer
This repository provides a "dev-container" directory with `Dockerfile` and `devcontainer.json` files.  These files can be copied into the toplevel `.devcontainer` directory of a project.
These files add `AWS CLI` and `CDK` to the Python-Poetry base container for a full development environment.

### AWS Credentials
Notice devcontainer.json mounts $HOME/.aws in the home of the vscode user in the devcontainer.  This makes your AWS credentials available in the container.
