# Sei-Network-About
Validator Name:Baranc
Hello, today I will show you how to create a Sei Network validator.What is Sei:Sei Network is the first orderbook-specific L1 blockchain. It is built using the Cosmos SDK and Tendermint core, and features a built-in central limit orderbook (CLOB) module. Decentralized applications building on Sei can build on top of the CLOB, and other Cosmos-based blockchains can leverage Sei's CLOB as a shared liquidity hub and create markets for any asset. 
Sei Shared Liquidity Model
Designed with developers and users in mind, Sei serves as the infrastructure and shared liquidity hub for the next generation of DeFi. Apps can easily plug-and-play to trade on Sei orderbook infrastructure and access pooled liquidity from other apps. To prioritize developer experience, Sei Network has integrated the wasmd module to support CosmWasm smart contracts.

# system requirements
```
4 CPU
16 RAM
500 SSD NVMe
```

# setup:
```
wget -q -O sei.sh https://api.rues.info/sei.sh && chmod +x sei.sh && sudo /bin/bash sei.sh
```

# To create a wallet. Type your own wallet name in the walletName field:
```
seid keys add walletName
```

# If you have joined before :
```
seid keys add walletName --recover
```
# Cüzdanımızı oluşturduktan sonra faucet'ı kullanalım: 

# Our node was matching when buying tokens, for check:
```
seid status 2>&1 | jq .SyncInfo
```

#  If you got false output, let's create validator:

# Customize parts such as creating validators, Moniker and From:
```
seid tx staking create-validator \
--moniker="monikername" \
--details="detail" \
--website="website" \
--amount=950000usei \
--pubkey=$(seid tendermint show-validator) \
--chain-id=atlantic-1 \
--commission-max-change-rate=0.01 \
--commission-max-rate=0.20 \
--commission-rate=0.10 \
--min-self-delegation=1 \
--from=name \
--yes
```
