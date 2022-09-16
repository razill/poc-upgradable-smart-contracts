# poc-upgradable-smart-contracts

```
1. Deploy State Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x90c23a7b5e02e3dba7b87ad672af78029e40f60a

2. Deploy Proxy Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x95471a51f53c7fd109a9b00037acb691fb70e4f6

3. Deploy Transfer Proxy Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x52b48f39c7d092125389448e55fefa5570906d1a

4. Deploy Logic Contract
params: (state, proxy, transfer_proxy)
state:0x90c23a7b5e02e3dba7b87ad672af78029e40f60a
proxy:0x95471a51f53c7fd109a9b00037acb691fb70e4f6
transfer_proxy:0x52b48f39c7d092125389448e55fefa5570906d1a

Deployer Contract:
0xe20145a904558f1fefb9e3a08c8e785456d7dc62

4. In State Contract, update Logic Contract

5. In Proxy Contract, update Logic Contract

6. In Transfer Proxy, updateProxy with Logic Contract

7. Increase Allowance in ZRC2

8. Execute SampleZRCTransfer

token
0x98a71b463a33bbff650d123bf04f1f32d1c8b508

from
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

to
0x307d9AA43caD46C68eaEe2C29c5f9EB4a8Ec7510

amont
1000000000000

```

