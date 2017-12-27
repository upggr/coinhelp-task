Task for coinhelp

Spin up a digital ocean droplet for faster syncing etc.

install geth in the droplet

sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum

If this was a 512 MB droplet you need to add a 2G swap and set swapiness to 30

Sync get on the rinkeby network :
geth --rinkeby --rpc --rpccorsdomain "*"

On your local machine create tunnet on port 9001

ssh  -L 9001:127.0.0.1:8545 root@165.227.167.176

Then you can attach to the remote geth :

geth attach http://localhost:9001

You can check if it is synced or not yet :

eth.syncing



When synced, you can use index.html

You can connect metamask, create accounts and get some ether from the faucet and try sending receiving some eth on the rinkeby network

