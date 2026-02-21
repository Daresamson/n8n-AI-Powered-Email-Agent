
<img width="1366" height="768" alt="Screenshot (414)" 
  src="https://github.com/user-attachments/assets/fa4b291e-3bd9-4600-8781-2c95b257253f" />


# n8n AI-Powered Email Automation Workflow

This project demonstrates a production-ready AI email automation system built with **n8n**, powered by **OpenAI GPT-5 Mini**, triggered via an **ElevenLabs AI Agent**, and integrated with **Google Sheets** and **Gmail**.

The workflow is designed to intelligently draft, confirm, and send professional emails in a secure and structured manner.

---

# 🧠 System Architecture Overview

**Voice / User Input → ElevenLabs Agent → n8n Webhook → AI Drafting → Contact Lookup → Gmail Send → Response Confirmation**

---

# 🚀 Stage-by-Stage Workflow Process

---

## 🔹 Stage 1: Trigger (ElevenLabs AI Agent)

The process begins with an **ElevenLabs conversational AI agent**.

### What Happens:

* A user speaks or submits an email request to the ElevenLabs agent.
* The agent structures the request into a formatted JSON payload.
* The agent sends a POST request to the n8n **Webhook URL**.

### Example Payload Sent to n8n:

```json
{
  "recipient": "John Doe",
  "subject": "Project Update",
  "message": "Please provide the status of the current project by EOD."
}
```

This webhook call activates the automation workflow inside n8n.

---

## 🔹 Stage 2: Webhook Node (n8n Entry Point)

The **Webhook Node** acts as the workflow entry gate.

### Responsibilities:

* Receives structured data from ElevenLabs.
* Validates incoming payload.
* Passes data to the AI Agent Node.

This ensures clean and structured processing from the very beginning.

---

## 🔹 Stage 3: AI Agent Node (Email Intelligence Layer)

This is the brain of the workflow.

Powered by **OpenAI GPT-5 Mini**, the AI Agent:

* Drafts a professional email.
* Applies tone, structure, and formatting rules.
* Ensures compliance and safety.
* Always signs off as **Olalekan**.
* Requests user confirmation before sending.

### Drafting Rules:

* Clear subject alignment
* Professional greeting
* Structured body
* Proper closing
* No unsafe or prohibited content

If content violates compliance rules, the AI agent refuses and suggests alternatives.

---

## 🔹 Stage 4: OpenAI Chat Model (GPT-5 Mini)

The **GPT-5 Mini model** powers the language generation process.

### Capabilities:

* Natural, human-like email drafting
* Context-aware tone adjustment
* Professional formatting
* Intelligent rewriting if needed

This ensures the final output sounds authentic and business-ready.

---

## 🔹 Stage 5: Google Sheets Node (`myContacts`)

Before sending the email, the workflow verifies the recipient’s address.

### What It Does:

* Searches the `myContacts` Google Sheet
* Retrieves the correct email address
* Prevents sending to incorrect or unverified addresses

This adds a layer of reliability and accuracy.

---

## 🔹 Stage 6: Gmail Node (`send_email`)

Once:

* The draft is confirmed by the user
* The recipient email is verified

The Gmail node sends the email securely via OAuth2 authentication.

### Security:

* Uses verified Google credentials
* Prevents unauthorized sending
* Logs sending status

---

## 🔹 Stage 7: Respond to Webhook Node

Finally, the workflow returns a structured response back to ElevenLabs.

Possible responses:

* ✅ Email sent successfully
* ❌ Recipient not found
* ⚠️ Confirmation required
* 🚫 Unsafe content rejected

This ensures full communication feedback to the original requester.

---

# ✨ Key Features

* ✅ Voice-triggered automation (via ElevenLabs)
* ✅ AI-generated professional emails
* ✅ Mandatory user confirmation
* ✅ Google Sheets contact verification
* ✅ Secure Gmail sending
* ✅ Compliance and content filtering
* ✅ Fully automated end-to-end workflow

---

# 🔐 Compliance & Safety Framework

The AI Agent will refuse to generate emails that include:

* Phishing attempts
* Threats or harassment
* Hate speech
* Illegal instructions
* Sensitive credentials
* Fraudulent impersonation

User approval is required before any email is sent.

---

# 🛠 Setup Instructions

### 1️⃣ Import Workflow

Import `email_ai_agent_workflow.json` into n8n.

### 2️⃣ Configure Credentials

* Google Sheets OAuth2
* Gmail OAuth2
* OpenAI API Key
* Webhook production URL

### 3️⃣ Configure ElevenLabs

* Connect ElevenLabs agent to the n8n Webhook URL
* Format payload correctly
* Enable POST method

### 4️⃣ Test the Flow

* Trigger via ElevenLabs
* Confirm email draft
* Verify Gmail sending
* Monitor webhook response

---

# 📌 Example Workflow Execution

1. User speaks request to ElevenLabs.
2. ElevenLabs sends structured data to n8n webhook.
3. AI Agent drafts email.
4. User confirms draft.
5. Google Sheets retrieves verified recipient.
6. Gmail sends email.
7. Webhook returns success response.

---

# 📚 Resources

* n8n Documentation: [https://docs.n8n.io](https://docs.n8n.io)
* OpenAI Platform: [https://platform.openai.com](https://platform.openai.com)
* ElevenLabs: [https://elevenlabs.io](https://elevenlabs.io)

---

# 🧩 Project Purpose

This workflow demonstrates how conversational AI, workflow automation, and secure email infrastructure can be combined to create a scalable AI-powered communication system.

It is designed for:

* Founders
* Automation engineers
* AI builders
* Productivity enthusiasts

