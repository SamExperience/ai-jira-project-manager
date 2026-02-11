# AI Jira Project Manager: AI | Bot Telegram | n8n

![n8n](https://img.shields.io/badge/n8n-ED4B21?style=for-the-badge&logo=n8n&logoColor=white)
![Jira](https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=Jira&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram-26A5E4?style=for-the-badge&logo=Telegram&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-4285F4?style=for-the-badge&logo=google-gemini&logoColor=white)

## Motivation
This project was developed as a personal initiative to solve a practical workplace challenge. I designed and built this tool to optimize my daily workflow, simplify task entry, and improve overall productivity. It demonstrates how AI-driven automation can transform personal organization into a structured, professional process.

## Overview
This advanced automation framework transforms a standard Telegram Bot into an intelligent Project Management Assistant. By leveraging **n8n** as the orchestration engine and **Gemini AI** as the Natural Language Interpreter, the workflow allows users to manage Jira tasks through conversational Italian. The AI processes these inputs and executes structured commands in professional technical English.

## Key Features
* **Conversational Task Management**: Create, update, and list Jira tasks using natural language.
* **Intelligent Translation (NLP)**: Automatically converts informal Italian user input into professional technical English for Jira fields (Summary and Description).
* **Real-time Feedback Loop**: Provides immediate raw output from the AI to ensure transparency and command confirmation.
* **Activity Logging**: Every operation is synchronized in real-time with **Google Sheets** for auditing and historical reporting.
* **Efficient Process Flow**: Features a Gateway filter to ignore empty polls and an automated offset management system to prevent execution loops.

## Technical Architecture
1. **Trigger**: A scheduled trigger polls the Telegram API every 5 seconds.
2. **Filtering**: A gateway node validates incoming data, ensuring the workflow only proceeds if new messages are detected.
3. **AI Reasoning**: An AI Agent (Gemini) interprets intent, translates content, and formats data into a structured JSON payload.
4. **Execution Logic**: A router directs the payload to the appropriate Jira action (Create Issue, Transition Status, or Fetch List).
5. **Persistence**: Actions are logged in Google Sheets, and a formatted response is sent back to the user via Telegram.



## Prerequisites
To deploy this workflow, you will need:
* An active **n8n** instance.
* A **Telegram Bot** token (via @BotFather).
* A **Jira Cloud** account with API access.
* A **Google Cloud** service account for Google Sheets integration.
* A **Google Gemini (PaLM) API Key**.

## Installation and Setup
1. **Import Workflow**: Download the `workflow.json` file from this repository and import it into your n8n workspace.
2. **Configure Credentials**: Set up your secure credentials in n8n for Telegram, Jira, Google Sheets, and Google Gemini.
3. **Activation**: Save and enable the workflow. The bot will start polling for commands immediately.

## Security and Privacy
* **Credential Management**: All API keys and tokens are handled through n8n's encrypted vault and are **not** included in the exported JSON file.
* **Anonymization**: This public version uses placeholders (e.g., `YOUR_PROJECT_NAME`) to ensure data privacy while maintaining functional logic.

---
*Developed as a personal productivity tool for professional workflow optimization.*

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
