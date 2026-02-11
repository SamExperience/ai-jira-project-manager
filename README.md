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

## Usage Guide
Once the workflow is active, you can interact with your Telegram Bot using these commands:

* **Create a Task**: Send `@crea [Your Task Details]`
  * *Example:* `@crea preparare la documentazione per lo stage`
  * *Result:* The AI translates it to English and creates a Jira Issue.
* **Update Status**: Send `@aggiorna [Issue-ID]: [New Status]`
  * *Example:* `@aggiorna CORE-123: in corso` (Supports: todo, in progress, done)
* **List Tasks**: Send `@lista`
  * *Result:* The bot returns a formatted list of all your active (not done) tasks.

## Technical Architecture
1. **Trigger**: A scheduled trigger polls the Telegram API every 5 seconds.
2. **Filtering**: A gateway node validates incoming data, ensuring the workflow only proceeds if new messages are detected.
3. **AI Reasoning**: An AI Agent (Gemini) interprets intent, translates content, and formats data into a structured JSON payload.
4. **Execution Logic**: A router directs the payload to the appropriate Jira action.
5. **Persistence**: Actions are logged in Google Sheets, and a response is sent via Telegram.



## Prerequisites
* An active **n8n** instance.
* A **Telegram Bot** token (via @BotFather).
* A **Jira Cloud** account.
* A **Google Cloud** service account for Sheets.
* A **Google Gemini API Key**.

## Installation and Setup
1. **Import Workflow**: Download `workflow.json` from this repository and import it into n8n.
2. **Configure Credentials**: Set up your credentials in n8n for Telegram, Jira, Google Sheets, and Google Gemini.
3. **Activation**: Save and enable the workflow.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Developed as a personal productivity tool for professional workflow optimization.*
