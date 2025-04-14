# CCS_2025_Privacy_Cost_of_Fun

## Supplementary Materials

# 1. Tool Setup and Configuration

# 1.1 Burp Suite Setup
Version Used: Burp Suite Community Edition v2023.7.1
Environment: Mobile device traffic was routed through Burp Suite installed on a local workstation.
Steps:
Configured Burp Suite as an intercepting proxy.
Installed Burp's CA certificate on the mobile device for HTTPS traffic decryption.
Captured and filtered requests related to mini-game activity (identified by endpoints such as /effect/api/category/effects, /tfe/api/request_combine/v1/, etc.).
1.2 JS Miner Extension
Tool: JS Miner
Purpose: To scan inline JavaScript and JSON files for sensitive keywords, API calls, and embedded tracking scripts.
Integration: Installed as a Burp extension through the BApp Store.
Limitations: JS Miner was used only as an initial detection tool; all flagged issues were manually reviewed for accuracy.

# 2. ChatGPT Prompt Engineering

# 2.1 Objective
To assist in analyzing discrepancies between TikTok’s privacy policy, observed behavior during gameplay, and network traffic logs.

# 2.2 Model Used
GPT Version: ChatGPT-4o via OpenAI
Interface: API + ChatGPT Pro interface
# 2.3 Prompt Design Strategy
Prompts were iteratively refined to extract actionable insights from gameplay logs, privacy policy documents, and observed network behavior.

# Example Initial Prompt:

"Identify any user data collected by TikTok mini-games."

# Refined Prompt:

"Based on the network traffic logs and privacy policy text, clearly identify which types of user data were mentioned, vague, omitted, or inconsistent in the context of TikTok mini-game interactions."
Other Used Prompts:

“What sensitive data is collected during mini-game gameplay that is not disclosed in TikTok’s privacy policy?”
“Which API calls in the captured traffic suggest the use of face tracking or device sensors?”
“Summarize what third-party involvement (if any) is visible in the JavaScript or network traces.”
# 3. Manual Validation

All insights generated through GPT-4o were manually validated by cross-checking against:
Raw network traffic logs (Burp Suite)
JavaScript payloads (viewed in decoded form)
TikTok privacy policy document (via Privacify tool)
Only results confirmed by direct evidence (e.g., endpoint names, payload values, headers) were included in the main analysis.
