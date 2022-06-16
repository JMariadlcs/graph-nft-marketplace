# GRAPH NFT MARKETPLACE SYNCHRO

This is a repo used for synchronize a NFT Marketplace backend with [TheGraph](https://thegraph.com/studio/) for listening to the emited Smart Contract events from Patrick Alpha's fcc. The backend repo can be found [here](https://github.com/JMariadlcs/nft-marketplace-backend) and the frontend repo can be found [here](https://github.com/JMariadlcs/nft-marketplace-frontend-thegraph).

The workshop followed to complete this repo is [this one](https://www.youtube.com/watch?v=gyMwXuJrbJQ&t=15996s).

The repo that we are going to implement is like [this one](https://github.com/PatrickAlphaC/graph-nft-marketplace-fcc)

## USE THEGRAPH

We are using TheGraph for reading the events. Steps:

1. Index events with TheGraph ✅.
2. Read indexed events from TheGraph ✅.

¿ How to use TheGraph ? -> Contracts must be verified on Etherscan.

- Go to [TheGraph](https://thegraph.com/studio/).
- Connect Metamask
- Change to Smart Contracts deployed network (maybe Rinkeby)
- Create subGraph studio
- Create a new git repository for your subGraph
- Install Graph CLI:

```bash
sudo yarn global add @graphprotocol/graph-cli
```

- Initialize subGraph (change the name):

```bash
graph init --studio nftgraphmarketplace
```

- Execute (change name):

```bash
mv nftgraphmarketplace/* ./
and marketplace-nft-fcc folder.
```

- Modify `schema.graphql` with your events info and new tables that you want to create.
- Every time you modify `schema.graphql` -> Execute:

```bash
graph codegen
```

- Modify `nft-marketplace.ts` inside `src`.
- Go to `subprah.yaml` and include after abi:

  ```bash
  startBlock: deployedcontractBlock -1
  ```

- Deploy subGraph (change name last command):

```bash
graph auth --studio XXX
graph codegen && graph build
graph deploy --studio nftgraphmarketplace
```

- Version label: v0.0.1

✅ SUBGRAPH DEPLOYED!!

- You can now start executing scripts from your backend and now your subGraph should be able to listen to these events.
