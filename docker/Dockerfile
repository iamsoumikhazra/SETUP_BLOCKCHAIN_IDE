# Use the latest Node.js LTS image as the base image
FROM node:20

# Set the working directory
WORKDIR /usr/src/app

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 g++ make curl

# Install Rust
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"

# Install Solidity compiler
RUN npm install -g solc

<<<<<<< HEAD
# Install Hardhat, Ganache CLI, and Forge globally
RUN npm install -g ganache hardhat
=======
# Install Hardhat, Ganache CLI, and the hardhat-ganache plugin globally
RUN npm install -g ganache hardhat
RUN npm install --save-dev @nomiclabs/hardhat-ganache
>>>>>>> 73453503c634343ac1e02d9a55256e7c715863da

# Install Foundry
RUN curl -L https://foundry.paradigm.xyz | bash
RUN /root/.foundry/bin/foundryup

# Add Foundry to PATH
ENV PATH="/root/.foundry/bin:${PATH}"

# Copy the current directory contents into the container
COPY . .

# Expose the port for Ganache
EXPOSE 8545

# Start Ganache CLI
CMD ["ganache", "--host", "0.0.0.0"]
<<<<<<< HEAD

=======
>>>>>>> 73453503c634343ac1e02d9a55256e7c715863da
