# Smart Contracts

Install dependencies
```
npm i
```

Compile contracts
```
npx hardhat compile
```

Clear cache / delete artifacts
```
npx hardhat clean
```

Run test suite
```
npx hardhat test
```

Run local hardhat network
```
npx hardhat node
```

Deploy contracts
```
npx hardhat run scripts/deploy.js
```

# Setup Merkle Distributor

Generate claim data file
```
npm run generate-claim-data
```

Convert claim data to generate the merkle input
```
npm run convert-claim-data
```

Generate the merkle root and proofs
```
npm run generate-merkle-root
```


# Etherscan verification

To try out Etherscan verification, you first need to deploy a contract to an Ethereum network that's supported by Etherscan, such as Ropsten.

In this project, copy the .env.template file to a file named .env, and then edit it to fill in the details. Enter your Etherscan API key, your Ropsten node URL (eg from Alchemy), and the private key of the account which will send the deployment transaction. With a valid .env file in place, first deploy your contract:

```shell
hardhat run --network ropsten scripts/deploy.js
```

Then, copy the deployment address and paste it in to replace `DEPLOYED_CONTRACT_ADDRESS` in this command:

```shell
npx hardhat verify --network ropsten DEPLOYED_CONTRACT_ADDRESS "Hello, Hardhat!"
```
