FROM python:3.13-slim-bullseye

# Install system dependencies for Poetry and AWS CLI
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    gnupg \
    && rm -rf /var/lib/apt/lists/*

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python -

# Add Poetry to PATH (important for non-interactive shells)
ENV PATH="/root/.poetry/bin:$PATH"

# Set working directory
WORKDIR /workspaces/codespaces

# Copy project files (if any) - adjust as needed
# NOT TODO COPY pyproject.toml poetry.lock ./

# Install project dependencies (if any) - use --no-dev for production
# TODO RUN poetry install --no-dev

# # Install AWS CLI
# RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
#     && unzip awscliv2.zip \
#     && ./aws/install \
#     && rm awscliv2.zip \
#     && rm -rf ./aws

# # Add AWS CLI to PATH
# ENV PATH="/usr/local/aws-cli/bin:$PATH"

# # Install AWS CDK CLI
# RUN npm install -g aws-cdk

# Create a non-root user (important for security)
RUN useradd -ms /bin/bash vscode

# Install sudo
RUN apt-get update && apt-get install -y sudo

# Add vscode user to sudo group and configure passwordless sudo
RUN usermod -aG sudo vscode

# NOTE RUN echo "vscode ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Switch to the vscode user
USER vscode
