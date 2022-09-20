# PoC Upgradable Smart Contracts

The idea of having upgradable smart contracts is to update the logic of the contract for any potential bug in the Smart Contract.

## Limitations

The current version of Scilla has a limitation working with ADTs between two smart contracts, however, this can be handled by replacing custom ADT with variables.

This design approach won’t allow to add new variables in the State contract, however, new variables can be added in Collection Proxy, but there will be a state loss when a new proxy contract is updated.

## Architecture

Contracts will be spilt into multiple chunks based on the operations they perform.

1. State Contract
2. Logic Contract
3. Proxy Contract
4. Transfer Proxy Contract
5. Multisig Contract

### State Contract

This contract holds the complete state of the smart contract and its non-upgradable

### Logic Contract

This contract has access to State Contract to make the changes in state after validating the required conditions, this is an upgradable contract.

### Proxy Contract

This contract delegates the calls to Logic Contract and has permission to update Logic Contract.

### Transfer Proxy Contract

This contract acts as a treasury or operator while handing the ZRC2 & ZRC6 transfers. This is a non-upgradable contract. The logic contract will have access to this contract.

### Multisig Contract

This contract has access to the following and can be extended for other functionalities in the state, logic & proxy

1. Updating the logic contract in the state contract
2. Updating the logic contract in the proxy contract
3. Updating the logic contract in the transfer proxy contract

## Deployment

Follow the below process to deploy the smart contract, make sure you follow the same sequence of operations.

1. Deploy State Contract

Parameters required:

```bash
multiSig wallet
```

2. Deploy Proxy Contract

Parameters required:

```bash
multiSig wallet
```

3. Deploy Transfer Proxy Contract

Parameters required:

```bash
multiSig wallet
```

4. Deploy Logic Contract

Parameters required:

```bash
state contract (required) - refer to checkpoint 1
proxy contract (required) - refer to checkpoint 2
proxy contract (required) - refer to checkpoint 3
```

5. Update Logic Contract

a. update logic contract in state contract

```
UpdateLogic( -logic contract address- )
```

b. update logic contract in proxy contract

```
UpdateLogic( -logic contract address- )
```

c. update logic contract in transfer proxy contract

```
updateOperator( -logic contract address-, -status- )
```

6. Execute Transaction

We have successfully, deployed the contract and have the necessary permissions to execute the transaction.

We can call SampleZRCTransfer by passing the below parameters

```
token_address, from, to, amount
```

note: Make sure that you increase the allowance in ZRC2 token contract before you execute SampleZRCTransfer.

Execution Flow 1:

![rfc20 drawio (10)](https://user-images.githubusercontent.com/110367244/191196470-7a68c39d-8b75-400b-bab0-054ca3640f12.png)

7. Upgrade Logic Contract

Deploy new logic smart contract with the update and fixes.

Parameters required:

```bash
state contract (required) - refer to checkpoint 1
proxy contract (required) - refer to checkpoint 2
proxy contract (required) - refer to checkpoint 3
```

8. follow step 5 in this section

9. follow step 6 to execute the transaction

Execution Flow 2:

![rfc20 drawio (11)](https://user-images.githubusercontent.com/110367244/191196489-49dd15ea-b8ee-4daf-bdf3-beee45f65bd5.png)

## Additional Info:

Test deployment details:

Deployed Logic:
```
https://devex.zilliqa.com/tx/0x4ce836ce0232ec1944097b983bfabcd319d4f8ed53e98bd0f71d8dd50de58374?network=https://dev-api.zilliqa.com
```

Updated Logic Contract:
```
https://devex.zilliqa.com/tx/1523aa740aaa7efb545ad2ef97bf5e6892b021e399550b11f203126e2745dd13?network=https://dev-api.zilliqa.com
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
