# Containerized Application Development Workflow

## Sample Dockerfile for python
```Dockerfile
# Select Base Image
FROM python:3

# Install development tools
RUN apt update && apt install -y vim git tmux

# Copy configuration for development tools
# vim configuration
RUN git clone https://github.com/sujairamprasathc/vim-config.git
WORKDIR /vim-config
RUN git submodule init && git submodule update
RUN make
ENV TERM=screen-256color
# tmux configuration
WORKDIR /
RUN git clone https://github.com/sujairamprasathc/tmux-config.git
WORKDIR /tmux-config
RUN make

# Set working directory and copy the requirements for the project
WORKDIR /app
COPY ./requirements.txt ./requirements.txt

# Install application dependencies
RUN pip install -r requirements.txt

# Copy the source files to the app directory inside the container
COPY ./ ./
```
