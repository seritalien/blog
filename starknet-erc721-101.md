---
layout: page
title: starknet-erc721-101
permalink: /starknet-erc721-101/
---

Here is my work on Henri's Lieutaud tutorial named [starknet-erc721-101](https://github.com/l-henri/starknet-erc721-101)

We will build a pet system

First Job is about writing an implementation of ERC721 token

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

