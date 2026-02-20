
<img width="1366" height="768" alt="Screenshot (414)" src="https://github.com/user-attachments/assets/fa4b291e-3bd9-4600-8781-2c95b257253f" />


# n8n AI-Powered Email Automation Workflow

This repository demonstrates a professional email automation workflow built with **n8n**. The workflow integrates an AI Agent, Google Sheets for contacts, Gmail for sending emails, and OpenAI GPT-5 Mini for natural email drafting.

---

## Workflow Components

### 1. Webhook Node

* Receives incoming POST requests with email data.
* Example payload:

```json
{
  "recipient": "John Doe",
  "subject": "Project Update",
  "message": "Please provide the status of the current project by EOD."
}
```

### 2. AI Agent Node

* Drafts professional emails based on user instructions.
* Confirms email content with the user before sending.
* Always signs off as **Olalekan**.
* Uses rules for tone, structure, and compliance.

### 3. OpenAI Chat Model (GPT-5 Mini)

* Powers the AI Agent to generate natural, professional emails.
* Ensures clarity, proper formatting, and human-like style.

### 4. Google Sheets Node (`myContacts`)

* Fetches recipient email addresses from a Google Sheet.
* Ensures accurate email delivery.

### 5. Gmail Node (`send_email`)

* Sends emails after user confirmation.
* Uses verified email addresses from the `myContacts` node.

### 6. Respond to Webhook Node

* Returns confirmation or errors to the original webhook request.

---

## Workflow Features

* ✅ Drafts professional, clear, and human-like emails.
* ✅ Confirms email drafts with users before sending.
* ✅ Retrieves verified recipient emails from Google Sheets.
* ✅ Uses GPT-5 Mini for AI-powered content generation.
* ✅ Ensures compliance and professional email standards.

---

## Getting Started

1. Import the workflow JSON into n8n.
2. Configure credentials:

   * Google Sheets OAuth2 for contact retrieval.
   * Gmail OAuth2 for sending emails.
   * OpenAI API key for AI Agent.
3. Set the webhook URL and test incoming requests.
4. Monitor the AI Agent for proper email drafting and confirmation.

---

## Example Workflow Flow

1. Webhook receives email request.
2. AI Agent drafts email and confirms with the user.
3. myContacts retrieves recipient email from Google Sheets.
4. Gmail node sends email after confirmation.
5. Respond to Webhook returns status.

---

## Compliance and Safety

* Emails must not contain threats, phishing, illegal content, hate speech, or sensitive credentials.
* The AI Agent refuses unsafe content and suggests alternatives.
* User approval is required before sending any email.

---

## Resources

* [n8n Documentation](https://docs.n8n.io)
* Workflow JSON file: `email_ai_agent_workflow.json`
* Google Sheet contact template included in `myContacts` node.

---

> This workflow demonstrates a professional, safe, and efficient approach to AI-powered email automation using n8n and OpenAI.
