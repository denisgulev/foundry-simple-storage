## Deploy to local chain

* 1st make to sure to run "anvil" in a terminal

Run the following command in terminal:
```
    forge create SimpleStorage --rpc-url http://127.0.0.1:8545 --private-key <private-key>
```


Use a script to deploy a contract:
```
    forge script script/DeploySimpleStorage.s.sol --rpc-url http://127.0.0.1:8545 --private-key <private-key>
```

* A note to not use private keys in plain text

1. 
```
    cast wallet import defaultKey --interactive
``` 
- put your private key 
- create a new password: "simple_storage_foundry"
- save the generated address

2. 
```
    forge script script/DeploySimpleStorage.s.sol --rpc-url http://localhost:8545 --account defaultKey --sender <address generated in the previous command> --broadcast
```
- put keystore password when required


## Interact with a deployed contract from CLI

- To call a function with parameters:
```
    cast send <contract-address> "<function-name>" <parameters> --rpc-url http://localhost:8545 --private-key <private-key>
```

- To call a viewing function:
```
    cast call <contract-address> "<function-name>"
```


## Compiling for ZKSync

1. install foundry-zksync
2. run 'foundryup-zksync'

- To switch back to vanilla foundry, simply run 'foundryup' in the CLI.