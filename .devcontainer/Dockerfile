FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Update and install basic development tools
RUN apt-get update && \
    apt-get install -y \
    build-essential \
    wget \
    git \
    vim \
    nano \
    unzip \
    zip \
    tar \
    software-properties-common \
    apt-transport-https \
    ca-certificates \
    gnupg \
    lsb-release \
    && apt-get clean -y

# Install Python and related tools
RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    python3-venv \
    && apt-get clean -y

# Install Node.js setup script
RUN curl -fsSL https://deb.nodesource.com/setup_20.x -o nodesource_setup.sh

# Run Node.js setup script
RUN bash nodesource_setup.sh

# Install Node.js and npm
RUN apt-get install -y nodejs

# Update npm to the latest version
RUN npm install -g npm

# Install TypeScript globally
RUN npm install -g typescript

# Clean up
RUN apt-get clean -y && rm nodesource_setup.sh

# Install C/C++ compilers and tools
RUN apt-get update && \
    apt-get install -y \
    gcc \
    g++ \
    cmake \
    gdb \
    && apt-get clean -y

# Install AI tools
RUN pip3 install --upgrade pip && \
    pip3 install \
    numpy \
    pandas \
    scipy \
    scikit-learn \
    matplotlib \
    jupyter \
    tensorflow \
    torch \
    torchvision \
    && apt-get clean -y

# Clean up
RUN apt-get autoremove -y && \
    apt-get clean -y

# Default command
CMD ["bash"]