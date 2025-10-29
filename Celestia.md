# <img src="https://raw.githubusercontent.com/Skyneticlabs/Logo/main/celestia-logo.png" width="30" align="center"> &nbsp; Celestia Network

Welcome to the **Celestia Validator Portal** — your access point for SkyneticLabs’ public infrastructure, snapshots, and tools supporting the Celestia ecosystem.

<section class="endpoint-section">
  <h2> Endpoint</h2>
  <p>Access public RPC, API, and gRPC endpoints for Celestia Mainnet and Testnet.</p>

  <details>
    <summary> ⚫ Mainnet Endpoints</summary>
    <ul>
      <li><strong>RPC:</strong> <a href="https://celestia-m-rpc.skyneticlabs.com" target="_blank">https://celestia-m-rpc.skyneticlabs.com/</a></li>
      <li><strong>API:</strong> <a href="https://celestia-m-api.skyneticlabs.com" target="_blank">https://celestia-m-api.skyneticlabs.com</a></li>
      <li><strong>gRPC:</strong> <a href="celestia-m-grpc.skyneticlabs.com:443" target="_blank">celestia-m-grpc.skyneticlabs.com:443</a></li>
    </ul>
  </details>

  <details>
    <summary> ⚪ Testnet Endpoints</summary>
    <ul>
      <li><strong>RPC:</strong> <a href="https://celestia-t-rpc.skyneticlabs.com" target="_blank">https://celestia-t-rpc.skyneticlabs.com/</a></li>
      <li><strong>API:</strong> <a href="https://celestia-t-api.skyneticlabs.com" target="_blank">https://celestia-t-api.skyneticlabs.com</a></li>
      <li><strong>gRPC:</strong> <a href="celestia-t-grpc.skyneticlabs.com:443" target="_blank">celestia-t-grpc.skyneticlabs.com:443</a></li>
    </ul>
  </details>
</section>

<section class="snapshot-section">
  <h2>Snapshots</h2>
  <p>Download and restore ready-to-use snapshots to quickly sync your Celestia Mainnet or Testnet node.</p>

  <details>
    <summary>⚫ Mainnet Snapshot</summary>
    <p>Use the following commands to download and restore the latest snapshot for Celestia Mainnet:</p>
    <pre><code>cd $HOME
sudo systemctl stop celestia-appd

cp $HOME/.celestia-app/data/priv_validator_state.json $HOME/.celestia-app/priv_validator_state.json.backup

rm -rf $HOME/.celestia-app/data

curl -L https://services-m.skyneticlabs.com/celestia/snapshot_mainnet.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.celestia-app/

mv $HOME/.celestia-app/priv_validator_state.json.backup $HOME/.celestia-app/data/priv_validator_state.json

sudo systemctl restart celestia-appd && sudo journalctl -u celestia-appd -f
</code></pre>
  </details>

  <details>
    <summary>⚪ Testnet Snapshot</summary>
    <p>Use the following commands to download and restore the latest snapshot for Celestia Testnet:</p>
    <pre><code>cd $HOME
sudo systemctl stop celestia-appd

cp $HOME/.celestia-app/data/priv_validator_state.json $HOME/.celestia-app/priv_validator_state.json.backup

rm -rf $HOME/.celestia-app/data

curl -L https://services-t.skyneticlabs.com/celestia/snapshot_testnet.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.celestia-app/

mv $HOME/.celestia-app/priv_validator_state.json.backup $HOME/.celestia-app/data/priv_validator_state.json

sudo systemctl restart celestia-appd && sudo journalctl -u celestia-appd -f
</code></pre>
  </details>
</section>

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
