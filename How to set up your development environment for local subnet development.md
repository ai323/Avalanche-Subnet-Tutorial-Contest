# How to set up your development environment for local subnet development?

First thing first, you need to install [Avalanche-CLI](https://github.com/ava-labs/avalanche-cli), which is a command line tool that gives developers access to everything Avalanche.

## Directory Creation

Before you rush to download the binary file, you need to create a local directory where the Avalanche-CLI file will be saved.

After that, you can use the cd command to go to the directory:

```
cd <your newly created directory>
```

## Default Installtion

To install the binary in your current directory, please use the following command in you command line window.

```shell
curl -sSfL https://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s
```
The binary will be installed inside the ./ directory (relative to where the install command was run).

## Custom Installation

To download the binary into a specific directory, run this command instead:
```shell
curl -sSfL https://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s -- -b <relative directory>
```
