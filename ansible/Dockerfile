# Use a base image with Python and minimal tools
FROM python:3.9-slim

# Install essential packages
RUN apt-get update && \
    apt-get install -y \
    build-essential \
    libssl-dev \
    libffi-dev \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# Install Ansible
RUN pip install ansible

# Set the working directory to /ansible
WORKDIR /ansible

# Create a non-root user to run Ansible commands
RUN useradd -m ansible

# Set the user to the newly created ansible user
USER ansible

# Copy the current directory contents into the container at /ansible
COPY . /ansible

# Default command when the container is run
CMD ["ansible", "--version"]
