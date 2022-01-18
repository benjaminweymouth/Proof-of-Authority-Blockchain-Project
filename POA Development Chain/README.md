# Blockchain POA: ZBank Blockchain TestNet. 


##  Environment setup instructions and dependencies.

1) install Go Ethereum (Geth link: https://geth.ethereum.org/downloads/) and install into a folder named as Blockchain-Tools
2) install MyCrypto (MyCrypto link: https://mycrypto.com/) 



## Concepts and Analysis: Blockchain, BlockTime, ChainID.

This exercise will refer to a number of concepts directly and indirectly. It is important to understand these key concepts. 

<em>Blockchain:</em> A Blockchain is a computing architecture that utilizes distributed processing and cryptography in order to create a secure, immutable and decentralized ledger upon which transactions and be made without the need for a centralized clearing authority. This form of distributed computing is utilized in this exercise to demonstrate how a blockchain can be spun up and leveraged to facilitate transactions between ethereum wallets. However, the Blockchain goes far beyond the scope of this exercise and is a continually changing and fundamentally altering various incumbant industrial transactions. 

<em>Blocktime:</em> The block time refers to the amount of time it will take one node or miner to complete the verification process for a transaction. This is an important concept because if the block time is too high, it will make for very slow transactions. At peak volumes a high block time could create a backlog of transactions which is an undesireable circumstance. 

<em>Chain ID:</em> On the Ethereum network there are various chains, some of which may be the official Ethereum chain, while others may be for testing, like the ropsten chain. A Chain ID will identify the chain you wish to connect to. In order to connect to a different chain you would specify the chain ID.  

## Step-by-Step with ScreenShots and Commands 

Various commands will be required to setup the blockchain, nodes and activate them. 

1) First, navigate to the blockchain-tools folder you created 
2) Open a GitBash terminal in that folder (on Windows can right-click and then "Git Bash Here) 
3) Navigate to the Blockchain-Tools folder and type the following command: ./puppeth


## ScreenShots Step-by-Step setting up a Blockchain Network (using Go Ethereum)  


Setting up accounts for two (or more) nodes for the network with a separate datadir for each using geth.


Using geth, initialize each node with the new account.

./geth --datadir node1 account new <br> 


![Screenshot: setting up Node1](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/Node1.PNG)

./geth --datadir node2 account new

![Screenshot: setting up Node2](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/Node2.PNG)



## Creating the Network and Genesis Block

Running puppeth, name your network, and select the option to configure a new genesis block.

![Screenshot: setting up network in Puppeth](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture1.PNG)

Configuring a new genesis block.


![Configuring a new genesis block](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture2.PNG)


## Setting up the Proof of Authority Consensus Algorithm. 

Screenshot showing the following steps: 

- Choosing the Clique (Proof of Authority) consensus algorithm.
- Pasting both account addresses from the first step one at a time into the list of accounts to seal.
- Pasting both again in the list of accounts to pre-fund. There are no block rewards in PoA, so pre-funding
- Choosing no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.

![Choosing the Clique for POA](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture3.PNG)

Screenshots showing the following steps: 

- Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.
- Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.


![Complete the rest of the prompts](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture4.PNG)

- Screenshot showing the nodes and json file (Did delete the other networkname-harmony.json file.)

![Complete the rest of the prompts](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture5.PNG)




## Initializing the Nodes on the BenjaminCoin Network  (using Go Ethereum)  


Initialize each node with the new networkname.json with geth.

Screenshot and code for geth, initialize each node with the new networkname.json.
<br> 
./geth --datadir node1 init benjamincoin.json <br> 
./geth --datadir node2 init benjamincoin.json

<br>
 

![Initialize each node](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture6.PNG)

## Running the Nodes to start Mining  (using Go Ethereum)  
Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.
Code for CLI: 

./geth --datadir node1 --unlock "PublicaddressNODE1" --mine --rpc --allow-insecure-unlock


![Start mining Node1](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture7.PNG)

Starting Node 2 for Mining, setting a different peer port for the second node and use the first node's enode address as the bootnode flag. Unlocked the account and enable mining on the second node.

Code for Geth: 

./geth --datadir node2 --unlock "PublicaddressNODE2" --mine --port 30304 --bootnodes "ENODE" --ipcdisable --allow-insecure-unlock

Node 2 mining new blocks: 
![Both new blocks](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture17.PNG)


Both nodes producing new blocks: 
![Both new blocks](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture16.PNG)


## ScreenShots Step-by-Step sending a Test Transaction 

Use the MyCrypto GUI wallet to connect to the node with the exposed RPC port.

In MyCrypto Using KeyStore to open wallet. Check node1 folder for KeyStore.  
![KeyStore to open wallet](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture9.PNG)

Check Wallet Balance on MyCrypto
![KeyStore to open wallet](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture10.PNG)

You will need to use a custom network, and include the chain ID, and use ETH as the currency.
![use a custom network](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture11.PNG)

Confirming the Transaction in MyCrypto

![Confirming the Transaction in MyCrypto](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture12.PNG)

Broadcasting the Transaction to the Network 

![Transaction to the Network ](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture13.PNG)

Checking the Transaction

![Checking the Transaction](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture14.PNG)

A Successful Transaction

![Successful Transaction](https://github.com/benjaminweymouth/Blockchain-Work/blob/main/POA%20Development%20Chain/Screenshots/benjamincoin/Capture15.PNG)


