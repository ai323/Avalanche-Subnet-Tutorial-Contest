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

## Add to path

To add the binary to your path, run

```shell
cd bin
export PATH=$PWD:$PATH
```

To add it to your path permanently, add an export command to your shell initialization script (ex: .bashrc).

## Create Subnet 

Now you can use this command to create your own subnet:

```shell
avalanche subnet create <subnetName>
```
After typing the command, use your keyboard to select **SubnetEVM** to getstarted.

<img width="290" alt="image" src="https://user-images.githubusercontent.com/85045618/172835351-1b584b5a-10df-4d36-b20c-7f849d9fc31b.png">

To get your subnet up and running, you need to assign a ChainId to it:

<img width="427" alt="image" src="https://user-images.githubusercontent.com/85045618/172839885-c4949e59-d354-4c20-a91f-2dbc3a54f2bc.png">

