# Deploy the node by running:
```bash
[ -f "beacon.sh" ] && rm beacon.sh; wget -q https://raw.githubusercontent.com/manish8227/blockcast/main/beacon.sh && chmod +x beacon.sh && ./beacon.sh 
```
OR
```bash
[ -f "beacon.sh" ] && rm beacon.sh; curl -s -o beacon.sh https://raw.githubusercontent.com/manish8227/blockcast/main/beacon.sh && chmod +x beacon.sh && ./beacon.sh
```

**At final step it would generate an output that looks like:**
Hardware ID: bkc-hw-xxxxxxxxxxxxxxxxxxxx
Challenge Key: bkc-ch-xxxxxxxxxxxxxxxxxxxx
Registration URL: https://app.blockcast.network/register?hwid={hwid}&challenge-key={challenge-key}

Note:
Hardware ID is a unique public identifier for your device.
Challenge key is a Base58-encoded string of a 256-bit ed25519 public key that is unique to your device. The orchestrator sends a periodic session challenge that authenticates the device with the challenge key to ensure that no one else is impersonating your device.

*NOTE: Backup your private key and keep it safe (in ~$HOME/certs/gateway.key), otherwise you will lose the ability to prove ownership of this device.*


**Registering your docker instance on the web portal:**

Go to the [web portal](https://app.blockcast.network/) and log in
Copy and paste the registration URL from the console output with your pre-filled hardware ID and challenge key into your browser.

OR

Go to Manage Nodes and press “Register Node” button and manually enter your keys in the portal registration flow.
_You will need to enable location from your browser to continue._


**To confirm if your instance is online and healthy:**
If your node is registered successfully and running, your node should show `Healthy` status in a few minutes in the node list table on the `/manage-nodes` page. 
Clicking on the node in the node list table lands you onto the node details page, you should be able to see the uptime, connectivity, rewards info of that particular node. The nodes need to be online for 6 hours in order for the first connectivity test to run. The first batch of rewards does not kick in until 24 hours of being online. 

