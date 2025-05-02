---
description: For corporate networks or VPNs
---

# Allowing Access to Mindstudio From Your Network

Some corporate networks or VPNs may block access to required MindStudio services, preventing the platform and its features from working as intended. To ensure full access, your IT or network administrator should allow traffic to the following domains and protocols:

## Required Domains & Protocols

Please make sure the following are **whitelisted**:

<table><thead><tr><th width="325.6536865234375">URL / Protocol</th><th>Description</th><th data-hidden>Purpose</th></tr></thead><tbody><tr><td><code>https://app.mindstudio.ai</code></td><td>The main MindStudio user interface</td><td>Web App Access</td></tr><tr><td><code>https://v1.mindstudio-api.com</code></td><td>Core API for agent runs and management</td><td>API Access</td></tr><tr><td><code>wss://v1-socket.mindstudio-api.com</code></td><td>Real-time communication (e.g., for agent logs or chat flows)</td><td><p>WebSockets </p><p>(Live Connections)</p></td></tr><tr><td><code>https://files.mindstudio-cdn.com</code></td><td>User-uploaded and agent-related files</td><td>File Hosting</td></tr><tr><td><code>https://images.mindstudio-cdn.com</code></td><td>Hosted image content for agents and UI</td><td>Image Assets</td></tr><tr><td><code>*@mindstudio-hooks.com</code></td><td>Required to send emails via agent workflows</td><td>Outbound Email Integration</td></tr></tbody></table>

## Recommendations

* **Firewall Rules:** No firewalls should be blocking outgoing HTTPS (TCP port 443) or WSS (WebSocket Secure) traffic to the above URLs.
* **DNS Whitelisting:** If using a DNS-based content filter, all the above domains must be resolved and accessible.

***

## Still Having Issues?

Contact us at [support@mindstudio.ai](mailto:support@mindstudio.ai) with any network logs or firewall reports, and we’ll be happy to help your IT team troubleshoot.
