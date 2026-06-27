# Contributions to Privacy-Preserving Zakat and Islamic Social Finance on Blockchain

- **Zero-Knowledge Zakat: Auditable Private Donations**
  - [Technical Paper (IEEE ICIMTech 2026)](https://github.com/tawf-labs/zkt-research/blob/main/zk-private-zakat.pdf)
  - [LaTeX Source](https://github.com/tawf-labs/zkt-research/blob/main/zk-private-zakat.tex)
  - [Live Testnet (Sepolia)](https://ziswaf.tawf.foundation)
  - [Smart Contract Source & Benchmarks](https://github.com/tawf-labs/zkt-research/tree/main/sc)
  - Performance: UltraHONK (270ms prove, 10ms verify, 8,384-byte proof); Foundry gas reports (v9)

- **Zero-Knowledge Private Zakat: Privacy-Preserving Donation Protocol**
  - [Draft Paper](https://github.com/tawf-labs/zkt-research/blob/main/zkdid.tex)
  - Aztec Network-based protocol, Noir circuits, nullifier mechanism, selective disclosure
  - Circuit benchmarks: UltraHONK (452ms prove, 89ms verify); Base Sepolia gas measurements

- **Solana ZK Layer: Groth16 Eligibility Circuit**
  - [Circom Circuit (`zakat_eligibility`)](https://github.com/tawf-labs/zkt-research/blob/main/solana/circuits/zakat_eligibility.circom)
  - [Vendored no_std Groth16 Verifier](https://github.com/tawf-labs/zkt-research/blob/main/solana/zkt_core/src/groth16.rs)
  - [Circuit Build Guide + Trusted Setup](https://github.com/tawf-labs/zkt-research/blob/main/solana/circuits/README.md)
  - Prove wealth ≥ nisab ∧ hawl elapsed under zero-knowledge (Poseidon nullifier, BN254, Groth16)
  - **Papers the Groth16 verifier is based upon**
    - [Light Protocol's groth16-solana](https://github.com/Lightprotocol/groth16-solana) (audited on-chain verifier)

- **Trusted Setup Ceremony for Zakat Eligibility**
  - [Ceremony Runbook](https://github.com/tawf-labs/zkt-research/blob/main/solana/circuits/CEREMONY.md)
  - [Verification Key → Rust Converter](https://github.com/tawf-labs/zkt-research/blob/main/solana/circuits/vk_to_rust.js)
  - Phase 1: Reuses Hermez/Powers of Tau (`powersOfTau28_hez_final_12.ptau`)
  - Phase 2: Multi-party with Squads signers + optional Bitcoin block-hash beacon
  - Security model: secure if ≥1 honest contributor

- **Architecture Decision Records**
  - [ADR-0001: Quasar over Anchor for Solana](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0001-quasar-over-anchor-for-solana-port.md)
  - [ADR-0002: Groth16/Circom for the ZK layer](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0002-groth16-circom-for-solana-zk-layer.md)
  - [ADR-0003: Phase 1 Guarded Launch (Squads multisig)](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0003-phase1-guarded-launch-squads-multisig.md)
  - [ADR-0004: Fixing the Eligibility Predicate + Shielding Split](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0004-phase2-zk-eligibility-predicate-and-shielding-split.md)
  - [ADR-0005: Privacy Posture & Regulatory Positioning](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0005-privacy-posture-and-regulatory-positioning.md)
  - [ADR-0006: Recipient Privacy via Commitments](https://github.com/tawf-labs/zkt-research/blob/main/docs/adr/0006-recipient-privacy-commitment-for-zakat-disbursements.md)

- **Security Analysis**
  - [In-House Audit of `zkt_core` (Solana Phase 1)](https://github.com/tawf-labs/zkt-research/blob/main/solana/SECURITY.md)
  - Trust model, invariants, vulnerability-class audit (arbitrary CPI, PDA, signer, ownership, sysvar)
  - [Fix: emergency pause bypassing organizer withdraw](https://github.com/tawf-labs/zkt-research/commit/6f5f8a5)
  - [Security-Awareness Corrections for the IEEE Paper](https://github.com/tawf-labs/zkt-research/blob/main/security-analysis-corrections.md)

- **Sharia-Compliant Governance Model**
  - Progressive decentralization: Admin Multisig → Sharia Council (off-chain → on-chain) → Community
  - [Off-Chain ZK Coordinator for Sharia Council Voting](https://github.com/tawf-labs/zkt-research/blob/main/sc/offchain-coordinator/README.md)
  - ShariaVoteAggregator circuit (Groth16); Docker + Supabase deployment
  - Squads multisig administering Phase 1 organizer whitelist and config

- **Domain Model & Glossaries**
  - [Canonical Terminology (CONTEXT.md)](https://github.com/tawf-labs/zkt-research/blob/main/CONTEXT.md)
  - Resolves ambiguous terms: Pool vs Fallback Vault, Receipt vs Receipt NFT, Eligibility Proof vs KYC
  - [System Architecture Diagrams](https://github.com/tawf-labs/zkt-research/tree/main/docs/diagrams)

- **Disaster Response & Emergency Zakat**
  - [DRCP Integration](https://github.com/tawf-labs/zkt-research/blob/main/ZISWAF_DOCUMENTATION.md)
  - Emergency campaign type with accelerated 7-day deadline
  - Pool cap policy (~$300) for Phase 1 guarded launch

## Links

- [Main Repository](https://github.com/tawf-labs/zkt-hackathon)
- [Live Testnet](https://ziswaf.tawf.foundation)
- [IEEE ICIMTech 2026 Paper](https://github.com/tawf-labs/zkt-research/blob/main/zk-private-zakat.pdf)
