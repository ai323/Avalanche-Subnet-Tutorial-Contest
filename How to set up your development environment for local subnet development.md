# How to set up your development environment for local subnet development?

## Step-By-Step Guide

First thing first, you need to install [Avalanche-CLI](https://github.com/ava-labs/avalanche-cli), which is a command line tool that gives developers access to everything Avalanche.

## 📁 Directory Creation

Before you rush to download the binary file, you need to create a local directory where the Avalanche-CLI file will be saved.

After that, you can use the cd command to go to the directory:

```
cd <your newly created directory>
```

## ⏳ Default Installtion

To install the binary in your current directory, please use the following command in you command line window.

```shell
curl -sSfL https://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s
```
The binary will be installed inside the ./ directory (relative to where the install command was run).

## ⏳ Custom Installation

To download the binary into a specific directory, run this command instead:
```shell
curl -sSfL https://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s -- -b <relative directory>
```

## 🏷️ Add to path

To add the binary to your path, run

```shell
cd bin
export PATH=$PWD:$PATH
```

To add it to your path permanently, add an export command to your shell initialization script (ex: .bashrc).

## ⚒️ Create Subnet 

Now you can use this command to create your own subnet:

```shell
avalanche subnet create <subnetName>
```
After typing the command, use your keyboard to navigate to the **SubnetEVM** option to get started.

<img width="290" alt="image" src="https://user-images.githubusercontent.com/85045618/172835351-1b584b5a-10df-4d36-b20c-7f849d9fc31b.png">

To get your subnet up and running, you need to assign a **ChainId** to it:

<img width="432" alt="image" src="https://user-images.githubusercontent.com/85045618/173055221-5783acd7-1778-4baa-bdd7-9645ec91239c.png">

**Warning** Please make sure the **ChainId** that you are assigning to your subnet is not takend by existing EVM chains (i.e. ChainID = 1 will thorw an error when you try to deploy your subnet to local network)

Also, you have to set the fee configuration for your subnet, there are three default options: Low/Medium/High and if none of the opiton satisfies your needs, you can go ahead with **Customize fee config** option 😀

<img width="528" alt="image" src="https://user-images.githubusercontent.com/85045618/172840496-eb1a16b3-ef5f-4d21-a771-b55251dbc3a7.png">

Next is to configure the **airdrop** option and again we go with the flow 😀

<img width="553" alt="image" src="https://user-images.githubusercontent.com/85045618/172842231-9c9b5cd8-f886-479b-b77c-8ff5a48c0f7e.png">

And next you are given an option to add custom **precompile** to modify the EVM:

<img width="514" alt="image" src="https://user-images.githubusercontent.com/85045618/172842604-60574ad5-b727-4c87-85e6-a867691ef5be.png">

With all the configurations, we just successfully created genesis 🎉 Congratulations 😆

<img width="540" alt="image" src="https://user-images.githubusercontent.com/85045618/172843450-3afc8339-4179-47db-8f25-879474b15e50.png">

## ⚒️ Deploy Subnet

Once you successfully created your own subnet, you can now deploy it 😀

```shell
avalanche subnet deploy <subnetName>
```

Basically you have three options here: Local Network, Fuji Network and Mainnet:

<img width="283" alt="image" src="https://user-images.githubusercontent.com/85045618/172843923-3e83b088-e32e-4c7f-bce6-d2b82d50f874.png">

For now we'll go with Local Network. Once the depolyment is completed, you should see something like the screenshot below:

<img width="1188" alt="image" src="https://user-images.githubusercontent.com/85045618/173053161-4ad85523-c901-4c74-93ed-70e6410ae18b.png">

## 🤔 Closing Thoughts

Fantastic! You have successfully created and deployed a subnet to your local network 😀

And here are a few open questions that you can play around with your subnet:

- Troubleshoot common issues
- Add node validators to the subnet
- Access funded accounts
- Deploy smart contracts
- Interact with contracts
- Bonus point: explain how to experiment with different customization by creating/tearing down/recreating


## 📕 Glossary

### Subnet

A subnet, or subnetwork, is a dynamic set of validators working together to achieve consensus on the state of a set of blockchains. Each blockchain is validated by exactly one subnet. A subnet can validate many blockchains. A node may be a member of many subnets.

A subnet manages its own membership, and it may require that its constituent validators have certain properties.

### EVM

EVM stands for Ethereum Virtual Machine, it is a concept first brought up by Ethereum. 

A Virtual Machine (VM) defines the application-level logic of a blockchain. In technical terms, it specifies the blockchain’s state, state transition function, transactions, and the API through which users can interact with the blockchain. Every blockchain on Avalanche is an instance of a VM.

When you write a VM, you don't need to concern yourself with lower-level logic like networking, consensus, and the structure of the blockchain. Avalanche does this behind the scenes so you can focus on the thing you would like to build.

Think of a VM as a blueprint for a blockchain; you can use the same VM to create many blockchains, each of which follows the same ruleset but is logically independent of other blockchains.


### ChainId

Ethereum networks have two identifiers, a network ID and a chain ID. Although they often have the same value, they have different uses.

Peer-to-peer communication between nodes uses the network ID, while the transaction signature process uses the chain ID.

### Airdrop

Airdrops involve crypto projects sending free tokens en masse to their communities in a bid to encourage adoption.

In our subnet case, since you are the creator of the subnet, you are entitled to create airdrop for yourelf.
