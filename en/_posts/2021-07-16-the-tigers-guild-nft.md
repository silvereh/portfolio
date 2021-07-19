---
title: The Tigers Guild NFT
tags: [Solidity, Web3js, python]
lang: en
categories: [en]
summary: The Tigers Guild had hired a bad developer for their smart contract. They hired me to redo their whole contract and achieve a successful launch.
thumbnail: 
---
## Context

I've been getting interested in the NFT and blockchain space recently. I learned how to code smart contracts for the Ethereum blockchain in Solidity and needed to find a project to work on to complete that training with actual experience. That's when I met [The Tigers Guild][1]. They had hired a bad developer for their smart contract, who left them with a failed NFT launch, tokens with no visible metadata, and a disappointed community. They hired me in catastrophe to fix it.

[1]: https://thetigersguild.com/ "Welcome to the tigers guild - the first fully 3d animated tiger nfts to take over the jungle!"

## Processus

I started by making sure I understood their needs, what the contract needed to reflect, and any specific functionality that was needed. Next, I studied in more details the interfaces concerned with the project, the ERC 721 contract, to determine how to accomodate thoses need within that framework. I then developed the contract according to the specifications I determined, taking example on other published contracts like Bored Apes Yacht Club, Cool Cats, and Boring Bananas. Next, I asked my community of developers to review the contract to ensure there was no obvious mistakes in there. And I finally guided the team in their publication of the contract on the Ethereum blockchain.

## What I learned

Of course, as any first experience, this project didn't go without hiccups, and I learned a lot from them. First thing first, the contract. Deploying a smart contract is not free, it cost about 0.08 ETH to deploy a standard contract on the Ethereum blochain, which translate to approximately $150 USD (at the time of writing). That means that a failed contract is a big dip on an individual's budget. It is therefore capital to do **very thorough** testing and checking on test networks before deploying a contract. There exist [several resources][2] to get test ETH on your wallet in order to ensure proper testing, and [OpenSea][3], the number 1 platform for selling NFTs on Ethereum offers a [free facade to test networks][4], which is meant to allow developers to ensure that their NFTs will mint properly and that their metadata will be properly detected by their API.
Unfortunately, we were not able to connect properly to the testnet facade of OpenSea. Our wallets would try to connect to it with our mainnet accounts instead of testnet, which made us unable to realize before the final deployment that our NFTs' metadata were invisible to OpenSea... After digging more intensely in the testnet logs, I eventually understood that our tokens were not exposing their metadata to the public because of a simple mistake, I had forgotten to override the method exposing them, `tokenURI()`.

[2]: https://www.2key.network/blog-posts/what-is-ropsten-eth-and-how-can-i-get-some "A list of faucets to get test ETH for the Ropsten test network"
[3]: https://opensea.io "A peer-to-peer marketplace for NFTs, rare digital items and crypto collectibles. Buy, sell, auction, and discover CryptoKitties, Decentraland, ..."
[4]: https://testnets.opensea.io/ "A test network version of the peer-to-peer marketplace for NFTs, rare digital items and crypto collectibles. Buy, sell, auction, and discover CryptoKitties, Decentraland, ..."

By the time I realized that first mistake, we were already only 9 hours away from launch time, which leads to the second very important thing I learned from this project, deploying a contract takes time, and so does updating all Web3 references to a contract, especially when working with a remote team spread around the globe. When the contract was finally fixed and redeployed, the backend developer was not available to update the references across the project... We were forced to postpone our launch to ensure that the correct contract was connected to our website and that our customers would actually mint the correct token.
Postponing our launch in that manner forced us to do more giveaways in the meantime to maintain engagement with the community and keep their trust.

And with more giveaways comes another very important learning. Manual airdrop is terribly long and inefficient, in addition to the gas cost of airdropping a lot of tokens, in a lot of transactions... It took several days to deliver the more than 200 airdrops that were necessary, which cost close to 1 or 2 ETH total. The irony of the situation is that I found [a resource to do batch airdrop][5] only a few hours after we finally finished the manual airdrops. I should now be able to handle that in the future.

[5]: https://nft.multisender.app/ "A tool to do batch NFT airdrop"
