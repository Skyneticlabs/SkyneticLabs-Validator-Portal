# <img src="https://raw.githubusercontent.com/Skyneticlabs/Logo/main/story.png" width="30" align="center"> &nbsp; Story Network

Welcome to the **Story Validator Portal** — your access point for SkyneticLabs’ public infrastructure, snapshots, and tools supporting the Story ecosystem.

---

##   Endpoint

Access public RPC, API, and gRPC endpoints for Celestia Mainnet and Testnet.

<details>
  <summary>⚫ Mainnet Endpoints</summary>

- **RPC:** [https://story-m-rpc.skyneticlabs.com](https://story-m-rpc.skyneticlabs.com)  
- **API:** [https://story-m-api.skyneticlabs.com](https://story-m-api.skyneticlabs.com)  
- **JSON-RPC:** [https://story-m-evm.skyneticlabs.com](https://story-m-evm.skyneticlabs.com) 
</details>

<details>
  <summary>⚪ Testnet Endpoints</summary>

- **RPC:** [https://story-t-rpc.skyneticlabs.com](https://story-t-rpc.skyneticlabs.com)  
- **API:** [https://story-t-api.skyneticlabs.com](https://story-t-api.skyneticlabs.com)  
- **JSON-RPC:** [https://story-t-evm.skyneticlabs.com](https://story-m-evm.skyneticlabs.com) 
</details>

---

##   Snapshots

Access Story **Mainnet** and **Testnet** snapshot resources and installation guides.  
Snapshots are **updated every 8 hours** to ensure fast and reliable node synchronization.

###   Snapshot directories
You can explore snapshot directories here:
- **Mainnet:** [https://services-m.skyneticlabs.com/story/](https://services-m.skyneticlabs.com/story/)  
- **Testnet:** [https://services-t.skyneticlabs.com/story/](https://services-t.skyneticlabs.com/story/)

Each directory contains:
- `addrbook.json` and `genesis.json` — configuration files  
- Snapshot with pruning  
- Metadata files with snapshot creation date and block height

---

<details>
<summary>⚫ Mainnet Snapshot — install guide</summary>

Use the following commands to restore **Celestia Mainnet** snapshot:  
📁 [View directory](https://services-m.skyneticlabs.com/story/)  
📦 [Download snapshot](https://services-m.skyneticlabs.com/story/snap.tar.lz4)

```bash
cd $HOME
sudo systemctl stop story story-geth
cp $HOME/.story/story/data/priv_validator_state.json $HOME/.story/story/priv_validator_state.json.backup
rm -rf $HOME/.story/story/data
rm -rf $HOME/.story/geth/story/geth/chaindata
curl https://services-m.skyneticlabs.com/story/mainnet/snap.tar.lz4 | lz4 -dc - | tar -xf - -C $HOME/.story/story
mv $HOME/.story/story/priv_validator_state.json.backup $HOME/.story/story/data/priv_validator_state.json
curl https://services-m.skyneticlabs.com/story/mainnet/snap_geth.tar.lz4 | lz4 -dc - | tar -xf - -C $HOME/.story/geth/story/geth
sudo systemctl restart story story-geth
sudo journalctl -u story-geth -u story -f
```
</details>

<details>
<summary>⚪ Testnet Snapshot — install guide</summary>

Use the following commands to restore **Celestia Testnet** snapshot:  
📁 [View directory](https://services-t.skyneticlabs.com/story/)  
📦 [Download snapshot](https://services-t.skyneticlabs.com/story/snap.tar.lz4)

```bash
cd $HOME
sudo systemctl stop story story-geth
cp $HOME/.story/story/data/priv_validator_state.json $HOME/.story/story/priv_validator_state.json.backup
rm -rf $HOME/.story/story/data
rm -rf $HOME/.story/geth/story/geth/chaindata
curl https://services-t.skyneticlabs.com/story/mainnet/snap.tar.lz4 | lz4 -dc - | tar -xf - -C $HOME/.story/story
mv $HOME/.story/story/priv_validator_state.json.backup $HOME/.story/story/data/priv_validator_state.json
curl https://services-t.skyneticlabs.com/story/mainnet/snap_geth.tar.lz4 | lz4 -dc - | tar -xf - -C $HOME/.story/geth/story/geth
sudo systemctl restart story story-geth
sudo journalctl -u story-geth -u story -f
```
</details>


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

**SkyneticLabs** contributes to the Story ecosystem by maintaining:

- Reliable and secure validator infrastructure  
- Publicly accessible endpoints and tools  
- Guides, scripts, and best practices for the community

📘 You can find all **Story-related services**, as well as **security** and **monitoring guides**, in the main documentation:  
👉 [https://skyneticlabs.gitbook.io/docs/](https://skyneticlabs.gitbook.io/docs/)  

---

<p align="center">
  <sub><i>Empowering modular blockchain infrastructure with transparency and open access.</i></sub>
</p>

<p align="center"> <a href="README.md">← Back to main portal</a> </p> 
