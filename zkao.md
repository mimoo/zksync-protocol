# ZKsync Era - Audit Scope

> Based on the [Immunefi Bug Bounty Program](https://immunefi.com/bug-bounty/zksyncera/scope/) (Last Updated: 23 January 2026)

**Maximum Bounty:** $1,100,000
**PoC Required** | **KYC Required**
**Total Assets in Scope:** 92
**Total Impacts in Scope:** 19

---

## 1. Blockchain/DLT Assets (ZK Circuits)

### zksync-protocol (zkevm_circuits)

All paths are relative to [`github.com/matter-labs/zksync-protocol`](https://github.com/matter-labs/zksync-protocol) on the `main` branch.

| Name | Path | Added |
|------|------|-------|
| Main VM | [`crates/zkevm_circuits/src/main_vm`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/main_vm) | 18 Apr 2024 |
| Scheduler | [`crates/zkevm_circuits/src/scheduler`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/scheduler) | 18 Apr 2024 |
| Recursion | [`crates/zkevm_circuits/src/recursion`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/recursion) | 18 Apr 2024 |
| FSM Input Output | [`crates/zkevm_circuits/src/fsm_input_output`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/fsm_input_output) | 18 Apr 2024 |
| EC Recover | [`crates/zkevm_circuits/src/ecrecover`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/ecrecover) | 18 Apr 2024 |
| Secp256r1 Verify | [`crates/zkevm_circuits/src/secp256r1_verify`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/secp256r1_verify) | 17 Sep 2024 |
| Keccak | [`crates/zkevm_circuits/src/keccak256_round_function`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/keccak256_round_function) | 18 Apr 2024 |
| SHA256 | [`crates/zkevm_circuits/src/sha256_round_function`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/sha256_round_function) | 18 Apr 2024 |
| Code Unpacker | [`crates/zkevm_circuits/src/code_unpacker_sha256`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/code_unpacker_sha256) | 18 Apr 2024 |
| Code Decommitment Sorter | [`crates/zkevm_circuits/src/sort_decommittment_requests`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/sort_decommittment_requests) | 18 Apr 2024 |
| Storage Sorter | [`crates/zkevm_circuits/src/storage_validity_by_grand_product`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/storage_validity_by_grand_product) | 18 Apr 2024 |
| Storage Application | [`crates/zkevm_circuits/src/storage_application`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/storage_application) | 18 Apr 2024 |
| Transient Storage | [`crates/zkevm_circuits/src/transient_storage_validity_by_grand_product`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/transient_storage_validity_by_grand_product) | 17 Sep 2024 |
| Events Sorter (L1Messages) | [`crates/zkevm_circuits/src/log_sorter`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/log_sorter) | 18 Apr 2024 |
| Log Demuxer | [`crates/zkevm_circuits/src/demux_log_queue`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/demux_log_queue) | 18 Apr 2024 |
| RAM Permutation | [`crates/zkevm_circuits/src/ram_permutation`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/ram_permutation) | 18 Apr 2024 |
| Linear Hasher | [`crates/zkevm_circuits/src/linear_hasher`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/linear_hasher) | 18 Apr 2024 |
| EIP 4844 | [`crates/zkevm_circuits/src/eip_4844`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src/eip_4844) | 18 Apr 2024 |
| Supplementary Code | [`crates/zkevm_circuits/src`](https://github.com/matter-labs/zksync-protocol/tree/main/crates/zkevm_circuits/src) | 18 Apr 2024 |

### zksync-crypto (SNARK Wrapper)

| Name | Path | Added |
|------|------|-------|
| SNARK Wrapper | [`crates/snark-wrapper`](https://github.com/matter-labs/zksync-crypto/tree/main/crates/snark-wrapper) | 18 Apr 2024 |

### Blockchain/DLT Impacts in Scope

| Severity | Impact |
|----------|--------|
| **Critical** | Direct loss of funds |
| **High** | Difference between implementation outside of the circuit and within the circuit, where the in-circuit implementation is accurate (e.g. overconstraint in the circuit) |

---

## 2. Smart Contract Assets

### L1 Contracts (Ethereum Mainnet)

#### Diamond Proxy (Core ZK Chain)

| Name | Address | Added |
|------|---------|-------|
| DiamondProxy.sol | [`0x3240...0324`](https://etherscan.io/address/0x32400084c286cf3e17e7b677ea9583e60a000324) | 10 Mar 2023 |
| AdminFacet.sol | [`0x4314...aFBC`](https://etherscan.io/address/0x431449e2a28A69122860A4956A3f7191eE15aFBC#code) | 10 Mar 2023 |
| ExecutorFacet.sol | [`0x2f11...A39A`](https://etherscan.io/address/0x2f116b9033d88Bb3Cf64C371AE5458fbA22BA39A#code) | 10 Mar 2023 |
| MailboxFacet.sol | [`0x365D...4fec`](https://etherscan.io/address/0x365D0ae3ECA13004daf2A4ba1501c01AaEbb4fec#code) | 10 Mar 2023 |
| GettersFacet.sol | [`0xae5c...CF22`](https://etherscan.io/address/0xae5cbB5f70e134668a13d7C8EcEF5e9E6FffCF22#code) | 10 Mar 2023 |

#### Bridges

| Name | Address | Added |
|------|---------|-------|
| L1ERC20Bridge proxy (TransparentUpgradeableProxy) | [`0x5789...e063`](https://etherscan.io/address/0x57891966931Eb4Bb6FB81430E6cE0A03AAbDe063) | 10 Mar 2023 |
| L1ERC20Bridge.sol | [`0x2dd3...9142`](https://etherscan.io/address/0x2dd3329a2ae9de60da02828a34f0cb6d6aff9142#code) | 10 Mar 2023 |
| L1Nullifier proxy (TransparentUpgradeableProxy) | [`0xD7f9...B2cB`](https://etherscan.io/address/0xD7f9f54194C633F36CCD5F3da84ad4a1c38cB2cB#code) | 22 Jan 2025 |
| L1Nullifier.sol | [`0xc6f0...9431`](https://etherscan.io/address/0xc6f08efb7ba78f40d00f41afac00211d59eb9431#code) | 22 Jan 2025 |
| Bridgehub proxy (TransparentUpgradeableProxy) | [`0x303a...5213`](https://etherscan.io/address/0x303a465B659cBB0ab36eE643eA362c509EEb5213#code) | 22 Jan 2025 |
| Bridgehub.sol | [`0x08a9...9f32`](https://etherscan.io/address/0x08a98b1048fb61e9fff7d7d98305ac6286ae9f32#code) | 22 Jan 2025 |

#### Chain Management & Verification

| Name | Address | Added |
|------|---------|-------|
| ChainTypeManager.sol | [`0x3453...b5ce`](https://etherscan.io/address/0x345314c7e4af84b763d98d23f772622e23afb5ce#code) | 22 Jan 2025 |
| ChainTypeManager proxy (TransparentUpgradeableProxy) | [`0xc2eE...5f5C`](https://etherscan.io/address/0xc2eE6b6af7d616f6e27ce7F4A451Aedc2b0F5f5C#code) | 22 Jan 2025 |
| ValidatorTimelock | [`0x8c0b...f564`](https://etherscan.io/address/0x8c0bfc04ada21fd496c55b8c50331f904306f564) | 27 Mar 2023 |
| DualVerifier.sol | [`0x53F5...1579`](https://etherscan.io/address/0x53F5DE9De3B2DA90633a2c74BEb3b9912cdd1579#code) | 10 Mar 2023 |
| PlonkVerifier.sol | [`0x06aa...EB66`](https://etherscan.io/address/0x06aa7a7B07108F7C5539645e32DD5c21cBF9EB66#code) | 19 Jul 2025 |
| L1VerifierFflonk.sol | [`0xD5dB...6a5b`](https://etherscan.io/address/0xD5dBE903F5382B052317D326FA1a7B63710C6a5b#code) | 19 Jul 2025 |

#### Governance

| Name | Address | Added |
|------|---------|-------|
| ProtocolUpgradeHandler proxy (TransparentUpgradeableProxy) | [`0xE30D...5Ab3`](https://etherscan.io/address/0xE30Dca3047B37dc7d88849dE4A4Dc07937ad5Ab3) | 25 Jul 2025 |
| ProtocolUpgradeHandler.sol | [`0x0a67...f19a`](https://etherscan.io/address/0x0a67f0fd2f7523057039f14969fe23a5f620f19a#code) | 19 Jul 2025 |
| EmergencyUpgradeBoard.sol | [`0xECE8...E3f6`](https://etherscan.io/address/0xECE8e30bFc92c2A8e11e6cb2e17B70868572E3f6#code) | 25 Jul 2025 |
| SecurityCouncil.sol | [`0x66E4...F410`](https://etherscan.io/address/0x66E4431266DC7E04E7d8b7FE9d2181253df7F410#code) | 25 Jul 2025 |
| Guardians.sol | [`0x600d...86b8`](https://etherscan.io/address/0x600dA620Ab29F41ABC6596a15981e14cE58c86b8) | 25 Jul 2025 |

### L2 Contracts (zkSync Era)

#### System Contracts

| Name | Address | Added |
|------|---------|-------|
| EmptyContract | [`0x0000...0000`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000000#contract) | 27 Mar 2023 |
| Ecrecover | [`0x0000...0001`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000001#contract) | 27 Mar 2023 |
| SHA256 | [`0x0000...0002`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000002#contract) | 27 Mar 2023 |
| EcAdd | [`0x0000...0006`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000006#contract) | 18 Apr 2024 |
| EcMul | [`0x0000...0007`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000007#contract) | 18 Apr 2024 |
| EcPairing | [`0x0000...0008`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000008#contract) | 13 Jun 2024 |
| P256Verify | [`0x0000...0100`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000000100#contract) | 13 Jun 2024 |
| AccountCodeStorage | [`0x0000...8002`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008002#contract) | 27 Mar 2023 |
| NonceHolder | [`0x0000...8003`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008003#contract) | 27 Mar 2023 |
| KnownCodesStorage | [`0x0000...8004`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008004#contract) | 27 Mar 2023 |
| ImmutableSimulator | [`0x0000...8005`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008005#contract) | 27 Mar 2023 |
| ContractDeployer | [`0x0000...8006`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008006#contract) | 27 Mar 2023 |
| L1Messenger | [`0x0000...8008`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008008#contract) | 27 Mar 2023 |
| MsgValueSimulator | [`0x0000...8009`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008009#contract) | 27 Mar 2023 |
| L2BaseToken | [`0x0000...800a`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800a#contract) | 27 Mar 2023 |
| SystemContext | [`0x0000...800b`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800b#contract) | 27 Mar 2023 |
| BootloaderUtilities | [`0x0000...800c`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800c#contract) | 27 Mar 2023 |
| EventWriter | [`0x0000...800d`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800d#contract) | 27 Mar 2023 |
| Compressor | [`0x0000...800e`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800e#contract) | 27 Mar 2023 |
| ComplexUpgrader | [`0x0000...800f`](https://explorer.zksync.io/address/0x000000000000000000000000000000000000800f#contract) | 18 Apr 2024 |
| Keccak256 | [`0x0000...8010`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008010#contract) | 27 Mar 2023 |
| PubdataChunkPublisher | [`0x0000...8011`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008011#contract) | 13 Jun 2024 |
| CodeOracle | [`0x0000...8012`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000008012#contract) | 13 Jun 2024 |

#### L2 Bridge & Gateway Contracts

| Name | Address | Added |
|------|---------|-------|
| Create2Factory | [`0x0000...10000`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010000#contract) | 13 Jun 2024 |
| L2GenesisUpgrade | [`0x0000...10001`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010001#contract) | 25 Jul 2025 |
| BridgeHub | [`0x0000...10002`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010002#contract) | 25 Jul 2025 |
| L2AssetRouter | [`0x0000...10003`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010003#contract) | 25 Jul 2025 |
| L2NativeTokenVault | [`0x0000...10004`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010004#contract) | 25 Jul 2025 |
| MessageRoot | [`0x0000...10005`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010005#contract) | 25 Jul 2025 |
| SloadContract | [`0x0000...10006`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010006#contract) | 25 Jul 2025 |
| L2WrappedBaseToken | [`0x0000...10007`](https://explorer.zksync.io/address/0x0000000000000000000000000000000000010007#contract) | 25 Jul 2025 |
| L2SharedBridge.sol | [`0xcc87...ba46`](https://explorer.zksync.io/address/0xcc87d9e8525bc40afc11e79f637e1570d7e5ba46#contract) | 22 Jan 2025 |
| L2SharedBridge proxy (TransparentUpgradeableProxy) | [`0x11f9...E102`](https://explorer.zksync.io/address/0x11f943b2c77b743AB90f4A0Ae7d5A4e7FCA3E102#contract) | 22 Jan 2025 |

#### L2 Governance Contracts

| Name | Address | Added |
|------|---------|-------|
| ZkProtocolGovernor.sol | [`0x7670...e34f`](https://explorer.zksync.io/address/0x76705327e682F2d96943280D99464Ab61219e34f#contract) | 25 Jul 2025 |
| ZkTokenGovernor.sol | [`0xb83F...5746`](https://explorer.zksync.io/address/0xb83FF6501214ddF40C91C9565d095400f3F45746#contract) | 25 Jul 2025 |
| ZkToken.sol | [`0x01a6...c09`](https://explorer.zksync.io/address/0x01a6715d3560241e09e865a46122bf347a576c09#contract) | 25 Jul 2025 |
| ZkToken proxy (TransparentUpgradeableProxy) | [`0x5A7d...af3E`](https://explorer.zksync.io/address/0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E#contract) | 25 Jul 2025 |
| ZkProtocol TimelockController.sol | [`0x085b...c714`](https://explorer.zksync.io/address/0x085b8B6407f150D62adB1EF926F7f304600ec714#contract) | 25 Jul 2025 |
| ZkGovOps TimelockController.sol | [`0xC9E4...428a`](https://explorer.zksync.io/address/0xC9E442574958f96C026DeF9a50C3236cab17428a#contract) | 25 Jul 2025 |
| ZkToken TimelockController.sol | [`0xe5d2...c3d`](https://explorer.zksync.io/address/0xe5d21A9179CA2E1F0F327d598D464CcF60d89c3d#contract) | 25 Jul 2025 |

#### Source Code (GitHub)

| Name | Path | Added |
|------|------|-------|
| Bootloader | [`era-contracts/system-contracts/bootloader/bootloader.yul`](https://github.com/matter-labs/era-contracts/blob/release-v28/system-contracts/bootloader/bootloader.yul) | 27 Mar 2023 |
| DefaultAccount | [`era-contracts/system-contracts/contracts/DefaultAccount.sol`](https://github.com/matter-labs/era-contracts/blob/release-v28/system-contracts/contracts/DefaultAccount.sol) | 27 Mar 2023 |

### Smart Contract Impacts in Scope

| Severity | Impact |
|----------|--------|
| **Critical** | Direct theft of any user funds, whether at-rest or in-motion |
| **Critical** | Permanent freezing of funds (that cannot be fixed by upgrade) |
| **Critical** | Protocol insolvency |
| **High** | Permanent freezing of funds (that can be fixed by upgrade) |
| **High** | Permanent stopping the priority queue |
| **High** | Theft of user fees |
| **Medium** | Block stuffing for profit |
| **Medium** | Griefing (e.g. no profit motive for an attacker, but damage to the users or the protocol) |
| **Medium** | Theft of gas |
| **Medium** | Unbounded gas consumption |
| **Low** | Contract fails to deliver promised returns, but doesn't lose value |

---

## 3. Web & App Assets

| Name | Target | Added |
|------|--------|-------|
| Block Explorer API | [zksync2-mainnet-explorer.zksync.io/network_stats](https://zksync2-mainnet-explorer.zksync.io/network_stats) | 10 Mar 2023 |
| WEB3 HTTP API | [zksync2-mainnet.zksync.io](https://zksync2-mainnet.zksync.io/) | 10 Mar 2023 |
| WEB3 WebSocket API | [zksync2-mainnet.zksync.io/ws](https://zksync2-mainnet.zksync.io/ws) | 10 Mar 2023 |
| zkSync Era Block Explorer | [explorer.zksync.io](https://explorer.zksync.io/) | 10 Mar 2023 |
| zkSync Era Portal | [portal.zksync.io](https://portal.zksync.io/) | 10 Mar 2023 |

### Web & App Impacts in Scope

| Severity | Impact |
|----------|--------|
| **Critical** | Execute arbitrary system commands |
| **Critical** | Retrieve sensitive data/files from a running server (database passwords, blockchain keys, etc.) |
| **Critical** | Taking down the application/website |
| **High** | Contract verification bypass |
| **High** | Misrepresentation of transaction data that may lead to misleading third party users |
| **High** | Misrepresentation of transaction data that may lead to misleading API users |

---

## 4. Out of Scope

### Program-Specific Exclusions

- Broken link hijacking
- Attacks requiring changing the verifier key

### Blockchain/DLT & Smart Contract Specific

- Incorrect data supplied by third party oracles (not to exclude oracle manipulation/flash loan attacks)
- Impacts requiring basic economic and governance attacks (e.g. 51% attack)
- Lack of liquidity impacts
- Impacts from Sybil attacks
- Impacts involving centralization risks

### Web & App Specific

- Theoretical impacts without any proof or demonstration
- Impacts involving attacks requiring physical access to the victim device
- Impacts involving attacks requiring access to the local network of the victim
- Reflected plain text injection (e.g. url parameters, path, etc.) -- this does not exclude reflected HTML injection with or without JavaScript, nor persistent plain text injection
- Any impacts involving self-XSS
- Captcha bypass using OCR without impact demonstration
- CSRF with no state modifying security impact (e.g. logout CSRF)
- Impacts related to missing HTTP Security Headers (such as X-FRAME-OPTIONS) or cookie security flags (such as "httponly") without demonstration of impact
- Server-side non-confidential information disclosure (IPs, server names, stack traces)
- Impacts causing only the enumeration or confirmation of the existence of users or tenants
- Impacts caused by vulnerabilities requiring un-prompted, in-app user actions that are not part of the normal app workflows
- Lack of SSL/TLS best practices
- Impacts that only require DDoS
- UX and UI impacts that do not materially disrupt use of the platform
- Impacts primarily caused by browser/plugin defects
- Leakage of non sensitive API keys (e.g. Etherscan, Infura, Alchemy, etc.)
- Any vulnerability exploit requiring browser bugs for exploitation (e.g. CSP bypass)
- SPF/DMARC misconfigured records
- Missing HTTP Headers without demonstrated impact
- Automated scanner reports without demonstrated impact
- UI/UX best practice recommendations
- Non-future-proof NFT rendering

### All Categories

- Impacts requiring attacks that the reporter has already exploited themselves, leading to damage
- Impacts caused by attacks requiring access to leaked keys/credentials
- Impacts caused by attacks requiring access to privileged addresses (including, but not limited to: governance and strategist contracts) without additional modifications to the privileges attributed
- Impacts relying on attacks involving the depegging of an external stablecoin where the attacker does not directly cause the depegging due to a bug in code
- Mentions of secrets, access tokens, API keys, private keys, etc. in GitHub will be considered out of scope without proof that they are in-use in production
- Best practice recommendations
- Feature requests
- Impacts on test files and configuration files unless stated otherwise in the bug bounty program
- Impacts requiring phishing or other social engineering attacks against project's employees and/or customers

---

## 5. Notes

- **Primacy of Impact** applies to both Smart Contract and Web & App categories (added 5 October 2023), meaning bugs may be accepted even if not explicitly in the listed scope if they demonstrate valid impact.
- The `release-v28` branch of [`era-contracts`](https://github.com/matter-labs/era-contracts) is the reference for Bootloader and DefaultAccount source code.
- The `main` branch of [`zksync-protocol`](https://github.com/matter-labs/zksync-protocol) is the reference for all ZK circuit code.
- The `main` branch of [`zksync-crypto`](https://github.com/matter-labs/zksync-crypto) is the reference for the SNARK wrapper.
