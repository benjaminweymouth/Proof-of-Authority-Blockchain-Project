# Blockchain POA: ZBank Blockchain TestNet. 


##  Environment setup instructions and dependencies.

1) install Go Ethereum (Geth link: https://geth.ethereum.org/downloads/) and install into a folder named as Blockchain-Tools
2) install MyCrypto (MyCrypto link: https://mycrypto.com/) 



## Concepts and Analysis: Blockchain, BlockTime, ChainID, NetworkID.

This exercise will refer to a number of concepts directly and indirectly. It is important to understand these key concepts. 

Blockchain: A Blockchain is a computing architecture that utilizes distributed processing and cryptography in order to create a secure, immutable and decentralized ledger upon which transactions and be made without the need for a centralized clearing authority. This form of distributed computing is utilized in this exercise to demonstrate how a blockchain can be spun up and leveraged to facilitate transactions between ethereum wallets. However, the Blockchain goes far beyond the scope of this exercise and is a continually changing and fundamentally altering various incumbant industrial transactions. 

Blocktime: The block time refers to the amount of time it will take one node or miner to complete the verification process for a transaction. This is an important concept because if the block time is too high, it will make for very slow transactions. At peak volumes a high block time could create a backlog of transactions which is an undesireable circumstance. 

Chain ID: On the Ethereum network there are various chains, some of which may be the official Ethereum chain, while others may be for testing, like the ropsten chain. A Chain ID will identify the chain you wish to connect to. In order to connect to a different chain you would specify the chain ID.  

## Puppeth and Geth Commands 

Various commands will be required to setup the blockchain, nodes and activate them. 

1) First, navigate to the blockchain-tools folder you created 
2) Open a GitBash terminal in that folder (on Windows can right-click and then "Git Bash Here) 
3) navigate to the Blockchain-Tools folder and type the following command: ./puppeth


## Step-by-Step with ScreenShots 


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


