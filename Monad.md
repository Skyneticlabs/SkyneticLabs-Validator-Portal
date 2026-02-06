# <img src="https://raw.githubusercontent.com/astrosynx/Logo/main/monad.png" width="30" align="center"> &nbsp; Monad Validator Portal

---

## 📚 Documentation & Learning

Explore SkyneticLabs resources for Monad:

- **Mainnet Docs:** https://skyneticlabs.gitbook.io/docs/services/mainnet-networks/monad  
- **Testnet Docs:** https://skyneticlabs.gitbook.io/docs/services/testnet-networks/monad  

These guides cover setup considerations, configuration details,  
and recommended operational workflows for validators.

---

## 🔐 Validator Security & Operational Safety

This repository focuses on **validator-side security** and safe operational practices.

While official Monad documentation defines protocol rules and supported flows,  
this portal documents **how operators reduce risk in real-world deployments**.

Security incidents are rarely caused by protocol flaws.  
They are almost always the result of **operational mistakes**.

---

## Threat Model (Operator View)

Primary risk areas for validators:

- unsafe or shared key handling
- blind restarts after crashes
- high-risk upgrades without rollback plans
- infrastructure failures (disk, memory, networking)
- misconfigured monitoring or missing alerts

---

## Core Security Principles

- **Key separation**  
  Validator authority and operational funding must be isolated to reduce blast radius.

- **No blind restarts**  
  Validators must never resume signing without verifying sync and state consistency.

- **Fail-safe upgrades**  
  Every upgrade must include a rollback path and a non-signing verification phase.

- **Least access by default**  
  Validator infrastructure should expose only what is strictly required.

Security is enforced by **operator discipline**, not by defaults.

---

## Key Management (Operator Perspective)

Recommended role separation:

- **Funding address**  
  Pays fees and routine operational transactions.

- **Validator authority**  
  Controls validator lifecycle and signing.

- **Recovery access**  
  Stored offline, used only for emergencies.

Compromise of a funding wallet must **never** allow validator takeover.

Validator keys must:
- never be stored on shared or user-accessible hosts
- never be copied between machines outside controlled recovery procedures
- never be backed up in hot or cloud storage

---

## Operational Checklists

### Safe Restart Checklist

Before resuming validator signing:

- verify local block height equals network height
- confirm the node is fully synced
- review recent logs for consensus or state errors
- start the node in **non-signing / observer mode**
- enable signing only after state consistency is confirmed

---

### Upgrade Safety Checklist

Upgrades represent the highest operational risk.

A safe upgrade workflow:

- snapshot or backup taken before upgrade
- new binary source verified
- rollback binary available
- validator stopped cleanly
- upgraded node started **without signing**
- signing resumed only after verification

> Every upgrade must have a rollback path.

---

## Non-Signing / Observer Mode

After crashes or upgrades, validators should start in a **non-signing mode**.

This allows:
- state verification
- consensus health checks
- log inspection without risk of accidental signing

Signing must remain disabled until full consistency is confirmed.

---

## Common Operator Mistakes

The following patterns are responsible for most validator incidents:

- restarting validators blindly after crashes
- upgrading without a rollback plan
- storing validator keys on shared or cloud-accessible hosts
- assuming funding wallet compromise is harmless
- exposing validator infrastructure beyond required access

Avoiding these mistakes prevents the majority of real-world failures.

---

## Monitoring as a Security Layer

Monitoring is part of security, not just observability.

Critical signals include:
- validator liveness
- block height lag
- disk usage thresholds
- memory pressure or OOM events

Alerts must be actionable and tied directly to validator risk.

---

## Scope & Intent

This repository intentionally avoids:
- protocol implementation details
- client-specific commands
- economic or slashing mechanics

It documents **operational guardrails** that apply regardless of client or network version.

> Security is not a feature — it is an operational discipline.

---

## Relationship to Official Monad Documentation

Official Monad documentation focuses on **supported workflows and protocol behavior**.

This portal complements it by capturing **operator-side context**,  
security considerations, and lessons learned from running validators over time.

Official documentation: https://docs.monad.xyz/

---

<p align="center">
  <i>Maintained by SkyneticLabs — validator operations & reliability</i>
</p>

