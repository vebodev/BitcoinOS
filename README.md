
<img src="images/bitcoinos.png" width="66%">

#

[![Apache-2 licensed](https://img.shields.io/crates/l/rgb-wallet)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

## What's bitcoinOS

Bitcoin is a peer-to-peer electronic cash system designed to create a decentralized financial ecosystem, providing individuals with sovereignty over their identity and digital assets. 
bitcoinOS, on the other hand, takes Bitcoin as its core and adds sovereignty protection for data assets on top of it. bitcoinOS is a modular blockchain network that uses Bitcoin L1 as the settlement layer and builds Bitcoin L2: Fastnet with RGB smart contracts and ICP network technology at its core. 

While the Bitcoin network primarily focuses on asset platforms and payment applications, bitcoinOS expands the scope of Bitcoin's ecosystem and enhances user experience by fully integrating Bitcoin L1 assets and combining them with the ICP network through the SmartWallet.

bitcoinOS maintains the identity and asset sovereignty of Bitcoin while also increasing support and protection for data sovereignty, enhancing privacy and scalability, thereby facilitating rapid payments and transactions for all Bitcoin assets.

In the era of artificial intelligence, data is considered the most important means of production and factor. Through data sovereignty provided by bitcoinOS, legitimate data owners are given the first step of protection. 

Similar to Bitcoin's empowerment of identity and currency, bitcoinOS's data empowerment can activate innovation for everyone by utilizing massive data with large language models (LLMs) or large world models (LWM). This not only promotes the rapid integration of Web2 and Web3 but also drives the widespread adoption of Bitcoin and blockchain technology.

[White paper](./whitepaper/bitcoinOS-whitepaper.pdf)

## Vision
- Digital Sovereign Network: While Bitcoin L1 has successfully established sovereignty over identity and assets, bitcoinOS takes this concept to new heights. Built on the core of Bitcoin L1 and utilizing the RGB smart contract protocol on the ICP network, bitcoinOS constructs Bitcoin L2: Fastnet. Fastnet provides comprehensive Bitcoin smart contract functionality and unlimited scalability while enhancing support for data sovereignty. On the bitcoinOS platform, ownership and rights to data assets belong entirely to individuals, making data assets a first-class asset.

- One-stop Platform: bitcoinOS serves as a comprehensive platform for managing Bitcoin L1 assets, including but not limited to BTC transfers, as well as issuing and trading Ordinals, Atomicals, and RGB assets. As the Bitcoin L2 layer within bitcoinOS, Fastnet facilitates the issuance and trading of RGB assets, providing financial support and fast payments for dApps and ecosystems. Additionally, Fastnet features Turing-complete smart contract functionality, meeting the needs of various application scenarios and empowering Bitcoin assets in areas such as DEX, social networks, staking, gaming, and more.

- Door to AGI: Data assets are considered one of the most important digital assets. Just as Bitcoin is digital gold, data is digital oil, and bitcoinOS becomes the catalyst for the digital oil revolution. As the first Bitcoin network to grant data ownership, bitcoinOS is positioned as the gateway to the era of artificial intelligence. In the era of artificial intelligence, data becomes the most important production factor, and owning bitcoinOS and data assets becomes the entry ticket for every individual into the era of artificial intelligence. You may not have your own large-scale model, but you must have your own unique intelligent agent.

- Foundation for Bitcoin Mass Adoption: As the cornerstone of driving Bitcoin's mass adoption, bitcoinOS combines the transparency of Bitcoin assets with the versatility of the Fastnet universal network. Fastnet not only facilitates fast payments but also ensures the privacy of content and services to protect individual while offering almost unlimited scalability to meet diverse application needs. bitcoinOS positions Bitcoin assets as the universal tokens of the digital world in the era of artificial intelligence.

- Copilot of Developers & Creators: The runtime of bitcoinOS is based on WebAssembly, standing at the forefront of industry standards and benefiting from the research achievements of the entire industry. The core functionality of bitcoinOS smart contract containers simplifies the complexity of developers' smart contract development. They can utilize various programming languages supported by WebAssembly, such as Golang, JavaScript, Python, Java, Rust, for development. Additionally, the built-in dApp store in bitcoinOS greatly facilitates developers and users in accessing Bitcoin ecosystem resources, as well as enabling Bitcoin developers and users to utilize resources and services from web2, integrating Web2 and Web3.

## Architecture
![avatar](./images/bitcoinOS-arch.svg)

## Setup
To get started, you might want to explore the project directory structure and the default configuration file. Working with this project in your development environment will not affect any production deployment or identity tokens.

To learn more before you start working with bitcoinOS, see the following documentation available online:

- [Quick Start](https://internetcomputer.org/docs/current/developer-docs/setup/deploy-locally)
- [SDK Developer Tools](https://internetcomputer.org/docs/current/developer-docs/setup/install)
- [Rust Canister Development Guide](https://internetcomputer.org/docs/current/developer-docs/backend/rust/)
- [ic-cdk](https://docs.rs/ic-cdk)
- [ic-cdk-macros](https://docs.rs/ic-cdk-macros)
- [Candid Introduction](https://internetcomputer.org/docs/current/developer-docs/backend/candid/)

If you want to start working on your project right away, you might want to try the following commands:

```bash
git clone https://github.com/bitcoinOS/bitcoinOS.git
cd bitcoinOS/
dfx help
dfx canister --help
```

## Running the project locally

If you want to test your project locally, you can use the following commands:

```bash
# Clone the `wasm-forge/wasi2ic` project:
git clone https://github.com/wasm-forge/wasi2ic

## Enter the wasi2ic directory and install it
cd wasi2ic
cargo install --path .

# Install just
cargo install just

# Starts the replica, running in the background
# Add --clean if you want to reset the dfx state: dfx start --background --clean
dfx start --background 


# All the just command details are in `justfile`

# Deploy os canister
just deploy_os

# Deploy steward canister
just deploy_steward

# Create canister if first time to install
just create_wallet

# Compile the project with `wasm-wasi` inside the project folder
just build_wallet

# Translate `wasm32-wasi` target to wasm32-unknown-unknown` under the project directory
just translate_wasm

# If you want to deploy smartwall by manually, In normal, the smartwallet will be install by os canister
just install_wallet
```

Once the job completes, your application will be available at `http://localhost:4943?canisterId={asset_canister_id}`.


### Note on frontend environment variables

If you are hosting frontend code somewhere without using DFX, you may need to make one of the following adjustments to ensure your project does not fetch the root key in production:

- set`DFX_NETWORK` to `ic` if you are using Webpack
- use your own preferred method to replace `process.env.DFX_NETWORK` in the autogenerated declarations
  - Setting `canisters -> {asset_canister_id} -> declarations -> env_override to a string` in `dfx.json` will replace `process.env.DFX_NETWORK` with the string in the autogenerated declarations
- Write your own `createActor` constructor

## Contribute
Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## License

bitcoinOS is primarily distributed under the terms of both the MIT license and the
Apache License (Version 2.0), with portions covered by various BSD-like
licenses.

See [LICENSE-APACHE](LICENSE-APACHE), [LICENSE-MIT](LICENSE-MIT), and
[COPYRIGHT](COPYRIGHT) for details.
