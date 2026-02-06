# <img src="https://raw.githubusercontent.com/astrosynx/Logo/main/monad.png" width="30" align="center"> &nbsp; Monad Validator Portal

Welcome to the **Monad Validator Portal** — a curated entry point for  
**SkyneticLabs validator knowledge, operational notes, and practical guidance**.

This repository serves as a **living runbook** for operating a Monad validator  
in real-world conditions across **testnet and mainnet** environments.

It is designed to evolve alongside the network and the validator experience.

---

## 📚 Documentation & Learning

Explore SkyneticLabs resources for Monad:

- **Mainnet Docs:** [View Mainnet Guide](https://skyneticlabs.gitbook.io/docs/services/mainnet-networks/monad)  
- **Testnet Docs:** [View Testnet Guide](https://skyneticlabs.gitbook.io/docs/services/testnet-networks/monad)  

These guides cover setup considerations, configuration details,
and recommended operational workflows for validators.

---

## Validator Lifecycle Coverage

This runbook is structured around the **actual lifecycle of a validator** —
from first readiness checks to long-term operation.

### 1. Environment Readiness

Key considerations before interacting with keys or chain state:

- hardware expectations and common pitfalls
- kernel and firmware nuances
- disk layout and TrieDB constraints
- time synchronization, networking, and entropy

---

### 2. Pre-Consensus Sanity

Checks and observations before joining or rejoining consensus:

- keystore presence and permissions
- service ordering and dependency behavior
- ports, peers, and gossip visibility
- subtle states where the node appears healthy but is not

---

### 3. Validator Actions

Operational guidance for **high-impact actions**, including:

- validator registration
- configuration adjustments
- restarts and rolling updates
- testnet → mainnet transitions

Each action is approached through:
- prerequisites
- runtime observations
- post-action verification

---

### 4. Failure & Recovery Patterns

A growing collection of real-world failure scenarios and recovery notes, such as:

- silent or partial sync stalls
- early indicators of TrieDB degradation
- late discovery of keystore inconsistencies
- services running without effective consensus participation
- edge cases observed after upgrades

The emphasis is on **early recognition** and **informed response**.

---

## Relationship to Official Monad Documentation

Official Monad documentation focuses on **supported workflows and component behavior**.

This portal complements it by capturing **operational context**,  
practical considerations, and lessons learned from running validators over time.

📘 Official documentation: https://docs.monad.xyz/

---

<p align="center">
  <i>Maintained by SkyneticLabs — validator operations & reliability</i>
</p>

