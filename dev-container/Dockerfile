FROM cs2025/py-aws-base:latest

# Install AWS CLI (system-wide)
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm awscliv2.zip \
    && rm -rf ./aws
ENV PATH="/usr/local/aws-cli/bin:$PATH"

# Install Node.js and npm
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash -  # Choose your Node.js version
RUN apt-get install -y nodejs

# Create the vscode user
RUN useradd -ms /bin/bash vscode
# Install sudo
RUN apt-get update && apt-get install -y sudo
# Add vscode user to sudo group and configure passwordless sudo
RUN usermod -aG sudo vscode
RUN echo "vscode ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Switch to the vscode user
USER vscode

# FIX THIS Set the initial WORKDIR
WORKDIR /workspaces/test-proj
# Install AWS CDK CLI (as the vscode user) - Install locally
RUN npm install aws-cdk
