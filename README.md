A script that tracks incoming transactions from an rpc daemon using geth and javascript (and some jquery, no web3)

enviroment setup :

I spinned up a digital ocean droplet for faster syncing etc.

install geth in the droplet

sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum
sudo apt install geth

geth was failing to sync properly with 512 ram, added a 2G and set swapiness to 30.

Sync geth on the rinkeby network :

geth --rinkeby --rpc --rpccorsdomain "*"

5 hours later....

A full node is up on the rinkeby network...

On your local machine create tunnel on port 9001

ssh  -L 9001:127.0.0.1:8545 root@165.227.167.176  (thats my ip obviously and I am using a key for security)

Then you can attach to the remote geth :

geth attach http://localhost:9001

You can check if it is synced or not yet :

eth.syncing

and all the other api commands...

When synced, you can use index.html

You can connect metamask, create accounts and get some ether from the faucet and try sending receiving some eth on the rinkeby network




