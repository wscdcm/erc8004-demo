# ERC-8004 Trustless Agents · Sepolia Demo

Interactive demo for [ERC-8004 (Trustless Agents)](https://github.com/ethereum/ERCs/issues/1696) — AI Agent on-chain identity system deployed on Sepolia testnet.

## 🌐 Live Demo

**https://wscdcm.github.io/erc8004-demo/**

- **MetaMask mode**: Connect wallet for read-write interaction
- **Read-only mode**: Automatic fallback when no wallet available
- Built-in multi-RPC fallback for restricted networks

## 📋 Deployed Contracts (V2 Suite)

All contracts source-verified on Sepolia Etherscan:

| Contract | Address | Feature |
|----------|---------|---------|
| ERC8004IdentityV2 | [`0xc0D37E6F...`](https://sepolia.etherscan.io/address/0xc0D37E6F7B214C92f292FC0534195027CD38AB79#code) | Agent Identity NFT (ERC-721) |
| SimpleReputationRegistryV2 | [`0xeD24f204...`](https://sepolia.etherscan.io/address/0xeD24f20485F025a85FB6e410900e24623B13D622#code) | Reputation Management |
| SimpleValidationRegistryV2 | [`0xa390763C...`](https://sepolia.etherscan.io/address/0xa390763C43125F9fA52190AacaFFd9EC8feF868c#code) | Validation Registry |
| DeFAIVaultV2 | [`0xf1b78204...`](https://sepolia.etherscan.io/address/0xf1b78204cEfe5eaCE25162dF9B7437d334C144aF#code) | DeFi Vault |
| StrategyExecutor | [`0x3ba9BEdE...`](https://sepolia.etherscan.io/address/0x3ba9BEdE58311402F9436776D8dF9251Dc203cDd#code) | Strategy Execution |
| CrossChainBridge | [`0xd012bcA5...`](https://sepolia.etherscan.io/address/0xd012bcA54679434B31b932F1E345fF0000957622#code) | Cross-chain Bridge |

## 🧪 E2E Test Results

Grand Loop v3 — all 5 phases passed (36.8s):

- ✅ Phase 1: Agent identity creation → Agent #1 "QClaw Master Agent"
- ✅ Phase 2: Capability registration → 7 capabilities added
- ✅ Phase 3: Validation recording → TEE Attestation passed
- ✅ Phase 4: Trust level upgrade → Level 1→5 (Platinum)
- ✅ Phase 5: Reputation confirmation → score=8000, 5 validations

## 🔗 Related

- **ERC-8004 Discussion**: [ethereum/ERCs#1696](https://github.com/ethereum/ERCs/issues/1696)
- **TARS Framework Proposal**: Security layer for autonomous agents
- **Juejin Article** (Chinese): [我把ERC-8004部署到了Sepolia](https://juejin.cn/post/7631624091740864527)
- **Paragraph Blog**: [@0x3ec8b9e6](https://paragraph.com/@0x3ec8b9e6a839cb497105900687590742300883d2)

## 🛠 Tech Stack

- Solidity 0.8.19 + OpenZeppelin 4.9.3
- Hardhat 2.x (with viaIR for stack-too-deep)
- ethers.js v6
- Ethereum Sepolia Testnet


## 🔗 ERC-8004 Ecosystem

Our deployment uses a custom ERC8004IdentityV2 implementation. For the official ERC-8004 adapter pattern (UUPS upgradeable, binding external tokens to identity records), check out:

- **adapter8004.xyz** — Official ERC-8004 Identity Adapter by [@nxt3d](https://github.com/nxt3d)
  - Deployed on: Ethereum, Base, Sepolia
  - GitHub: [nxt3d/adapter](https://github.com/nxt3d/adapter)
  - ERC-8217 binding standard: [PR #1648](https://github.com/ethereum/ERCs/pull/1648)

Our V2 contracts implement the same core ERC-8004 semantics (Identity NFT + Reputation + Validation) with additional DeFi-specific extensions (Vault, StrategyExecutor, CrossChainBridge).

## License

MIT
