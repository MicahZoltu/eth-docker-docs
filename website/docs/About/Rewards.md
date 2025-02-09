---
id: Rewards
title: Chain Rewards	 
sidebar_label: Chain Rewards
---

Validators that participate in securing the beacon chain and execute "duties" get rewarded for this by new issuance of ETH. In addition, post-merge, validators will receive priority fees paid by users, and optionally MEV, Maximal Extractable Value.

1) Validator rewards


Validators have three duties: Attestations, once every epoch; block production, once every few weeks; sync committees, once every two years or so, on average. Block production and sync committees are randomly assigned, and the time between them therefore varies widely for any one validator. 

They are rewarded for executing those duties by new ETH issuance to the "validator balance". The current APY can be seen on the [official launchpad](https://launchpad.ethereum.org/).

If the validator is down and not executing its duties, it will be penalized at a rate slightly lower than the rewards for the same period of time.

Rewards will be able to be withdrawn sometime after merge, with the first scheduled hardfork after, "Shanghai".

2) Priority fees

Users of Ethereum set a [priority fee](https://ethereum.org/en/developers/docs/gas/#priority-fee) for their transactions. This fee is paid to block proposers and is immediately liquid. In order for that fee to be paid, a `--suggested-fee-recipient` needs to be configured. This is why eth-docker prompts for an Ethereum address to send priority fees to.

This address could be a hardware wallet, a software wallet, or even a multi-sig contract.

3) MEV

[MEV](https://ethereum.org/en/developers/docs/mev/), or "maximal extractable value", is a controversial topic. Node operators can extract MEV by accepting blocks built by "searchers", via a small side program called ["mev-boost"](https://ethresear.ch/t/mev-boost-merge-ready-flashbots-architecture/11177) by Flashbots. In this case, the CL ... Consensus Layer client such as Nimbus, Teku, &c ... will, when asked to procure a block to propose, get blocks from MEV relays via mev-boost and from the EL, and then choose whichever block pays best. For this, the relay has to be trusted to deliver valid blocks.

Rewards from MEV are paid to the same `--suggested-fee-recipient` address that priority fees go to.
 
