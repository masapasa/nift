# nft-mix

<br/>
<p align="center">
<a href="https://chain.link" target="_blank">
<img src="https://raw.githubusercontent.com/smartcontractkit/chainlink-mix/master/img/chainlink-brownie.png" width="225" alt="Chainlink Brownie logo">
</a>
</p>
<br/>

This is a repo to work with and use NFTs smart contracts in a python environment, using the Chainlink-mix as a starting point. 

If you'd like to see another repo using random NFTs that are deployed to mainnet, check out the [D&D package](https://github.com/PatrickAlphaC/dungeons-and-dragons-nft).

## Prerequisites

Please install or have installed the following:

- [nodejs and npm](https://nodejs.org/en/download/)
- [python](https://www.python.org/downloads/)
## Installation

1. [Install Brownie](https://eth-brownie.readthedocs.io/en/stable/install.html), if you haven't already. Here is a simple way to install brownie.

```bash
pip install eth-brownie
```

2. Clone this repo
```
git clone https://github.com/PatrickAlphaC/nft-mix
cd nft-mix
```

3. [Install ganache-cli](https://www.npmjs.com/package/ganache-cli) and [openzepplin contracts](https://github.com/OpenZeppelin/openzeppelin-contracts)

```bash
npm install -g ganache-cli
npm install @openzeppelin/contracts
```


If you want to be able to deploy to testnets, do the following. 

Set your `WEB3_INFURA_PROJECT_ID`, and `PRIVATE_KEY` [environment variables](https://www.twilio.com/blog/2017/01/how-to-set-environment-variables.html). You can get this by getting a free trial of [Infura](https://infura.io/). At the moment, it does need to be infura. You can find your `PRIVATE_KEY` from your ethereum wallet like [metamask](https://metamask.io/). 

For those not familiar with environment variables, just run:
```
export WEB3_INFURA_PROJECT_ID=<PROJECT_ID>
export PRIVATE_KEY=<PRIVATE_KEY>
```
Just know, that when you restart your shell/terminal, these environment variables are removed. 

# Useage

There are 2 types of NFTs here. 
1. `SimpleCollectibles.sol`
2. `AdvancedCollectibles.sol`

They each deploy unique dogs. The advanced version gives you a random breed (out of a Pug, Shiba Inu, and St. Brenard).

The advanced collection uses a [Chainlink VRF](https://docs.chain.link/docs/get-a-random-number) to deploy the random dog. 

### Running Scripts

The simple collectibles work on a local network,  however the advanced requires a testnet. We default to rinkeby since that seems to be the testing standard for NFT platforms.

# For the Simple ERC721
```
brownie run scripts/simple_collectible/deploy_simple.py
brownie run scripts/simple_collectible/create_collectible.py
```

# For the Advanced ERC721

You'll need [testnet Rinkeby](https://faucet.rinkeby.io/) and [testnet LINK](https://rinkeby.chain.link/) in the wallet associated with your private key. 

```
brownie run scripts/advanced_collectible/deploy_advanced.py --network rinkeby
brownie run scripts/advanced_collectible/fund_collectible.py --network rinkeby
brownie run scripts/advanced_collectible/create_collectible.py --network rinkeby
```

## Testing

```
brownie test
```
(Tests are weak at the moment)

## Resources

To get started with Brownie:

* [Chainlink Documentation](https://docs.chain.link/docs)
* Check out the [Chainlink documentation](https://docs.chain.link/docs) to get started from any level of smart contract engineering. 
* Check out the other [Brownie mixes](https://github.com/brownie-mix/) that can be used as a starting point for your own contracts. They also provide example code to help you get started.
* ["Getting Started with Brownie"](https://medium.com/@iamdefinitelyahuman/getting-started-with-brownie-part-1-9b2181f4cb99) is a good tutorial to help you familiarize yourself with Brownie.
* For more in-depth information, read the [Brownie documentation](https://eth-brownie.readthedocs.io/en/stable/).


Any questions? Join our [Discord](https://discord.gg/2YHSAey)

## License

This project is licensed under the [MIT license](LICENSE).
