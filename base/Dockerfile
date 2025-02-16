FROM python:3.13-slim-bullseye

# Install system dependencies for Poetry and AWS CLI
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    gnupg \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Install Poetry
ENV POETRY_HOME=/etc/poetry
RUN curl -sSL https://install.python-poetry.org | POETRY_HOME=$POETRY_HOME python - \
    && chmod a+x ${POETRY_HOME}/bin/poetry \
    && ln -s ${POETRY_HOME}/bin/poetry /usr/local/bin/poetry


