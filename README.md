# BlockchainDevelopment-PoA
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

## Now for the fun stuff! 

# Setting up your blockchain

1. Using your terminal navigate to your "Blockchain-Tools" folder and initiate geth using ./geth 
It should look something like this. 
<img width="1440" alt="Screen Shot 2021-05-04 at 11 51 28 PM" src="https://user-images.githubusercontent.com/73208140/117095180-a817c700-ad33-11eb-9ee2-d25ee4d914a0.png">
2. Because the accounts must be approved, we will generate two new nodes with new account addresses that will serve as our pre-approved sealer addresses.
Create accounts for two nodes for the network with a separate datadir for each using geth.
./geth --datadir node1 account new
./geth --datadir node2 account new
* Note: You will need to create a password however, when you enter it you will not be able to see what you are typing, don't worry this is totally normal! Please be sure to write your password down. 
It should look like this. 

<img width="895" alt="Screen Shot 2021-05-04 at 11 59 19 PM" src="https://user-images.githubusercontent.com/73208140/117095592-c03c1600-ad34-11eb-8a81-a28a019a5f0e.png">


