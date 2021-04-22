+++
title = "Glossary"
slug = "glossary"
template = "page.html"
draft = true
[taxonomies]
tags = []
+++

## Data structures

- **GIS Data structures**
  - Raster
    - made up of pixels
    - represented by a matrix
    - simple data structure
    - large storage requirements (all satellite imagery)

  - Vector
    - Consists of individual points stored as (x, y) coordinates ←→ (x=longitude, y=latitude)
    - Points, lines, polygons
    - Usually small storage requirements


- **O notations**
  Alternative Big O notations:
  - O(1) = O(yeah)
  - O(log n) = O(nice)
  - O(nlogn) = O(k-ish)
  - O(n) = O(ok)
  - O(n²) = O(my)
  - O(2ⁿ) = O(no)
  - O(n^n) = O(fuck)
  - O(n!) = O(mg!)

  Array
  - Access: O(1)
  - search : O(n)
  - Insert : O(n)
  - Delete : O(n)

  LinkedList
  - Access: O(n)
  - search : O(n)
  - Insert : O(n)
  - Delete : O(n)

## Blockchain
- A distributed (same copy of the data is kept in multiple machines) data storage consisting of containers (blocks) that are connected
- The order of the blocks matters. Every block read like a folder on your system (not technically a folder but easier to understand) that contains some data. Each folder knows about the folder before it building a chain
- Blockchain is not limited to just transactions. It's a "Data Storage". A single block can hold any data you want (text, number, program that can be executed). In bitcoin, it's a list of transactions.
- Each block is **hashed** (receives a hash value - some long text) that's generated from all the parts that make up the block using some hasing algorithm. You'll always get the same hash value for the same input, then that hash value is stored in the next block. So, whenever you change the previous block, it does not match the recalculated hash for that updated data.

  <img src="https://snipboard.io/1rv0Bs.jpg" width="450">


- Use cases:
  - Cryptocurrency - most prominent use case of the blockchain. If the data you store in a block is a list of transactions (who is sending how much to whom. Ex: the coins transferred in the trasansactions), it forms your cryptocurrency. These transactions cannot be edited without the next block recognizing it. All the cryptocurrencies (Bitcoin, Ethereum, rebel, etc) use such blockchains distributed across multiple machines called **nodes**.
    - Coins are transferred with Transactions
    - Changing them into other currencies is not possible inside the Blockchain. The value of a coin is determined by the value the participants of the blockchain network assign to it (i.e what you're willing to pay in "real" currencies)
    - Coins are created with **Mining** (as a reward for the effort) - Mining is how new blocks are added. You'll have open transactions, where you want to send something to someone, for that transaction to be confirmed, it needs to be added to a new block, which is added at the end of the blockchain. People who are adding this are doing the so called "Mining" - actually takes a bit longer because they need to solve complex algorithm, and they get new coins out of the system - as a reward.
    - A **wallet** is just a node that enables you to send/receive coins. It's a piece of data which allows you to identify yourself. You can send coins to another wallet which makes a **transaction** - when such new transaction is created, it is also broadcast into the nodes, which is distributed across the network and they will verify the transaction in the network to ensure you have enough funds, you are who you claim to be. Then, one node will eventually bundle transactions and sotre them in newly generated (mined) block and broacast new block to the network.

    <img src="https://snipboard.io/zp6MfP.jpg" width="450">
