## Why SOLANA is assuming to be a "Ethereum Killer"

## Introduction
Solana is one of the most performant permissionless blockchain in the world. But before that let's talk about what we have now. Ethereum blockchain was released in 2015  which proves to be a breakthrough in the blockchain world where people not only use it as a cryptocurrency but more than that they can upload their code on Ethereum blockchain which we call a Smart Contract to make decentralised applications, NFTs and an enormous amount of possibilities unlocked with it.


## But what's the need for SOLANA

- ####   It claims to solve the Blockchain Trilemma
Termed by Vitalik buterin the co-founder of Ethereum that all blockchain projects revolve around three core concepts which are Scalability, Decentralization and Security at one given time a blockchain can have two qualities and need to compromise on the third one.
This trade-off is called Blockchain Trilemma and Solana claims that they have solved this trilemma 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660202605517/kriXR0ZRW.png align="center")
 
- <h4> Transaction per second  </h4>

All these years Ethereum works well but in terms of dapps or decentralised applications which can be a web-Application like Facebook or Instagram but powered through a decentralised network like Ethereum. And there is a term called transaction per second(TPS) which means every action we do like liking a picture or posting a new photo on this dapps is termed as a transaction and for these transactions blockchain scales themselves.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660194814395/vwvZ6xR5n.png align="left")

For Ethereum, tps is around 15 tps but for Solana, it is about 65000 per second which is a major difference.

- <h4>Trasaction Cost</h4>

For each transaction we have discussed, there is a Gas fee linked to the transaction which applies whenever we do a transaction like posting a new image and this transaction cost can be as much high as 4-5 dollars for every transaction.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660195501019/eE1QBmD-d.png align="left")

- <h4> <li>Block Time </li></h4>

Block time means after reaching a certain amount of transactions these transactions are bundled into a block with some cryptographic hashing algorithms and this block will be made by anyone validator. How this validator is selected will talk about it later on but the point is that for bitcoin this block time is about 10 min and for Ethereum, it's about 15 sec. That means no matter what happens you will have to wait at least 15 sec to get your transaction done and reflect on the blockchain. Imagine reacting to a photo or uploading a photo on dapps takes this much time will not gonna be a good experience at all.

Whereas this block time is about 0.4 seconds for Solana and these are some of the huge perks in a decentralised environment where Solana is the closest to the current internet that we have in web2.


##  How Solana has achieved all of this? 

Like every other blockchain, Solana has also a consensus mechanism. In the above title of Block Time, we have talked about how the validators got selected. This consensus mechanism helps to select a validator such that it is transparent to everyone and every other node or participant in the blockchain has an equal chance of being a validator. Now there are many consensus mechanisms but we will talk about some top consensus.

- ###  Proof of Work (POW) -: 
POW consensus gives all the node participants a set of the puzzle. This puzzle is a mathematical problem and all the computers try to find the hash or solution of this puzzle now this puzzle is made in such a way that the more powerful computer is, the more easily it will solve the problem and the fastest to solve this puzzle will get a chance to make the block on the existing chain. Solidity and Bitcoin follow POW but this consensus has its own drawbacks like this mechanism is very slow in terms of TPS and Block Time. 

- ###   Proof of Stack (POS) -: 
POS consensus works in such a way that the validator who wanted to mine a block. He has to stake some of his coins and whosoever will stake the highest amount of currency will get a chance to mine a block. The block that the validator mined is verifiable by other nodes but if they improperly validate bad or fraudulent data then the validator's stake will be seized. 

Ethereum is also planning to transfer its mechanism from proof of work to proof of stake this will immensely increase its TPS from 15 to 100,000. But the catch here is that although the transaction per second will increase the block time will be changed from 15 seconds to somewhere around 12.5 seconds and all other blockchains like Cardano, and Polkadot has also same block time.


- ###  Why Block time is high? 

There comes a concept called Timekeeping which means that after the transaction has happened the transaction node has to distribute this transaction in the network. In the below image we can see:- A mine a transaction and A has to distribute it to their neighbours and as same their neighbour will distribute to again their neighbour.

![decen-fi.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660281767112/H1pmXWJFN.png align="left")


But sometimes this information distribution is between nodes which are 1000s of km far away from each other like in the above image distance between A and B is less so B will be notified first but A and C have more distance so C will be notified much later. But to verify a block majority of the validators needed to verify that block, so the block can be successfully mined. And this time taken in the transfer of signal is the limitation of proof of stack block mining.

- ### Proof of History:-

Here comes the unique consensus mechanism of the SOLANA blockchain named as proof of history it's a high frequency [Verifiable delay function]( https://www.youtube.com/watch?v=qUoagL7OZ1k). A Verifiable Delay Function requires a specific number of sequential steps to evaluate, yet produces a unique output that can be efficiently and publicly verified. It's like when you take a photo of the New York Time cover page, you are creating a proof that this photo has taken after the article got published. In the same way, this mechanism takes a photo of a block after some fixed time and later with some simple rules, we can verify which transaction was processed first and which transaction was processed later. 

%[https://www.youtube.com/watch?v=rywOYfGu4EA&t=2s]


With this consensus mechanism and some more upgrades on scalability Solana becomes a key competitor of Ethereum because it's fast, cheap and more reliable.

### For developers-:
At this time Ethereum is the biggest competitor of Solana At this current time Solana has 1000+ validators whereas Ethereum has more than 300000 validators in its beacon chain which is the upgrade of the current Ethereum chain. The more no. of validators will be there the more safe blockchain will become. So time will tell what's in future for Solana for now, You have to use rust to make a project on Solana but on Ethereum or any EVM-based blockchain, you can use Solidity or Vyper. Solana has made a bridge by which you can help to transfer your Ethereum-based project to Solana that's why people believe that both the blockchains can co-exist at the same time.


#### Resources-
Here I am linking some of the resources which helped me to make this blog happen
[Proof Of Work](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/)

[The Beacon Chain](https://ethereum.org/en/upgrades/beacon-chain/)

[A video by tanmay bhat](https://www.youtube.com/watch?v=_ivdpGSloaY)

[Proof of history In-depth explaination](https://medium.com/solana-labs/proof-of-history-a-clock-for-blockchain-cf47a61a9274)