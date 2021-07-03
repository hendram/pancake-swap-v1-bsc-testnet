# Pancake Swap V1 on BSC Testnet
This repo contains all source code of Pancake Swap V1. It has modified to run on Binance Smart Chain (BSC) Testnet.
<br />My original purpose is to use it to test my DApps that connect to Pancake Swap. Using the BSC Testnet environment has helped me a lot in reducing the cost and time of DApps development. I see thay it very useful for developers so I shared this version.

<p>If you want to use Pancake Swap v1 on BSC Testnet, please to the link: https://pancake.kiemtienonline360.com/
<br />If you want to implement your own Pancake Swap, please see detailed instructions below.

# Step by step to deploy Pancake Swap V1
<ul>
  <li><b>Step 1</b>: Deploy Pancake Factory Contract</li>
  <li><b>Step 2</b>: Deploy Pancake Router Contract</li>
  <li><b>Step 3</b>: Deploy Pancake Swap Interface</li>
</ul>
<p>Of these three steps, step 3 will take the longest time, step 2 need for a little attention. It takes time for me, but I will guide you how to deploy them in just 10 minutes.
<p>Before you start, you need to install NodeJs (Version 8 or later). In addition, you must also have experience to deploy contracts on Remix. You also install Metamask extension on Chrome browser and added "BSC Testnet".

# Step 1: Deploy Pancake Factory Contract
You can use <b>Truffle</b> hoặc <b>Remix</b> to build and deploy the contract. But for simplicity you should use Remix.
<p>The steps are as follows:
<ul>
  <li>
    <b>1. Install required libraries</b>
    <br />Go to "pancake-swap-core-v1" folder and run npm install:
    <br />&nbsp;&nbsp;&nbsp;&nbsp; <code>cd pancake-swap-core-v1</code>
    <br />&nbsp;&nbsp;&nbsp;&nbsp; <code>npm install</code>
  </li>
  <li>
    <b>2. Join contract files to 1 file</b>
    <br />I created a small tool to help join the contract files into 1 file. Run below command to join:
    <br />&nbsp;&nbsp;&nbsp;&nbsp; <code>mkdir build</code>
    <br />&nbsp;&nbsp;&nbsp;&nbsp; <code>node tools/merge-contract.js</code>
    <br />You can see the file <b>PancakeFactory.sol.merge.txt</b> in build directory.
  </li>
  <li>
    <b>3. Deploy on Remix</b>
    <br /> - Go the Remix website: https://remix.ethereum.org
    <br /> - Create new contract file <b>PancakeFactory.sol</b> on Remix and then copy all content in PancakeFactory.sol.merge.txt to the PancakeFactory.sol file.
    <br /> - Click left menu item "<b>Solidity complier</b>", select "<b>0.5.16</b>" in COMPILER section. And then click "<b>Complile PancakeFactory.sol</b>", compile success and no error.
    <br /> - Click left menu item "<b>Deploy &amp; run transactions</b>", select "<b>Injected Web3</b>" in ENVIRONMENT section. This step request to connect an account in Metamask.
    <br />Select "<b>PancakeFactory - ...</b>" in CONTRACT item. Enter your any bsc wallet address in "<b>address_feeToSetter</b>" input. And then click "<b>Deploy</b>" button, and wait.
    <br /> - Once deployed, you will see the contract address of PancakeFactory. In the "Deployed Contracts" section, you will see the new deployed contract. Expand it and you will get INIT_CODE_PAIR_HASH. For example:
    <br />PancakeFactory contract: <a href="https://testnet.bscscan.com/address/0xb7926c0430afb07aa7defde6da862ae0bde767bc">0xB7926C0430Afb07AA7DEfDE6DA862aE0Bde767bc</a>
    <br />INIT_CODE_PAIR_HASH: 0xecba335299a6693cb2ebc4782e74669b84290b6378ea3a3873c7231a8d7d1074
  </li>
</ul>
