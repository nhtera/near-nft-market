
Deploy this smart contract to a development account:

```bash
near dev-deploy --wasmFile target/wasm32-unknown-unknown/release/near_nft_market.wasm
```

initialize the contract using the `new` method:
```bash
near call $CONTRACT_NAME new_default_meta '{"owner_id": "'$CONTRACT_NAME'"}' --accountId $CONTRACT_NAME
```

To view the NFT metadata:

```bash
near view $CONTRACT_NAME nft_metadata
```