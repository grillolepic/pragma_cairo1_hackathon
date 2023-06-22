# StarkPong
A fully P2P real-time, multiplayer game. Secured by StarkNet.

## Deployments

### Alpha-Testnet
Save for the Cairo0 one, all contracts were compiled/declared/deployed with: **starknet 0.11.2** and **cairo 1.1.0**

**PONG Token:**
- ClassHash: 0x111630357350e90324b40d6e67c06d687964a6da214c99a7e412dc138fffad7
- ContractAddress: 0x076d616a4566c5cd5d46fe83cf7511f62f868d15e55b60d2ea56103239db2337

**PONG Faucet:**
- ClassHash: 0x7d6d9b1c17515efe883a73eff944be7df6189e8cbd7a735995362381c73a095
- ContractAddress: 0x007f53eaefff754aad4b12b1316e33521cf20f79361f3934c87b98b575521d1f

**Signature Verification (Cairo 0)**
- ClassHash: 0x16bc10d25350cfb98807701abc3fc01108a75e668b45f83eace2ed256415eba
- ContractAddress: 0x0090eb31ad0d49d1a1dc446379a74a5a5a40908a7be3838fe93ef5d5a801ef6b

**Game Room:**
- ClassHash: 0x750376849e6f3271dab28be028be19a008a0ebda4c94a44c3f9ebea5e59852

**Game Room Factory:**
- ClassHash: 0x5903a51f204a4d87c428aba9db2e5a6c01565d55bd6a09f6ee79572c89277ef
- ContractAddress: 0x02909102709cbd49f3d5cccc85056bc489c81b09baecdc98f44bb4cb0f7b9a74

## Development notes
- ECDSA Signature verification libfuncs are still experimental on Cairo1. I had to deploy a Cairo0 contract to verify signatures.
- Reading packed variables produced errors when compiling for deployment (https://github.com/starkware-libs/cairo/issues/3153). I had to remove all variable packing.
- Upcasting and downcasting are also still experimental. Had to convert all values through felt252.
- u256 division was also still experimental. Used u128 division for token balances, assuming it would never go over u128 max value.
