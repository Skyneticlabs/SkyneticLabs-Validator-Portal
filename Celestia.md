# <img src="https://raw.githubusercontent.com/Skyneticlabs/Logo/main/celestia-logo.png" width="30" align="center"> &nbsp; Celestia Network

Welcome to the **Celestia Validator Portal** — your access point for SkyneticLabs' validator, analytics and open data for the Celestia ecosystem.  
Celestia is our **home network**: it's where we built our first public dashboard and API.

---

## Our Validator

| | |
|---|---|
| **Network** | Celestia Testnet (Mocha) |
| **Operator address** | `celestiavaloper1uqnlzylk0uld4azf2n0awclxxtllmr7d0xrj3m` |
| **Explorer** | [View validator ↗](https://celestia-dashboard.krews.xyz/celestia-mocha/validators/celestiavaloper1uqnlzylk0uld4azf2n0awclxxtllmr7d0xrj3m) |
| **Hardware** | Own bare metal in Buenos Aires · remote signer + sentry nodes |

---

## Celestia Economic Dashboard

🟣 **[skyneticlabs.com/celestia](https://skyneticlabs.com/celestia)** — a lightweight analytics product for monitoring network load, transaction economics and fee efficiency.

- **Staking & yield** — total supply, annual provisions, bonded ratio, inflation rate and estimated staking APR
- **Inflation ladder** — from 8% at genesis through CIP-29 and CIP-41 to the 1.5% floor, with a 10-year supply projection
- **Who pays for security** — user fees vs. newly minted TIA, and fee coverage of the security budget
- **Data costs** — flat per-MB pricing compared with Ethereum blobs and calldata
- **Security & distribution** — top 5 / 10 / 25 stake share, median self-bond, unclaimed rewards
- **Trends & correlations** — staking ratio, supply growth, block load, active validators
- **bot.fun** — the AI-agent economy on Eden, an EVM rollup that pays gas in TIA

🔎 **[Validator & Fund Lookup](https://skyneticlabs.com/celestia/lookup/)** — Foundation Delegation Program seats, seat-holder uptime, jailed validators and archived cohorts.

---

## Public API

The data behind the dashboard is available as an open JSON API.  
**GET only · no auth · open CORS · 30s cache.**

**Base URL:** `https://skyneticlabs.com/celestia/api/v1/`

| Endpoint | Returns |
|---|---|
| `/network` | Chain state, block load, mempool |
| `/economics/supply` | Supply, provisions, community pool, inflation |
| `/economics/staking` | Bonded ratio, validator counts, top-N share |
| `/economics/fees` | Average and median fees, 24h fee series |
| `/economics/da-cost?mb=24000` | Data-availability cost calculator |
| `/economics/da-usage` | PayForBlobs share and blob bytes |
| `/validators?status=bonded&limit=10` | Filterable, sortable validator list |
| `/validators/<moniker-or-valoper>` | Single validator profile |
| `/namespaces/<namespace_id>` | DA footprint of a rollup or appchain |
| `/insights` | 24h and 7d changes in plain English |
| `/series/<key>?limit=200` | Historical time series |
| `/meta/status` | Collector health and available series keys |

```bash
# What changed on Celestia in the last 24h / 7d
curl https://skyneticlabs.com/celestia/api/v1/insights

# How much would it cost to publish 24 GB of data?
curl "https://skyneticlabs.com/celestia/api/v1/economics/da-cost?mb=24000"
```

🚧 **skynetic-da** — an open-source, local-first Python SDK for tracking namespace DA costs over time. *Coming soon.*

---

## Security Best Practices

To ensure a secure and resilient Celestia validator environment, we recommend following these guidelines:

- **Enable a firewall** (`ufw` or `firewalld`) and restrict access to essential ports only  
- **Disable public RPC** unless explicitly required for your setup  
- **Use a dedicated server for TMKMS** or any external signing solution  
- **Never run the validator and signer on the same machine**  
- **Enable monitoring and alerts** (Grafana, Loki, Prometheus, Telegram, etc.) to detect issues early  
- **Keep your system and packages up to date** with regular security patches  
- **Secure SSH access** using keys instead of passwords and restrict root login  
- **Implement regular backups** of configuration files and validator keys (securely stored offline)  
- **Protect against DDoS attacks** using rate-limiting or upstream filtering when possible

---

##  About SkyneticLabs

**SkyneticLabs** contributes to the Celestia ecosystem by maintaining:

- Reliable and secure validator infrastructure  
- Open dashboards and a public API for Celestia economics  
- Guides, scripts, and best practices for the community

📘 Installation, upgrades, data-availability nodes, security and monitoring guides live in the main documentation:  
👉 [https://skyneticlabs.gitbook.io/docs/](https://skyneticlabs.gitbook.io/docs/)  

---

<p align="center">
  <sub><i>Empowering modular blockchain infrastructure with transparency and open access.</i></sub>
</p>

<p align="center"> <a href="README.md">← Back to main portal</a> </p>

