# [SOLfees.fyi](https://www.solfees.fyi/)

Check how much you\'ve spent on Solana transaction fees across all your wallets & compare with other blockchains.
![2-wide](https://github.com/ronnyhaase/solfees.fyi/assets/714368/cbeeb847-2988-469c-8079-e2e2ac4f4fd8)

## Contributing

### Ideas & Issues

New ideas on how to make SOLfees.fyi better are highly welcome!

If you face any problems, let me know!

Don't hesitate to create an issue or ping me on [X / Twitter](https://x.com/ronnyhaase)!

### Development

Following services are used to fetch the data:

- Helius for transaction history
- Birdeye for token prices
- QuickNode GraphQL for gas prices
- Dune for gas usage / Tx
- Vercel KV to cache gas data


I. Install dependencies
```
npm install
```

II. Create an `.env.local` file in the project route and add the sercrets of the services
```
BIRDEYE_KEY=12345
DUNE_KEY=12345
HELIUS_KEY=12345
KV_URL=redis://...
KV_REST_API_URL=https://...
KV_REST_API_TOKEN=12345
KV_REST_API_READ_ONLY_TOKEN=12345
QUICKNODE_KEY=12345
```

III. Run the development server
```
npm run dev
```

IV. Call the hooks locally to cache initial data
```
curl -X POST http://localhost:3000/hooks/update-gas-fees
curl -X POST http://localhost:3000/hooks/update-gas-usage
```

---

