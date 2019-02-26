---
layout: post
title:  "Block"
permalink: /lessons/Usecase_block/
---

# BlockChain

- Language:TypeScript and JavaScript SDK 
- SDK-Version:v0.10.1-beta 
- MODEL:Blockchain

## Prerequisites
- Finish the getting started section
- Text editor or IDE
- NEM2-SDK or CLI


## NewBlock

Description:Get notified when a new block is included.

Code sample: 

```javascript
const listener = new Listener('120.79.181.170:3000');

listener.open().then(() => {

    listener
        .newBlock()
        .subscribe(block => console.log(block), err => console.error(err));

});
```


## GetBlockchainHeight
Description:Get the block information given a height.


Code sample: 


```javascript
const blockchainHttp = new BlockchainHttp('120.79.181.170:3000');

const height = 1;

blockchainHttp
    .getBlockByHeight(height)
    .subscribe(block => console.log(block), err => console.error(err));
``` 
    
    
- The following snippet returns the height of the latest block.

```javascript
const blockchainHttp = new BlockchainHttp('120.79.181.170:3000');

blockchainHttp
    .getBlockchainHeight()
    .subscribe(height => console.log(height.compact()), err => console.error(err));
```
