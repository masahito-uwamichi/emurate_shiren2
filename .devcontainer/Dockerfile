# Use the official Rust image as base
FROM rust:1.75-bookworm

# Install basic development tools
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
        git \
        curl \
        wget \
        build-essential \
        pkg-config \
        libssl-dev \
        sudo \
        vim \
        nano \
    && apt-get autoremove -y && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install additional Rust components
RUN rustup component add clippy rustfmt rust-src

# Install only essential cargo tools with individual error handling
RUN cargo install cargo-edit || echo "cargo-edit failed, continuing..."

# Set up the workspace directory
WORKDIR /workspaces/emurate_shiren2

# Default command
CMD ["/bin/bash"]
