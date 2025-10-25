# 🚀 Automated LinkedIn Content Factory: AI-Powered Scheduled Posting with n8n

## Overview
This n8n workflow provides a complete, full-cycle automation solution for generating, drafting, publishing, and tracking professional content on LinkedIn. It is designed for Business Analysts, consultants, or anyone in the tech industry looking to maintain a consistent, high-value brand presence with **zero manual effort**.

## ⚙️ Workflow Logic (3 Key Steps)

The workflow runs on a set schedule (`every 6 hours`, as configured in the JSON) and executes the following steps:

1.  **Idea Generation (`Schedule Trigger` -> `AI Content Research`):**
    * The schedule triggers the workflow.
    * It calls an AI tool (e.g., OpenAI or Claude) with a defined prompt to generate a new, highly targeted content topic focused on **Business Analysis, AI, and Automation** trends.

2.  **Content Creation & Formatting (`AI Copywriter` -> `Hashtag Generator`):**
    * The new topic is passed to a second AI node which drafts the full LinkedIn post text and generates an image prompt.
    * A dedicated node creates a set of relevant, high-impact hashtags for maximum visibility.

3.  **Publishing & Tracking (`LinkedIn` -> `Google Sheets`):**
    * The completed post (text + image data) is sent via the **LinkedIn** node to publish directly to your feed.
    * The final **Google Sheets** node logs the post title and URL, creating a simple tracker for performance monitoring.

## 🛠️ Setup Instructions

To import and run this workflow successfully, you must configure the following:

### 1. Import the Workflow

1.  Open your n8n instance.
2.  Go to **Workflows**.
3.  Click the **+ New** button or the **Import** option.
4.  Copy the raw JSON content (this file) and paste it into the JSON import field, or upload the file directly.

### 2. Configure Credentials (Essential Security Step)

This JSON was exported **without** the actual sensitive data. You must manually connect your API keys for the following nodes:

| Node Name | Service Required | Action Required |
| :--- | :--- | :--- |
| **AI Content Research / AI Copywriter** | OpenAI / Claude (or similar) | Create or link your **API Key** credentials. |
| **LinkedIn** | LinkedIn | Create or link a **LinkedIn Access Token** credential. |
| **Append or update row** | Google Sheets | Create or link a **Google Sheets** credential with write access to your desired tracking sheet. |

### 3. Review & Activate

1.  Verify the prompt text in the AI nodes to ensure the content tone matches your professional voice.
2.  Set the `Schedule Trigger` to your desired posting frequency.
3.  Click **Activate** (toggle the switch in the top right) to turn the workflow ON.

---

### **Dependencies**

* **n8n Version:** (Update with your current n8n version, if known)
* **Nodes Used:** `Schedule Trigger`, `AI Language Model` (x2), `Merge`, `HTTP Request`, `LinkedIn`, `Google Sheets`
