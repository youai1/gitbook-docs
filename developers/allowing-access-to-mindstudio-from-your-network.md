---
description: For corporate networks or VPNs
---

# Allowing Access to Mindstudio From Your Network

Some corporate networks or VPNs may block access to required MindStudio services, preventing the platform and its features from working as intended. To ensure full access, your IT or network administrator should allow traffic to the following domains and protocols:

## Required Domains & Protocols

Please make sure the following are **whitelisted**:

<table><thead><tr><th width="163.982666015625">Purpose</th><th width="325.6536865234375">URL / Protocol</th><th width="257.98162841796875">Description</th></tr></thead><tbody><tr><td>Web App Access</td><td><code>https://app.mindstudio.ai</code></td><td>The main MindStudio user interface</td></tr><tr><td>API Access</td><td><code>https://v1.mindstudio-api.com</code></td><td>Core API for agent runs and management</td></tr><tr><td><p>WebSockets </p><p>(Live Connections)</p></td><td><code>wss://v1-socket.mindstudio-api.com</code></td><td>Real-time communication (e.g., for agent logs or chat flows)</td></tr><tr><td>File Hosting</td><td><code>https://files.mindstudio-cdn.com</code></td><td>User-uploaded and agent-related files</td></tr><tr><td>Image Assets</td><td><code>https://images.mindstudio-cdn.com</code></td><td>Hosted image content for agents and UI</td></tr><tr><td>Outbound Email Integration</td><td><code>*@mindstudio-hooks.com</code></td><td>Required to send emails via agent workflows</td></tr></tbody></table>

## Recommendations

* **SSL Inspection:** Ensure that if your network inspects SSL traffic, and that the domains listed above are excluded from interception or have proper certificate handling.
* **Firewall Rules:** No firewalls should be blocking outgoing HTTPS (TCP port 443) or WSS (WebSocket Secure) traffic to the above URLs.
* **DNS Whitelisting:** If using a DNS-based content filter, all the above domains must be resolved and accessible.

***

## Still Having Issues?

Contact us at [support@mindstudio.ai](mailto:support@mindstudio.ai) with any network logs or firewall reports, and we’ll be happy to help your IT team troubleshoot.
