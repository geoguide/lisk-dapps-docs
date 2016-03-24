# Lisk Dapps Documentation

Welcome to the Lisk Dapps documentation. Where you will find all the information needed to start developing decentralized applications on the Lisk blockchain.

## About Lisk

Lisk is a decentralized application platform and crypto-currency, which offers an all round solution for Node.js and JavaScript developers to deploy their own decentralized applications (dapps).

## Lisk Dapps

Lisk Dapps are blockchain based decentralized applications which run on a custom sidechain. They are secured by a group of 101 master nodes elected by the dapp's owner, and operate using the same Delegated-proof-of-stake (DPOS) consensus mechanism as the parent Lisk network.

### Features

- Delegated-proof-of-stake (DPOS) consensus mechanism
- Centralized and decentralized application storage options
- Custom token issuance and exchange
- LISK deposits / withdrawals
- Sandboxed virtual machine

## Development

Lisk Dapps are written using existing web technologies:

  * Backend: **NodeJS/JavaScript**
  * Frontend: **CSS3/HTML5/JavaScript**

Developers already familiar with these technologies, will quickly find their comfort zone, and can start building decentralized applications in very little time at all.

Using the provided command line interface: **Lisk CLI**. Developers can easily generate a new genesis block for their dapp's sidechain, clone the **Lisk Dapp SDK** as a base project structure and create new contracts.

If you are just starting out, then before progressing any further. We strongly suggest learning the basics of the [JavaScript](http://www.w3schools.com/js/default.asp) programming language and [NodeJS](https://nodejs.org/) runtime.

## Tutorials

For more information on how to proceed with developing your first Lisk based dapp. Please read the following tutorials:

* [Setting up an Environment](/documentation?i=lisk-dapps-docs/EnvironmentSetup)
* [Creating a Basic Dapp](/documentation?i=lisk-dapps-docs/BasicDapp)
* [Creating a Messaging Dapp](/documentation?i=lisk-dapps-docs/MessagingDapp)
* [Adding a User Interface](/documentation?i=lisk-dapps-docs/UserInterface)
* [Introducing the Dapp SDK](/documentation?i=lisk-dapps-docs/DappSDK)
* [Creating a Custom Sidechain](/documentation?i=lisk-dapps-docs/Sidechain)
* [Creating a Reddit Dapp](/documentation?i=lisk-dapps-docs/RedditDapp)
* [Debugging Dapps](/documentation?i=lisk-dapps-docs/DebuggingDapps)

## Sandboxing

Lisk Dapps are executed using Lisk Node, a specialized version of NodeJS that provides a sandboxed runtime environment in which to run individual dapps. Inter-process communication is achieved using Named Pipes, with no imposed limit on message size.

Upon launching a new Dapp, the Lisk client starts a new instance of Lisk Node as a child process. If a Dapp encounters a fatal error, then the child process is killed gracefully, leaving the parent Lisk client unaffected.

**Please note, currently there is no protection against unauthorized system calls made from the running dapp. Therefore, running untrusted code is not yet advisable, and could potentially lead to loss of funds. Work is underway to provide a fully sandboxed environment in which to run untrusted code.**

## Determinism

In order for a Lisk sidechain to function correctly, all contracts pertaining to the dapp must behave deterministically. Meaning if a contract is given some particular input, it should always produce the exact same output.

Therefore, when developing new contracts, please take note of the following rules:

* Contracts must always return the exact same result on all nodes.
* Do not use non-deterministic functions such as: Math.random(), which in this case returns a random number.
* All contract logic must exist inside a contract module and follow the Dapp SDK guidelines.
* Any new data added to the sidechain must be broadcast to all nodes.

If the above rules are not adhered to, the sidechain will most likely fork, and fail to achieve consensus. By adhering to the above rules, it will reduce the likelihood of any forking of the sidechain, and therefore ensure consensus is reliably agreed upon by all nodes on the network.

## Forgers

It is the responsibility of forgers to sign blocks for each sidechain.

Forgers are elected by the owner of a dapp and each receive a portion of the transaction fees as a reward for securing the sidechain.

Each genesis block contains a basic list of forgers, but this can be altered at any given point.

All operations affecting the genesis block are done using the provided command line tool: **Lisk CLI**.

## Deposits/Withdrawals

When making deposits or withdrawals between a dapp and the Lisk mainchain. A special type of transaction is used.

In the case of a deposit, this special transaction is broadcast from the mainchain to the dapp's sidechain. Wherein a new transaction, along with a reference to the mainchain's transaction id, is saved to dapp's sidechain, preventing double spending attacks.

**NOTE:** All funds deposited to a dapp reside within the Dapp owner's account.

To prevent any theft of these funds, Lisk provides the option of using a multi-signature dapp account. Which for open sourced dapps is highly recommended, as it requires all signees to a sign any withdrawal requests before they can be authorized.

When making a withdrawal from a dapp. Another special type of transaction is broadcast from the mainchain to the dapp's sidechain. Once this transaction has been applied to a block, the dapp master nodes will initiate the withdrawal. Wherein a copy of the transaction id from the sidechain is saved into the mainchain, preventing double spending attacks.

## API Reference

Lisk Dapps interact with the main Lisk blockchain using an easy to use API.

A detailed reference of this API can be found in our Lisk Dapps API Documentation.

## Further Help

The Lisk Foundation is ready and waiting to answer your questions.

Please feel free to join our chat at: [Lisk.Chat](https://lisk.chat), where you will find us ready and waiting to answer any questions you may need answered as quickly as possible.

Thank you for making Lisk your decentralized application platform of choice.

**The Lisk Team**
