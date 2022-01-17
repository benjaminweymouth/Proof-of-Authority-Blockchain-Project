# Blockchain POA: ZBank Blockchain TestNet. 

This repo is for setting up a custom development chain, create documentation for others on how to start it using the pre-configured
nodes and accounts.

Create a new project directory for your new network. Call it whatever you want!


Create a "Screenshots" folder inside of the project directory.


Create accounts for two (or more) nodes for the network with a separate datadir for each using geth.


Run puppeth, name your network, and select the option to configure a new genesis block.


Choose the Clique (Proof of Authority) consensus algorithm.


Paste both account addresses from the first step one at a time into the list of accounts to seal.


Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.


You can choose no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.


Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.


Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.


You can delete the networkname-harmony.json file.


Screenshot the puppeth configuration once complete and save it to the Screenshots folder.


Initialize each node with the new networkname.json with geth.


Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.


Set a different peer port for the second node and use the first node's enode address as the bootnode flag.


Be sure to unlock the account and enable mining on the second node!


You should now see both nodes producing new blocks, congratulations!



Send a test transaction


Use the MyCrypto GUI wallet to connect to the node with the exposed RPC port.


You will need to use a custom network, and include the chain ID, and use ETH as the currency.

## Set-up Information 
This section includes some preliminary setup information, such as installing dependencies and environment configuration.


