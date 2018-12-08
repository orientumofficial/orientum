						     "Orientum: Own the Future"


Copyright (c) 2009-2018 Bitcoin Developers
Copyright (c) 2011-2018 Litecoin Developers
Copyright (c) 2018 Orientum Developers

What is Orientum?
----------------
http://www.orientum.io

Orientum (ORT) is a peer-to-peer and business-to-business cryptocurrency designed 
with a long-term vision in mind. We are determined to create a resilient digital 
currency that will play a pivotal role in the digital finance macrocosm of the 
future due to being built upon solid programming design and advanced financial 
technology with genuine usability and merchant integration.

Orientum is based on litecoin and bitcoin and uses scrypt as proof-of-work algorithm.
 - 3 minute block targets
 - 888888888 total coins
 - 3555555.552 coins per block (till 250th Block)
 - 480 blocks to retarget difficulty
 
 Web wallet: https://www.orientumwallet.website
 
 Explorer: http://explorer.orientumwall.website


License
-------

Orientum is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of Orientum depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to orientum folder. For that, go to the directory where orientum folder is located and then do:

sudo chmod -R 777 orientum/


 1.3 Compilation

After sucessfully giving all permissions, go to orientum folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running Orientum CLI

Once compilation successfully ends, you can run Orientum daemon with following steps:

a) Make sure you are in src folder of orientum ( your_directory/orientum/src )
b) Run: ./Orientumd -daemon
c) The above comamnd will create "data directory for orientum"(.Orientum folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.Orientum/Orientum.conf
It is recommended you use the following random password:
rpcuser=Orientumrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.Orientum/Orientum.conf
e) Run: nano /home/your_linux_username/.Orientum/Orientum.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to Orientum.conf file and save.
g) Run: ./Orientumd -daemon ( This time there won't be any error message )
h) Run: ./Orientumd getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running Orientum-qt (Linux GUI Wallet)

After successfully comiling Orientum CLI, you can proceed for Orientum-qt Wallet

a) Make sure you are in Orientum's root directory ( your_directory/orientum)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./Orientum-qt
e) You will see an Orientum-qt icon in your Orientum's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install Orientum GUI Wallet

2.2 Default Location of Orientum's root Directory in Windows is:
    
    32-bit: Program Files/Orientum
    64-bit: Program Files (x86)/Orientum

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/Orientum


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of orientum ( your_directory/orientum/src )

3.2 Run daemon: ./Orientumd -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./Orientumd getinfo

b) Check your Wallet's Balance: ./Orientumd getbalance

c) Check number of Nodes you are connected to: ./Orientumd getconnectioncount

d) Display Detailed information of Connedted Nodes: ./Orientumd getpeerinfo

e) Generate New Address for Wallet: ./Orientumd getnewaddress

f) Send some ORT amount to an ORT address: ./Orientumd sendtoaddress <ORT Address> <Amount>
   example: ./Orientumd sendtoaddress RVFWg6saZ4L6yvaJso14y2YpRD5hGPNVEL 0.888

g) View all transactions in your wallet: ./Orientumd listtransactions

h) Encrypt CLI and GUI Wallet: ./Orientumd encryptwallet <passphrase>
   example: ./Orientumd encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./Orientumd walletpassphrase <passphrase> <timeout>
   example: ./Orientumd walletpassphrase theahard*&password!! 120

j) Change Wallet Passphrase: ./Orientumd walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./Orientumd walletpassphrase thehard*&password!! thenew%^password

