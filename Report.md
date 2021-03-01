# ZCOIN: THE GENESIS

For this homework, I pretty much worked with my tutor and followed the POA creation instructions.<br><br>

First, I created two new accounts by using the <strong>./geth --datadir NODENAME account new</strong>. In doing so, I was given both the public address and path of the secret key file, both of which I recorded.<br><br> 

Once that was done, I went in and created the genesis block. I named my network <strong>zcoin</strong>, followed the options which included choosing <strong>POA</strong>, inserting the public addresses I previously created for sealing and pre-funding (I chose not to) and entered a Chain ID.<br><br>

I made it back to the main menu and chose to <strong> manage the existing genesis </strong> and export the genesis configs. This option created a <strong>zcoin.json</strong> and <strong>zcoin-harmony.json</strong> in the geth directory where my nodes were also stored. I opted not to delete the harmony file, even though I could.<br><br> 

Once all this was done, it was time to face the nodes. Step 1 was to initialize the nodes using the <strong>./geth --datadir NODENAME init networkname.json</strong> command for both nodes. Then I entered the commands in two separate terminal windows to run the nodes. This was slightly trickier as the commands are different because one node mines while the other is a transaction node. In addition, the nodes run on two different ports and the second node contains the enode address of the first. Here is an example:<br><br>

> ./geth --datadir node1z --unlock "7BD790809B8dBEEF3135295ED5FC8fDCa7020Ee9" --mine --minerthreads 1 <br><br>
>
> ./geth --datadir node2z --unlock "9B0f6e96D1b5E261E8CF7AB98F591797EF479628" --port 30304 --rpc --bootnodes "enode://073a16131cdd6bffd40200279f89dd71a7c40f0f0f487c5e0eeeb0a45833c5327ccd0fb646365195099938d6fa301f97bb79029e3397b72077c551a8c7849613@127.0.0.1:30303" --allow-insecure-unlock <br>

<br>Once I put in my password and had these up and running (peered with each other but searching for more), I created a new network on MyCrypto using my ChainID and making sure to leave the currency in ETH. Once this was done, the next step was to access the wallet using the keystore file and password  and sending ETH from node 1 to node 2. 






