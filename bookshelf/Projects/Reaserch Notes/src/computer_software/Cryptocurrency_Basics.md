# Foundations

In this chapter, I will explain the foundations of cryptocurrecies so hopefully a non-technical person can understand.

Before we get started, I highly suggest reading the Bitcoin white paper for yourself either before or after reading this chapter. It is only 9 pages, and uses minimal jargon and only a bit of math which you can skip if you are not doing a deep dive. https://bitcoin.org/bitcoin.pdf

You do not need to read the white paper to understand my explanation or vice versa. It's just good to read the original source material. Also it is another explanation and reading both may better help you understand.

For a deeper understanding of Cryptocurrencies we first need to understand how two foundational concepts work:

1. Computer Cryptography
2. Blockchain

## Computer Cryptography

### Basics

Cryptography is, in short, the process of limiting access to something via obfuscation. For example, in war Cryptography is used to limit the enemy's access to knowledge by making messages nonsensical unless you know both the method and the starting point to remove the obfuscation. 

So to define some terms:
* Obfuscating information is called **Encrypting, Encryption, and Hashing**, 
* While reversing that is called **Decrypting, Decryption**.
* The method used to accomplish this is called an **algorithm**, which in general computer lingo just means "Set of steps a computer follows to produce a repeatable outcome".
* The starting point is called a **key**. 
* The Obfuscated information is called a **Hash**.

Anyone with the right algorithm and key can encrypt and decrypt information to and from hashes.

With computers providing a very high rate of information processing, cryptographic algorithms needs to be complicated and hard to break by brute force. 

### SHA-256

One of the most widely used cryptographic algorithms in the computer security world is SHA-256.

SHA-256 is used by developers to access basically _all digital infrastructure worldwide_. It is like a password, but much more secure. It is estimated that with access to 2.5 **million** high end computers it would still take 10^57 years, far longer then the earth has existed, to break by brute force a SHA-256 encrypted hash.

A very abbreviated explanation of SHA-256 follows.
 
The SHA-256 algorithm uses a paired public and private key. You can generate your own personal key pair with a special program on demand, and many people will use a different public/private key pair for each thing they need to use it in, even replacing their keys regularly to make sure everything stays secure.

The public key can be used to encrypt information **but not decrypt it**! (in a reasonable time frame anyway) This is because there are many private keys possible for any single public key, but only one **private** key can decrypt the information to get the original message.

A simple example to understand why a public key can not be reversed is to consider adding two numbers. Say 15 + 13 = 28. If you are provided just 28 (what we would call the hash), you won't know what two numbers add up to create that output. You can use this fact to encrypt a message, but to decrypt it you will need to know exactly which two numbers add up to it. If you tried using 16 + 12 the message encrypted with 15 + 13 becomes nonsense. 

Obviously the actual SHA-256 algorithm is more complicated then adding two numbers, but it uses this basic idea. The Public key has enough info to encrypt data into a Hash, but not decrypt the hash into data, and a private key has enough info to both encrypt to- and decrypt from- hashes.

This means it is safe to send **public** keys over the internet to another computer who can then encrypt information into a Hash with it and send that Hash back to you with no one being able to decrypt the hash _even if they intercepted the public key you sent to the 2nd party_. This allows you to limit information so only you and your 2nd party know what is being exchanged.

**Sources Referenced**:
* https://www.simplilearn.com/tutorials/cyber-security-tutorial/sha-256-algorithm
* https://www.quora.com/How-long-would-it-take-to-crack-SHA-256?share=1
* https://crypto.stackexchange.com/questions/45377/why-cant-we-reverse-hashes

## Blockchain

### Basics
 
Blockchain was developed in the 80s as a method to store information in a **decentralized**, something lacking a centralized source/authority, and **distributed** manner, so that no one party or group has to be fully trusted. Blockchain functions in a peer-to-peer environment where, normally, a copy of the whole blockchain exists with every single involved party, and each party is able to connect to any other party. We refer to these parties involved in the network as **Nodes**.

Blockchain, as the name states, is a chain of "blocks". Each block contains whatever data you need in a single entry and the order of the blocks are enforced via cryptography linking any specific block all the way back to the first starting block, called the **Genesis block**. Blocks are also timestamped providing a history for the chain. To add a block to the chain, a consensus of involved parties must agree to do so. Likewise the history is preserved via a consensus. 

To clarify what is meant by consensus, consider ownership of a company. Someone starting a company owns 100% of that company making all decisions, but they can sell off shares of ownership in the company to make some money (essentially what the stock market facilitates). If their personal ownership in the company drops below 50% the shareholders can override decisions made by the original owners if at least 51% of the shareholders agree.

In a system using Blockchain, every Node has some sort of "ownership" over the system. It is usually equal ownership, where any individual Node's ownership changes based on the number of connected Nodes at any specific time. But there are other methods to implement the system. Point being a majority of nodes need to agree, to allow changes to the block chain to be made. Any nodes refusing to follow the majority are ignored by the majority since the refusing node's version of the Blockchain is considered invalid by the majority. 

So to summarize, a Blockchain is a chain of blocks of data linked via cryptographic hashes and timestamped to keep history. It's use is based on a peer-to-peer network where everyone participating has a full copy of the blockchain, and new blocks can only be added if a consensus of nodes agrees to add the data. If a node insists on adding a block not agreed on by a majority, that node invalidates itself and is ignored by all valid nodes from that point onward.


### Forking

**Forking** a blockchain essentially means that a new group breaks off from the original group and make their own version of the chain adding blocks to the chain based on their consideration of what is valid. Everything before the fork is exactly the same for both blockchains, but after the fork they diverge and can never be reintegrated since the cyptographic hashes linking to previous blocks are different from the fork point onward.

A fork is normally done if a minority group wants to change the underlying technology in some way that the majority do not agree to for some reason. 

An example of a fork is when Bitcoin Cash forked off of Bitcoin. People who already had bitcoins suddenly had an equal amount of "bitcoin cash" since both blocks has the same shared history, but bitcoin and "bitcoin cash" continued on allowing people to trade the respective currencies separately since new entries on the two blockchains were not shared.


# Bitcoin

TODO




