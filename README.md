# poc-upgradable-smart-contracts

```
1. Deploy State Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x28f39b65668916f3a4616ee6d38956ac0025cb82

2. Deploy Proxy Admin Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x646364d2c0f7fa37cfb03648c86237822d8220a8

3. Deploy Transfer Proxy Contract
params: (multisig)
0x5ca11C96263533AAe363c9fA0d3d8Dab7fAB6cB4

Deployed Contract:
0x8183dee5627ea8ada5cc89f6bf66a41aa13eefcd

4. Deploy Proxy Contract
params: (state, proxy_admin)
state:0x28f39b65668916f3a4616ee6d38956ac0025cb82
proxy_admin:0x646364d2c0f7fa37cfb03648c86237822d8220a8
transfer_proxy:0x8183dee5627ea8ada5cc89f6bf66a41aa13eefcd

Deployer Contract:
0x4a765f7b55f5f2ca0901a56783fc86fb25f7e580

4. In State Contract, update Proxy Contract

5. In Proxy Admin Contract, update Proxy Contract

6. In Transfer Proxy, updateProxy

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

