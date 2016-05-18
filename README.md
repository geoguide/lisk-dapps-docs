# Lisk Apps Documentation

Welcome to the Lisk Blockchain Apps documentation. Where you will find all the information needed to start developing blockchain applications on the Lisk platform.

## About Lisk

Lisk is a blockchain application platform and crypto-currency, which offers an all round solution for Node.js and JavaScript developers to deploy their own blockchain applications.

## Lisk Blockchain Apps

Lisk Blockchain Apps are blockchain based applications which run on a custom sidechain. They are secured by a group of 101 master nodes elected by the app's owner, and operate using the same Delegated-proof-of-stake (DPOS) consensus mechanism as the parent Lisk network.

### Features

- Delegated-proof-of-stake (DPOS) consensus mechanism
- Centralized and decentralized application storage options
- Custom token issuance and exchange
- LISK deposits / withdrawals
- Sandboxed virtual machine

## Development

Lisk Apps are written using existing web technologies:

  * Backend: **NodeJS/JavaScript**
  * Frontend: **CSS3/HTML5/JavaScript**

Developers already familiar with these technologies, will quickly find their comfort zone, and can start building blockchain applications in very little time at all.

Using the provided command line interface: **Lisk CLI**. Developers can easily generate a new genesis block for their app's sidechain, clone the **Lisk App SDK** as a base project structure and create new contracts.

If you are just starting out, then before progressing any further. We strongly suggest learning the basics of the [JavaScript](http://www.w3schools.com/js/default.asp) programming language and [NodeJS](https://nodejs.org/) runtime.

## Tutorials

For more information on how to proceed with developing your first Lisk based app. Please read the following tutorials:

* [Setting up an Environment](/documentation?i=lisk-apps-docs/EnvironmentSetup)
* [Creating a Basic App](/documentation?i=lisk-apps-docs/BasicApp)
* [Creating a Messaging App](/documentation?i=lisk-apps-docs/MessagingApp)
* [Adding a User Interface](/documentation?i=lisk-apps-docs/UserInterface)
* [Introducing the App SDK](/documentation?i=lisk-apps-docs/AppSDK)
* [Creating a Custom Sidechain](/documentation?i=lisk-apps-docs/Sidechain)
* [Creating a Reddit App](/documentation?i=lisk-apps-docs/RedditApp)
* [Debugging Apps](/documentation?i=lisk-apps-docs/DebuggingApps)

## Sandboxing

Lisk Apps are executed using Lisk Node, a specialized version of NodeJS that provides a sandboxed runtime environment in which to run individual apps. Inter-process communication is achieved using Named Pipes, with no imposed limit on message size.

Upon launching a new App, the Lisk client starts a new instance of Lisk Node as a child process. If a App encounters a fatal error, then the child process is killed gracefully, leaving the parent Lisk client unaffected.

**Please note, currently there is no protection against unauthorized system calls made from the running app. Therefore, running untrusted code is not yet advisable, and could potentially lead to loss of funds. Work is underway to provide a fully sandboxed environment in which to run untrusted code.**

## Determinism

In order for a Lisk sidechain to function correctly, all contracts pertaining to the app must behave deterministically. Meaning if a contract is given some particular input, it should always produce the exact same output.

Therefore, when developing new contracts, please take note of the following rules:

* Contracts must always return the exact same result on all nodes.
* Do not use non-deterministic functions such as: Math.random(), which in this case returns a random number.
* All contract logic must exist inside a contract module and follow the App SDK guidelines.
* Any new data added to the sidechain must be broadcast to all nodes.

If the above rules are not adhered to, the sidechain will most likely fork, and fail to achieve consensus. By adhering to the above rules, it will reduce the likelihood of any forking of the sidechain, and therefore ensure consensus is reliably agreed upon by all nodes on the network.

## Forgers

It is the responsibility of forgers to sign blocks for each sidechain.

Forgers are elected by the owner of a app and each receive a portion of the transaction fees as a reward for securing the sidechain.

Each genesis block contains a basic list of forgers, but this can be altered at any given point.

All operations affecting the genesis block are done using the provided command line tool: **Lisk CLI**.

## Deposits/Withdrawals

When making deposits or withdrawals between a app and the Lisk mainchain. A special type of transaction is used.

In the case of a deposit, this special transaction is broadcast from the mainchain to the app's sidechain. Wherein a new transaction, along with a reference to the mainchain's transaction id, is saved to app's sidechain, preventing double spending attacks.

**NOTE:** All funds deposited to a app reside within the App owner's account.

To prevent any theft of these funds, Lisk provides the option of using a multi-signature app account. Which for open sourced apps is highly recommended, as it requires all signees to a sign any withdrawal requests before they can be authorized.

When making a withdrawal from a app. Another special type of transaction is broadcast from the mainchain to the app's sidechain. Once this transaction has been applied to a block, the app master nodes will initiate the withdrawal. Wherein a copy of the transaction id from the sidechain is saved into the mainchain, preventing double spending attacks.

## API Reference

Lisk Apps interact with the main Lisk blockchain using an easy to use API.

A detailed reference of this API can be found in our Lisk Apps API Documentation.

## Further Help

The Lisk Foundation is ready and waiting to answer your questions.

Please feel free to join our chat at: [Lisk.Chat](https://lisk.chat), where you will find us ready and waiting to answer any questions you may need answered as quickly as possible.

Thank you for making Lisk your blockchain application platform of choice.

**The Lisk Team**
