# Writing a smart contract with Solidity

This repo is almost exactly based on a project developed by [Buildspace](https://buildspace.so/) team. 

If you'd like to do it yourself, please take a look at <b>Build a Web3 App with Solidity + Ethereum Smart Contracts</b> which is developed by the Buildspace team. It allows you to write a smart contract with very little prior knowledge about blockchain.

One of the main component of this project is `contracts/WavePortal.sol`. Although it's a very simple contract but it allows you to understand how smart contracts work.

This project is reliant on another [repo](https://github.com/ROZBEH/front-end-eth-smart-contract) for the frontend part. More on that later.

In this smart contract, we will be asking people to send us a message/wave and in return they have a 50% chance of receiving fake ethereum. This is just a simple example to get familiar with the concept of smart contract. Basically we are using a piece of software, in our case `WavePortal.sol` in order to handle financial and non-financial interactions between people. For our example, the contract is `If I wave at you, you have the obligation to send me fake eth with 50% chance`. Without the need for a human to intervene, we can run contracts and agreement between people. Once the contract goes live, if the condition satisfies the contract and agreement will be implemented. No one can stop this even the most powerful person in the world. There is only one way where the contract can be stopped and that is for the whole Ethereum network to shut down. 

This is a contract, right? As the writer of this contract you can add whatever requirements that you'd like as long is it doesn't scare the other party in the contract. For example, in order to stop users from spamming us, we put a requirement so that they can't wave at us incessantly. Basically as the following shows, we require them to wait for 30 minutes before sending us the next message/wave.

```
require(
            lastWavedAt[msg.sender] + 30 minutes < block.timestamp,
            "Wait for 30 minutes before sending the next message"
        );
```