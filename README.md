# info-node

Requires python3.6+

## Retrieve API key from panda-bot

Run $register command in DM or any channel with panda-bot present

## Git clone and update script

```
cd ~
git clone https://github.com/fat-panda-club/info-node.git
cd info-node
python3 -m pip install -r requirements.txt
vi panda_info_node.py
```

Insert values as follows:

| Attribute  | Description |
| ------------- | ------------- |
| CURRENCY_TICKER  | The ticker of your currency registered on panda-bot  |
| FAT_PANDA_CLUB_API_KEY  | panda-bot API key which you can obtain with $infonode  |
| INFO_NODE_HOST | IP of the live node |
| INFO_NODE_PORT | Port number of the live node |
| INFO_NODE_RPC_USERNAME | RPC User of the live node |
| INFO_NODE_RPC_PASSWORD | RPC Password of the live node |


The RPC settings are generally set in the daemon config similarly to below:

```
rpcuser=user
rpcpassword=pass
rpcport=123
rpcallowip=1.2.3.4/32 

```

## Create crontask 

Trigger every 5 minutes, replace with path to python3 and script location where applicable

`*/5 * * * * /usr/bin/python3 ~/info-node/panda_info_node.py`

## Set up info node 

Set up your blockchain node on the same or an alternate VPS with the configuration from above steps
Keep this node updated and in sync to ensure the correct stats are presented by panda-bot


## Notes

This will send your live node metric to panda-bot every 5 minutes, please do not increase the frequency as it will be rejected

If you'd like extra metrics to be monitored please [contact us via Discord](https://discord.gg/Hs57Jg4) and make a Pull Request
