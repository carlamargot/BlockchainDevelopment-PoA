# BlockchainDevelopment-PoA

![image](https://user-images.githubusercontent.com/73208140/117193868-63cb0c00-adb1-11eb-9e33-8a6d4ccf2d60.png)

## How to set up a private blockchain 

Welcome! This is a step-by-step guide to meant to help you get started with developing a private blockchain and send some practice crypto (testnet). 
* Note: these steps are for MAC users. 

What is a Proof of authority blockchain, you ask? 

A Proof of authority (PoA) blockchain is often used between two parties who don't always trust eachother interact. Validators (pre-approved participants) moderate the interactions between parties.

# Step 1: Setting yourself up for success 

Before we begin with the fun stuff you'll need to download a few programs.

# MyCrypto App 

1. Open your browser and navigate to the downloads page at https://download.mycrypto.com/.
2. Depending on your operating system, you will be redirected to the corresponding application installer. If you are not correctly redirected, choose the appropriate installer for your operating system.
3. Once you download the installer, open the file, and follow the installation wizard. 

![image](https://user-images.githubusercontent.com/73208140/117089062-67638200-ad22-11eb-9914-fd9219572b06.png)

* Note: The first time you execute MyCrypto, you will see the following warning message, you can safely click on the "Open" button to start the application.

Running in OS X:

The first time you execute MyCrypto, you will see the following warning message, you can safely click on the "Open" button to start the application.

![image](https://user-images.githubusercontent.com/73208140/117094493-edd39000-ad31-11eb-9d04-9bcd7ba84384.png)

Allowing Permission to Open Apps from Unidentified Developers
When an app is not registered with Apple, it can be automatically blocked by the Mac OS operating system when attempting to open the "unidentified" application. Therefore, in order to allow the use of the MyCrypto app, you may need to allow it as an exception to your Mac OS security preferences. To do so perform the following.

1. Open the MyCrypto app, it should produce a warning error saying that you cannot open the application due to security reasons. Therefore, we'll need to make a security exception for it.
2. Look to the top-left of the screen and click on the Apple Logo and navigate to System Preferences > Security & Privacy.

![image](https://user-images.githubusercontent.com/73208140/117094576-22474c00-ad32-11eb-8ba2-35b028cd2471.png)

3. Click in the General tab and allow your MyCrypto application security access to be opened in the "Allow Apps Downloaded From" section. Your screen should look similar to the image below.

# Go Ethereum Tools

We will use Go Ethereum Tools to create our very own blockchain, from the genesis block to mining tokens and making transactions.

To install the Go Ethereum Tools, please follow the next steps:

1.Open your browser and navigate to the Go Ethereum Tools download page at https://geth.ethereum.org/downloads/
2.Scroll down to the "Stable Releases" section and proceed depending on your operating system.
3. Installing on OS X. Click on the "Geth & Tools 1.9.7" to download the applications bundle archive.

![image](https://user-images.githubusercontent.com/73208140/117090196-ad6e1500-ad25-11eb-9c43-b2f69e363c76.png)

4. After downloading the tools archive, open your "Downloads" folder, and you will find a file named geth-alltools-darwin-amd64-1.9.7-a718daa6.tar.gz in OS X, and a file called geth-alltools-windows-amd64-1.9.7-a718daa6.zip in Windows. Note that the last numbers in the filename could vary depending on the last built available.

5. Decompress the archive in the location of your preference in your computer's hard drive, and rename the containing folder as Blockchain-Tools. We recommend using a location that can be easily accessed from the terminal window like the user's home directory.

# Now for the fun stuff! 

## Setting up your blockchain

1. Using your terminal navigate to your "Blockchain-Tools" folder and initiate (just a fancy way of saying type this in) geth using ./geth 

2. Because the accounts must be approved, we will generate two new nodes with new account addresses that will serve as our pre-approved sealer addresses.
Create accounts for two nodes for the network with a separate datadir for each using geth.
./geth --datadir node1 account new
./geth --datadir node2 account new
* Note: You will need to create a password however, when you enter it you will not be able to see what you are typing, don't worry this is totally normal! Please be sure to write your password down. 
* Important!! You will need to copy & store the public key's for both nodes. Please be sure to store this information somewhere accessible and safe. In my case I used Notes. 

3. In your "Blockchain-Tools" folder run the command ./puppeth. You should see something like this. 

<img width="423" alt="Screen Shot 2021-05-05 at 3 12 11 PM" src="https://user-images.githubusercontent.com/73208140/117196272-48153500-adb4-11eb-961a-3e28fc9ff600.png">

4. Once you are here, you will be asked to name your network and be prompted with several questions. 
    - Choose the Clique (Proof of Authority) consensus algorithm. (Enter 2)
    - Choose "Create new genesis from scratch" (Enter 1)
    - Choose " Clique - proof-of-authority" (Enter 2)
    - Leave this question blank "How many seconds should blocks take? (default = 15)" by hitting enter 
    - Paste both account addresses without the 0x from the first step one at a time into the list of accounts to seal. 
    - Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.
    - Answer No for "Should the precompile-addresses (0x1 .. 0xff) be pre-funded with 1 wei? (advisable yes)". This keeps the genesis cleaner. 
    - Create a "Chain ID" a series of 4 numbers. REMEMBER these numbers. It is advisable to store them with you public keys. 
    Congrats! You have your first genesis block! You should see "Configured new genesis block" just below your Chain ID. 
    - Now for "What would you like to do?" Enter 2 for "Manage exisiting genesis" and for the following prompt. 
    - Here you can either name a file to store your genesis or hit enter to skip this step.  If you choose to skip this step the specs will save in "Blockchain-Tools" file. 
 
    - Once you are back at the main menu, exit using control c. 
 5. We will now initialize the nodes with the genesis' json file.
    Using geth, initialize each node with the new networkname.json.

        ./geth --datadir node1 init networkname.json
        ./geth --datadir node2 init networkname.json
        
    * Remember: networkname is referring to YOUR network name. Refer to number 4. 
  6. Now the nodes can be used to begin mining blocks.
     In this window, enter ./geth --datadir node1 --unlock "YOURPRIVATEKEYHERE" --mine --rpc --allow-insecure-unlock
     * This must be the private key for you node1. 
     * When this block has started to mine, be sure to say the enode with the rest of the information for your node1. You will find the encode number where it reads " Started P2P networking ". Please copy everything including the word enode! 
     
     <img width="164" alt="Screen Shot 2021-05-05 at 3 45 12 PM" src="https://user-images.githubusercontent.com/73208140/117199994-e3a8a480-adb8-11eb-8caa-f62fa9379dca.png">

  7. In the same terminal, open another tab (press: Command t, for short) and enter 
