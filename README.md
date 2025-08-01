# 🔥 Q3 2025 Turbin3 Builder Cohort

![Turbine Banner](https://pbs.twimg.com/profile_banners/1707159181914976256/1748632505/1500x500)

<details>
<summary><strong>Enrollment - NFT mint (rs&ts)</strong></summary>

- Prerequsites code task: [ts](prereq/ts) | [rs](prereq/rs)

- Take-aways
    - Never expose private keys or seed phrases to public
</details>

<details>
<summary><strong>Week1 - SPL FT & NFT</strong></summary>

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
<summary><strong>Week2 - FT Trade</strong></summary>

- vault & escrow & amm: 
    - [vault](https://github.com/Mobius3-3/vault) | [escrow](https://github.com/Mobius3-3/escrow) | [amm](https://github.com/Mobius3-3/amm) 

- Take-aways
    - Custody based on trustless onchain escrow is widely used on almost any defi application.
    - Variable naming should be straightforwrd about the data referred to.
</details>

<details>
<summary><strong>Week3 - NFT Stake & Trade</strong></summary>

- nft stake & nft marketplace: 
    - [nft stake](https://github.com/Mobius3-3/nft-stake) | [nft marketplace](https://github.com/Mobius3-3/nft-marketplace)

- Take-aways
    - If program is not specified, it uses crate::ID (your program's ID). Anchor resolves the PDA using something like this internally:
        ```rust
        let (pda, bump) = Pubkey::find_program_address(seeds, program_id);
        ```
    - A system account can be created and passed into instructions without being initialized with any custom data or logic. 
        ```rust
        #[account(
            seeds = [b"treasury", marketplace.key().as_ref()],
            bump,
        )]
        pub treasury: SystemAccount<'info>, // PDA owned by system program

        ```
    - If an account doesn’t require an exclusive signing authority, then it can be a random keypair or a program-derived address (PDA), such as an SPL Token mint — because no one needs to hold the private key to use it.
     
    - Data type hack:
        - For numbers:
            - Use the smallest type that safely fits your data (e.g., u8, u64, u128) to save account space.

            - Use checked_add, checked_mul, checked_sub, etc., to avoid panics or logic bugs.

            - Document max values explicitly if used for things like points, weights, or supply.

        - For Strings: are variable-length, costly to store, and hard to compare efficiently on-chain.
            - Convert user-facing strings (e.g. names, symbols, tags) to a fixed-size hash (e.g., Pubkey, [u8; 32], or u64 short hash).
</details>

<details>
<summary><strong>Week4 - dice & magicblock_counter</strong></summary>

- dice & magicblock counter: 
    - [dice](https://github.com/Mobius3-3/dice) forked from @inspi-writer001  | [magicblock counter](https://github.com/Mobius3-3/magicblock-counter) forked from @brianobot

- Take-aways
    - **Test tips:** On-chain instruction invokes and state changes can be inspected locally in .anchor logs.

        These logs are decoded (human-readable) and faster to analyze compared to scanning transactions on an on-chain explorer.

    - **Capstone related:** Merkle tree proof verification has high cost in both byte size (large proofs) and computation units. Optimization in both areas is important:

        - For hash function choice:
            - Poseidon: extremely efficient (designed for zk constraints) in field computation.
            - SHA‑2: good for non-zk implementation.
</details>

## 📬 Connect me

✉️ [imfangcong@gmail.com](mailto:imfangcong@gmail.com)  
🐦 X: [@andrew_f_c](https://twitter.com/andrew_f_c)

_This submission represents my own work in accordance with academic integrity policies._