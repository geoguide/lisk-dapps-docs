# Setting up an Environment

Before we can start building our first Lisk blockchain application (app), we first need to setup a development environment to include a localized testnet and the **Lisk CLI** tool.

## Lisk Testnet

In order to install a suitable testnet environment that is isolated from the main network, please refer to one of the following installation tutorials, making sure to install the **testnet** version of Lisk, rather than the **mainnet** version.

* [Installing Lisk (from Binaries)](/documentation?i=lisk-docs/BinaryInstall)
* [Installing Lisk (using Docker)](/documentation?i=lisk-docs/DockerInstall)
* [Installing Lisk (from Source)](/documentation?i=lisk-docs/SourceInstall)

**Which option to choose:**

- [Installing Lisk (from Binaries)](/documentation?i=lisk-docs/BinaryInstall) is by far the easiest option to choose if your machine is running Linux, Mac OS X or FreeBSD.

- Windows users can [Install Lisk (using Docker)](/documentation?i=lisk-docs/DockerInstall) as a virtual machine.

- [Installing Lisk (from Source)](/documentation?i=lisk-docs/SourceInstall) is here as a reference for core developers and is only intended for special circumstances.

## Lisk CLI

With Lisk installed and up and running, we can now proceed to install **Lisk CLI** and start work on our first app.

Install **Lisk CLI**:

```text
sudo npm install -g lisk-cli
```

After installation completes, check that **Lisk CLI** is installed correctly:

```text
lisk-cli -h
```

If successful **Lisk CLI** should yield the following output:

```text
Usage: lisk-cli [options] [command]

Commands:

    dapps [options]      manage your apps
    contract [options]   contract operations
    crypto [options]     crypto operations

Options:

    -h, --help     output usage information
    -V, --version  output the version number
```

Congratulations! We are now ready to create our first app! Let's continue with the [next tutorial](/documentation?i=lisk-apps-docs/BasicApp).
