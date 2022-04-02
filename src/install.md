# Install

## Pre-compiled binaries

Executable binaries are available for download on the [GitHub Releases page](https://github.com/openfare/openfare/releases). Download the binary for your platform (Windows, macOS, or Linux) and extract the archive. The archive contains the `openfare` command line tool.

To make it easier to run, put the path to the binary into your PATH.

## Build from source using Rust

To build the `openfare` executable from source, you will first need to install Rust and Cargo. Follow the instructions on the Rust [installation page](https://www.rust-lang.org/tools/install). OpenFare currently requires at least Rust version 1.58.0

Once you have installed Rust, the following command can be used to build and install `openfare`:

```bash
cargo install openfare
```

This will automatically download `openfare` from [crates.io](https://crates.io), build it, and install it in Cargo's global binary directory (~/.cargo/bin/ by default).

## Installing the latest master version

The version published to crates.io will ever so slightly be behind the version hosted on GitHub. If you need the latest version you can build the git version of `openfare` yourself. Cargo makes this super easy!

```bash
cargo install --git https://github.com/openfare/openfare.git openfare
```

Again, make sure to add the Cargo bin directory to your PATH.
