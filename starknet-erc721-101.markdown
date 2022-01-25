---
layout: page
title: starknet-erc721-101
permalink: /starknet-erc721-101/
---

Here is my work on Henri's Lieutaud tutorial named [starknet-erc721-101](https://github.com/l-henri/starknet-erc721-101)

We will build a pet system

First Job is about writing an implementation of ERC721 token
0. Prerequisites

[Voyager Goerli](https://goerli.voyager.online/)
[Alpha feeder](https://alpha4.starknet.io/feeder_gateway/get_transaction_receipt?transactionHash=)

My Argent-X test account contract :
0x00b2168f01fb2694bb0ea5e60547110b1e5cfd83cd1f50f02dbc5e0287f26274

#Exercice 1
1. implement ERC721 contract

using ERC721_base.cairo
and implementing mint function

2. compile the contract and deploy it to Goerli

`code` nile deploy ERC721_pepette 31636730804466789 7368820 0x00b2168f01fb2694bb0ea5e60547110b1e5cfd83cd1f50f02dbc5e0287f26274 --network goerli 

Result :

`code` 🚀 Deploying ERC721_pepette
`code`⏳ ️Deployment of ERC721_pepette successfully sent at 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073
`code`🧾 Transaction hash: 0x1229358e022fa2961683e09fd572cf3e0ed0668e34342eea8a259c9f1278f7c
`code`📦 Registering 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073 in goerli.deployments.txt

Our pepette token contract is : [0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073](https://goerli.voyager.online/contract/0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073#transactions)

3. mint a token
starknet invoke --address 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073 --abi artifacts/abis/ERC721_pepette.json --function mint --inputs 0x00b2168f01fb2694bb0ea5e60547110b1e5cfd83cd1f50f02dbc5e0287f26274 1 1

add a token in Argent-X with the contract adresse token 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073

4. Give token #1 to Evaluator contract
send the minted token at step 3 to the Evaluator contract 
[Evaluator](contracts/Evaluator.cairo) [0x040f8555af087a40f16d1b3b9ebdf7065980cb9f0aa285f86ebae7263c60d015](https://goerli.voyager.online/contract/0x040f8555af087a40f16d1b3b9ebdf7065980cb9f0aa285f86ebae7263c60d015)

`code`starknet invoke --address 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073 --abi artifacts/abis/ERC721_pepette.json --function transferFrom --inputs 0x00b2168f01fb2694bb0ea5e60547110b1e5cfd83cd1f50f02dbc5e0287f26274 0x040f8555af087a40f16d1b3b9ebdf7065980cb9f0aa285f86ebae7263c60d015 1 1

5. Evaluate the contract
using the Evaluator contract and his submit_exercise to evaluate the ERC721_pepette contract

`code` starknet invoke --address 0x040f8555af087a40f16d1b3b9ebdf7065980cb9f0aa285f86ebae7263c60d015 --abi artifacts/abis/Evaluator.json --function submit_exercise --inputs 0x0226b6ca42179f85dfd8a834c09fe436fc71019112f01a6d3404e9ba83aa7073
