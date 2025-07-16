# Q3_25_Builder_AndrewFang

<details>
<summary><strong>Enrollment</strong></summary>

- Prerequsites code task: [ts](prereq/ts) | [rs](prereq/rs)

- Take-aways
    - Never expose private keys or seed phrases to public
</details>

<details>
<summary><strong>Week1</strong></summary>

- Spl ft & nft code task: 
    - [spl_init](solana_starter/ts/cluster1/spl_init.ts) | [spl_metadata](solana_starter/ts/cluster1/spl_metadata.ts) | [spl_mint](solana_starter/ts/cluster1/spl_mint.ts) | [blueshift_challenge](solana_starter/ts/cluster1/spl_challenge_blueshift.ts)
    - [nft_image](solana_starter/ts/cluster1/nft_image.ts) | [nft_metadata](solana_starter/ts/cluster1/nft_metadata.ts) | 
    [nft_mint](solana_starter/ts/cluster1/nft_mint.ts)

- Take-aways
    - Understand fundamental and core concepts related to [solana accounts model](https://solana.com/ru/docs/core/accounts).  
        - [PDA](https://solana.com/ru/docs/core/pda)
        - ATA
        - bump_seed_canonicalization
    
    - Hands-on interacting with [Token Programs](https://solana.com/ru/docs/tokens)(Original)
        - fungible token
        - [nft](https://developers.metaplex.com/token-metadata)

    - Cryptographic fun fact: when deriving a PDA public key, for each bump the expected possibility of bumping off ed25519 curve is about 50%. (Try to figure out the thereotical calculation under the hood but stuck with some algebra formulas).

    - Tradeoffs among kit, web3.js, gill. 
</details>
<details>
<summary><strong>Week2</strong></summary>

- vault & escrow & amm: 
    - [vault](https://github.com/Mobius3-3/vault) | [escrow](https://github.com/Mobius3-3/escrow) | [amm](https://github.com/Mobius3-3/amm) 

- Take-aways
    - Custody based on trustless onchain escrow is widely used on almost any defi application.
    - Variable naming should be straightforwrd about the data referred to.
</details>