# CCS_2025_Privacy_Cost_of_Fun

## Android App Traffic Analysis with Burp Suite
```
This guide outlines the step-by-step process for setting up Burp Suite with an Android emulator (Genymotion) to capture and analyze network traffic from mobile applications—specifically in the context of studying WebView-based games and privacy behaviors.
```
### Requirements
- `-- Burp Suite Professional (Professiona Edition)`
- `-- JS Miner plugin for Burp Suite`
- `-- Genymotion Android Emulator`
- `-- Internet-connected desktop PC and Genymotion emulator, on the same Wi-Fi network`

### Step-by-Step Setup
#### Burp Suite Configuration
- `-- Install and launch Burp Suite Professional on your desktop`
- `-- Enable the Proxy > Intercept > Intercept is on option`
- `-- Go to Proxy > Options > Proxy Listeners and ensure it's listening on the desired interface (e.g., 127.0.0.1:8080)`
- `-- Install and activate the JS Miner plugin if analyzing JavaScript resources is required`
#### Configure Genymotion Android Emulator
- `-- Launch your Genymotion device`
- `-- Go to Wi-Fi settings > hold on the connected network > tap Modify network`
- `-- Set the proxy to Manual:`
    - ` -- Proxy hostname: IP address of the host PC running Burp Suite`
    - ` -- Proxy port: 8080 (or your Burp listener port)`
### Install Burp Certificate on Genymotion
- ` -- In Burp, visit http://burp in the Genymotion browser`
- ` -- Download the CA certificate (named cacert.der)`
- ` -- Rename the certificate to cacert.cer`
- ` -- In Genymotion, go to Settings > Security > Install from SD card, and install the certificate`
- ` -- Use Frida to bypass SSL pinning for modern apps`
### Traffic Monitoring
- ` -- Launch the TikTok app , Begin gameplay and interactions`
- ` -- Burp Suite will now capture: HTTP/HTTPS requests and responses, WebSocket messages, Redirects and external resource loads, API calls`


