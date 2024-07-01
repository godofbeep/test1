# Use the official VS Code Dev Containers base image
FROM mcr.microsoft.com/vscode/devcontainers/base:0-bullseye

# Install Solana CLI
RUN sh -c "$(curl -sSfL https://release.solana.com/stable/install)"

# Add Solana CLI to PATH
ENV PATH="/root/.local/share/solana/install/active_release/bin:$PATH"

# Install Node.js and npm
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt-get install -y nodejs

# Install Solana web3.js
RUN npm install -g @solana/web3.js

# Install Rust and Cargo
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y

# Add Rust and Cargo to PATH
ENV PATH="/root/.cargo/bin:$PATH"

# Set the user to vscode
USER vscode