# Creating a Basic App

Moving on to our next tutorial, let's create our first app using **Lisk CLI**, an automated tool for bootstrapping Lisk based blockchain applications.

## GitHub Repository

Before we start, we first need to create a repository to store our app's source code.

[Log into](https://github.com/login) your [GitHub](https://github.com/) account, and [create a new repository](https://help.github.com/articles/create-a-repo/) using a name of your choosing.

The repository can be **public** or **private**, depending on your preference.

## Unique Genesis Block


Let's go back to our terminal and list the content of your client folder we have installed previously (for instance  in `lisk-0.1.2-Linux-x86_64/`, your folder name can be different), and verify you have the following files:

```text
> cd lisk-0.1.2-Linux-x86_64/
> ls
app.js config.json lib nodejs public bin genesisBlock.json lisk.sh package.build share build include
```

We will generate a new app into the dapps/ directory using the command line `lisk-cli`. This will create a new unique genesis block, which we will use to test our app.

To do so, enter the following command inside `lisk-0.1.2-Linux-x86_64/`:

```text
lisk-cli dapps -a
```

This command will ask you a few important questions:

```text
? Existing blockchain.db file will be replaced, are you sure?
? Enter secret of your testnet account
? Overwrite the existing genesis block?
? Enter DApp name
? Enter DApp description
? Enter Github clone url
? Enter public keys of dapp forgers - hex array, use ',' for separator
? Add DApp to autolaunch
```

Each question is further described below:

* **Existing blockchain.db file will be replaced, are you sure?**

Answering **yes** will replace the existing blockchain.db, the file in which your app's blockchain resides.

* **Enter secret of your testnet account**

Enter a password of your choosing. **Important**: Keep a record of your password, otherwise you will need to regenerate the genesis block.

* **Overwrite the existing genesis block?**

Answering yes will overwrite the existing genesis block, including delegates and any previous apps. **Important**: Answer **yes** if this is the first time you have launched **lisk-cli** for a given app.

* **Enter DApp name**

Enter the name of your app, e.g. `myFirstApp`.

* **Enter DApp description**

Enter a brief description of your app's intent and purpose.

* **Enter Github clone url**

Enter the clone url to your app's github repository. **Important**: Enter the SSH based clone URL, for example: `git@github.com:username/myFirstApp.git`

* **Enter public keys of dapp forgers - hex array, use ',' for separator**

Enter the public key of each account which will forge the side chain of your app. **Note**: The public key of the testnet account is added by default.

Separate each public key with a comma like so: `key1,key2,key3`

* **Add DApp to autolaunch**

Answering **yes** will set your app to automatically launch upon starting Lisks.

### Example

Below is an example of how to create a test app using **Lisk CLI** with the corresponding output:

```text
? Existing blockchain.db file will be replaced, are you sure? Yes
? Enter secret of your testnet account ******
? Overwrite the existing genesis block? Yes
? Enter DApp name test
? Enter DApp decription test
? Enter Github clone url git@github.com:username/myFirstApp.git
Generating unique genesis block...
? Enter public keys of dapp forgers - hex array, use ',' for separator (808c2a6e3bf0a8a6edd64356e98c8aab4daeacb4dc177a8a20a6442b40d1f0e0)
Creating DApp genesis block
Fetching Lisks DApp Toolkit
Connecting local repository with origin
Saving genesis blocks
Updating config
? Add DApp to autolaunch Yes
Done (DApp id is 16595324874141671114)
```

Upon successful completion, the **Lisk CLI** will return the app's unique id, in this case: **16595324874141671114**.

If you answered **Yes** to autolaunch the app, then you can launch it by starting Lisks, using the following command:

```text
node app.js
```

Once Lisks has loaded, your app should have launched. To verify this, simply open your browser with the following link: [http://localhost:7000/dapps/[appid]/](http://localhost:7000/dapps/[appid]/), replacing **[appid]** with your app's own unique identifier.

All done! In the [next tutorial](/documentation?i=lisk-dapps-docs/MessagingApp), we describe how to make a new Messaging App using Lisks's App SDK.
