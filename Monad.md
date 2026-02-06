# <img src="https://raw.githubusercontent.com/astrosynx/Logo/main/monad.png" width="30" align="center"> &nbsp; Monad Validator Portal

---

## 📚 Documentation & Learning

Explore SkyneticLabs resources for Monad:

- **Mainnet Docs:** [View Mainnet Guide](https://skyneticlabs.gitbook.io/docs/services/mainnet-networks/monad)  
- **Testnet Docs:** [View Testnet Guide](https://skyneticlabs.gitbook.io/docs/services/testnet-networks/monad)

These guides cover setup considerations, configuration details,  
and recommended operational workflows for validators.

---

## 🔐 Validator Security & Operational Safety

This repository focuses on **validator-side security** and safe operational practices.

While official Monad documentation defines protocol rules and supported flows,  
this portal documents **how operators reduce risk in real-world deployments**.

### Threat Model (Operator View)

Most validator incidents are caused by **operational mistakes**, not protocol flaws.

Primary risk areas:
- unsafe key handling
- blind restarts after crashes
- high-risk upgrades without rollback plans
- infrastructure failures (disk, memory, network)

---

### Core Security Principles

- **Key separation**  
  Validator authority and operational funding must be isolated to reduce blast radius.

- **No blind restarts**  
  Validators should never resume signing without verifying sync status and chain state.

- **Fail-safe upgrades**  
  Every upgrade must include a rollback path and a non-signing verification phase.

- **Least access by default**  
  Validator infrastructure should expose only what is strictly required for operation.

---

### Key Management (Operator Perspective)

Recommended role separation:
- **Funding address** — pays fees and routine operational transactions
- **Validator authority** — controls validator lifecycle and signing
- **Recovery access** — stored offline, used only for emergencies

Compromise of a funding wallet must never allow validator takeover.

Validator keys should:
- never be stored on shared or user-accessible hosts
- never be copied between machines outside controlled recovery procedures
- never be backed up in hot or cloud storage

---

### Safe Restarts & Recovery

Before resuming validator signing:
- verify local block height against the network
- confirm the node is fully synced
- review logs for consensus or state errors
- prefer starting in a non-signing / observer mode

Signing should only be re-enabled after state consistency is confirmed.

---

### Upgrade Safety

Upgrades represent the highest operational risk.

A safe upgrade workflow:
1. Pre-upgrade backup or snapshot
2. Binary verification
3. Controlled validator shutdown
4. Upgrade with configuration review
5. Startup without signing
6. Resume validation only after verification

> Every upgrade must have a rollback path.

---

### Monitoring as a Security Layer

Monitoring is part of security, not just observability.

Critical signals:
- validator liveness
- block height lag
- disk usage thresholds
- memory pressure or OOM events

Alerts should be actionable and tied directly to validator risk.

---

### Scope

This portal focuses on **operational safety**, not protocol implementation.

It documents guardrails, patterns, and operator discipline that help prevent:
- downtime during incidents
- accidental misconfiguration
- irreversible validator mistakes

> Security is not a feature — it is an operational discipline.

---

## Relationship to Official Monad Documentation

Official Monad documentation focuses on **supported workflows and protocol behavior**.

This portal complements it by capturing **operator-side context**,  
security considerations, and lessons learned from running validators over time.

📘 Official documentation: https://docs.monad.xyz/

---

<p align="center">
  <i>Maintained by SkyneticLabs — validator operations & reliability</i>
</p>
