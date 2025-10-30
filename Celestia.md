# <img src="https://raw.githubusercontent.com/Skyneticlabs/Logo/main/celestia-logo.png" width="30" align="center"> &nbsp; Celestia Network

Welcome to the **Celestia Validator Portal** — your access point for SkyneticLabs’ public infrastructure, snapshots, and tools supporting the Celestia ecosystem.

---

## 🌐 Endpoint

Access public RPC, API, and gRPC endpoints for Celestia Mainnet and Testnet.

<details>
  <summary>⚫ Mainnet Endpoints</summary>

- **RPC:** [https://celestia-m-rpc.skyneticlabs.com](https://celestia-m-rpc.skyneticlabs.com)  
- **API:** [https://celestia-m-api.skyneticlabs.com](https://celestia-m-api.skyneticlabs.com)  
- **gRPC:** `celestia-m-grpc.skyneticlabs.com:443`
</details>

<details>
  <summary>⚪ Testnet Endpoints</summary>

- **RPC:** [https://celestia-t-rpc.skyneticlabs.com](https://celestia-t-rpc.skyneticlabs.com)  
- **API:** [https://celestia-t-api.skyneticlabs.com](https://celestia-t-api.skyneticlabs.com)  
- **gRPC:** `celestia-t-grpc.skyneticlabs.com:443`
</details>

---

## 📦 Snapshots

Access Celestia **Mainnet** and **Testnet** snapshot resources and installation guides.

### 🌐 Snapshot directories
You can explore snapshot directories here:
- **Mainnet:** [https://services-m.skyneticlabs.com/celestia/](https://services-m.skyneticlabs.com/celestia/)  
- **Testnet:** [https://services-t.skyneticlabs.com/celestia/](https://services-t.skyneticlabs.com/celestia/)

Each directory contains:
- `addrbook.json` and `genesis.json` — configuration files  
- Snapshot archives (with pruning)  
- Metadata files with snapshot creation date and block height

---

<details>
<summary>⚫ Mainnet Snapshot — install guide</summary>

Use the following commands to restore **Celestia Mainnet** snapshot:  
📁 [View directory](https://services-m.skyneticlabs.com/celestia/)  
📦 [Download snapshot](https://services-m.skyneticlabs.com/celestia/celestia-snap-m.tar.lz4)

```bash
cd $HOME
sudo systemctl stop celestia-appd
cp $HOME/.celestia-app/data/priv_validator_state.json $HOME/.celestia-app/priv_validator_state.json.backup
rm -rf $HOME/.celestia-app/data
curl -L https://services-m.skyneticlabs.com/celestia/celestia-snap-m.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.celestia-app/
mv $HOME/.celestia-app/priv_validator_state.json.backup $HOME/.celestia-app/data/priv_validator_state.json
sudo systemctl restart celestia-appd && sudo journalctl -u celestia-appd -f
```
</details>

<details>
<summary>⚪ Testnet Snapshot — install guide</summary>

Use the following commands to restore **Celestia Testnet** snapshot:  
📁 [View directory](https://services-t.skyneticlabs.com/celestia/)  
📦 [Download snapshot](https://services-t.skyneticlabs.com/celestia/celestia-snap-t.tar.lz4)

```bash
cd $HOME
sudo systemctl stop celestia-appd
cp $HOME/.celestia-app/data/priv_validator_state.json $HOME/.celestia-app/priv_validator_state.json.backup
rm -rf $HOME/.celestia-app/data
curl -L https://services-t.skyneticlabs.com/celestia/celestia-snap-t.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.celestia-app/
mv $HOME/.celestia-app/priv_validator_state.json.backup $HOME/.celestia-app/data/priv_validator_state.json
sudo systemctl restart celestia-appd && sudo journalctl -u celestia-appd -f
```
</details>


---

##  About SkyneticLabs

**SkyneticLabs** contributes to the Celestia ecosystem by maintaining:

- Reliable and secure validator infrastructure  
- Publicly accessible endpoints and tools  
- Guides, scripts, and best practices for the community  

---

<p align="center">
  <sub><i>Empowering modular blockchain infrastructure with transparency and open access.</i></sub>
</p>

<p align="center"> <a href="README.md">← Back to main portal</a> </p> 
