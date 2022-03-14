
Deploy this smart contract to a development account:

```bash
near dev-deploy --wasmFile target/wasm32-unknown-unknown/release/near_nft_market.wasm
```

Behind the scenes, this is creating an account and deploying a contract to it. On the console, notice a message like:

>Done deploying to dev-1647269246143-96446453009066

In this instance, the account is `dev-1647269246143-96446453009066`. A file has been created containing a key pair to
the account, located at `neardev/dev-account`. To make the next few steps easier, we're going to set an
environment variable containing this development account id and use that when copy/pasting commands.
Run this command to set the environment variable:

```bash
source neardev/dev-account.env
```

You can tell if the environment variable is set correctly if your command line prints the account name after this command:
```bash
echo $CONTRACT_NAME
```

initialize the contract using the `new` method:
```bash
near call $CONTRACT_NAME new_default_meta '{"owner_id": "'$CONTRACT_NAME'"}' --accountId $CONTRACT_NAME
```

To view the NFT metadata:

```bash
near view $CONTRACT_NAME nft_metadata
```