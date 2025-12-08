<p align="center">
  <img src="https://dummyimage.com/1200x260/fb8c00/ffffff&text=Automated+Lead+Specialist+Workflow" alt="Automation Banner"/>
</p>

📩 Lead Management Automation using n8n + AI Agent + Slack + Gmail

This project showcases an automated Lead Management Workflow built using n8n, AI Agent, Slack, and Gmail.
The workflow acts like a 24/7 Lead Specialist, responding to new form submissions, generating personalized emails, and notifying the manager instantly.

🚀 Workflow Overview

When a user submits the n8n form:

Form Submission Trigger
Captures the following data:

Name

Do you like model cars?

Will you spend 1000 BDT for a diecast car?

Email

Submission time

AI Agent (OpenRouter Model)
Uses a custom system prompt to act as Mr. XYZ – Lead Communication Specialist at Diecast Cars Hub Ltd.

The AI Agent performs two independent tasks:

Task 1 — Client Email

If the user dislikes diecast cars → generate a soft, persuasive email to create interest

If the user likes diecast cars → generate an engaging email to encourage repeat buying

Ensures professional formatting, spacing, tone, and use of emojis where appropriate

This email is sent automatically through Gmail.

Task 2 — Slack Notification to Manager

Sends a formal update to manager Mohammad Toha

Includes all user responses

Briefs the manager about interest level + recommended next steps

Slack Node
Sends the AI-generated update message to the internal Slack channel.

Gmail Node
Sends the AI-generated client email directly to the lead.

🧠 AI Agent Prompt (Used inside n8n)
Your Name: Mr. XYZ
Your Role: Lead Specialist
Company Name: Diecast Cars Hub Ltd.

First Task is for client who will fill up the form. Under first task this mail will sent to client only:
You will act as a Lead Communication Specialist. When a user submits the n8n form, you will collect the submitted data and generate an email to the client. The form contains the client’s response regarding whether they like diecast cars or not.

If the user’s response is negative, you will write a persuasive email that gently encourages them toward developing interest and considering purchasing our products.

If the user’s response is positive, you will write an engaging email designed to turn the client into a repeat buyer.

Always follow formal and standard email formatting. Use appropriate:
indentation
line spacing
font size
emojis (where necessary but keep it professional)
and maintain clear, respectful tone.

Second Task is only for the manager you are working for. Under this second task you will send formall message to slack to inform your manager only :
You will also send a message in Slack to your manager, Mohammad Toha, informing him about the newly received lead and provide full user response as describption including all info user submitted. Maintain a professional, formal company tone while briefing him about the client's interest level and next actions.

Here is the information you will work:
{{ $json['What is your name?'] }}
{{ $json['Do you like model cars?'] }}
{{ $json['Will you spent 1000 BDT for a diecast car?'] }}
{{ $json['Your Email'] }}
{{ $json.submittedAt }}

🛠️ Tech Stack
Tool	Purpose
n8n	Workflow automation
OpenRouter AI Model	Generates personalized emails & Slack updates
Slack API	Manager notifications
Gmail API	Sending emails to clients
🖼️ Workflow Diagram

(Add your screenshot here — recommended filename: workflow.png)

🎯 Features

Auto-collects lead info

Auto-writes tailored emails

Auto-notifies the manager

Professional AI-generated communication

No manual typing or follow-ups

Works 24/7

📦 Repository Structure
/n8n_lead_workflow
│── workflow.json       # Exported n8n workflow
│── readme.md           # Project documentation
│── assets/
│     └── workflow.png  # Workflow diagram

📚 How to Use

Import workflow.json into your n8n instance

Add your:

Slack credentials

Gmail credentials

OpenRouter API key

Publish your n8n Form

Submit test data

Watch the system handle everything automatically 🎉

💡 Use Cases

Lead management

Automated onboarding

Customer interest scoring

AI-powered client communication

Internal team alerting

📞 Contact & Contributions

If you want help building similar automation workflows or integrating AI agents, feel free to open an issue or connect.