# Teams Chat Moderation Logic App – CST8917 Lab 3

This project implements a Microsoft Teams chat content moderation system using Azure Logic Apps. The system monitors new channel messages and sends an email alert when inappropriate content is detected based on keyword filtering.

---

## 🔍 Objective

To demonstrate how to automate real-time message moderation in Microsoft Teams using Azure Logic Apps with the following:
- Microsoft Teams trigger
- Keyword-based content filter (via Condition control)
- Email notification action when a policy violation is found

---

## 🧠 Technologies Used

- **Azure Logic Apps (Consumption)**
- **Microsoft Teams Connector**
- **Office 365 Outlook Connector**

---

## 📊 Moderation Flowchart

![Flowchart](./diagrams/Teams%20moderator%20flowchart.png)

---

## ⚙️ Workflow Setup

### 1. Trigger: Microsoft Teams
- **Trigger:** "When a new channel message is added"
- This monitors new messages posted in a specified Microsoft Teams channel.

### 2. Condition Control: Keyword Check
- Evaluates if the message **contains inappropriate words** such as:
  - `"test"`
  - *(More keywords can be added as needed)*

### 3. Action on Violation: Send Email
- If a violation is found (`True` branch):
  - An email is sent via **Send an email (V2)** using Office 365 Outlook.
  - Email includes the message content and a brief alert.
- If clean (`False` branch): no action is taken.

---

## 🧪 Testing

Test cases included sending different messages to the configured Teams channel:
- ✅ Clean message → No email sent
- ❌ Message containing `"test"` → Email notification sent successfully

---

## 🧱 Limitations & Next Steps

- **Keyword filtering is case-sensitive**
- No advanced AI-based detection was used
- Consider integrating:
  - Azure Cognitive Services (Content Moderator)
  - Azure Functions for preprocessing or enrichment
  - Logging or audit trail storage (e.g., Azure Blob or Cosmos DB)

---

## 🎥 Demo

**


