🛡️ Web3 Wallet Personality & Agentic Security AI
An advanced n8n automation workflow leveraging the Alchemy API and Google Gemini AI to analyze the "Personality" of crypto wallets and identify real-time security risks.

🚀 Overview
This project goes beyond simple data visualization. It is a functional AI Agent that interprets blockchain data like a human analyst. By scanning transaction history, it categorizes wallet addresses into specific behavioral profiles:

Whale: High-volume institutional or individual traders.

Degen/Gambler: High-frequency traders focused on volatile assets and new meme coins.

Patient Investor: Long-term holders with low turnover and "diamond hand" behavior.

Bot/Airdrop Hunter: Wallets exhibiting automated, multi-wallet farming patterns.

🛠️ Tech Stack
Automation: n8n (Self-hosted via Docker)

Blockchain Infrastructure: Alchemy API (Asset Transfers)

AI Engine: Google Gemini AI

Backend Logic: Node.js (Custom n8n Code Nodes)

Data Storage: n8n Data Table / MariaDB

🔄 Workflow Logic
HTTP Request (Alchemy): Uses the alchemy_getAssetTransfers method to fetch full history across External, ERC20, ERC721, and ERC1155 categories.

Code Node (Data Processor): Sanitizes raw JSON data, extracts timestamps, and simplifies values to optimize the AI's context window.

Gemini AI Node: Performs deep behavioral analysis to determine the wallet's "Personality" and assigns a quantitative Risk Score.

Formatting Node: Parses the AI's natural language response into structured fields (personality, riskScore, summary).

Action Layer:

Saves final analysis to an n8n Data Table for historical tracking.

Agentic Alert: If the Risk Score > 7, an automated security notification is triggered (e.g., via WhatsApp/Telegram).

📝 Example Output
JSON
{
  "personality": "Bot/Airdrop Hunter",
  "riskScore": "7/10",
  "hinglishSummary": "BAYC ki hai lambi kataar, har wallet mein ek naya yaar. Airdrop ke liye full taiyaari!"
}
⚙️ Installation & Setup
Download: Download the workflow.json file from this repository.

Import: Go to your n8n instance and select Import from File.

Credentials: * Add your Alchemy API Key in the HTTP Request node.

Add your Google Gemini API Key in the Google Gemini node.

Deploy: Set the workflow to Active or run it manually to scan a specific address.
