# 📧 n8n Multi-Step Email Follow-Up Automation

A smart, time-based email outreach and follow-up system built with **n8n**, **Google Sheets**, and **Gmail**. This workflow automatically sends initial emails and follow-ups after **2, 5, and 7 days**, while safely avoiding duplicate messages and stopping outreach once a lead replies.

---

## 🚀 Features

- ✅ Automated first outreach email
- ⏱️ Time-based follow-ups (2 / 5 / 7 days)
- 🧠 Dynamic date difference calculation (no hard delays)
- 📊 Google Sheets as a lightweight CRM
- 📬 Gmail integration for sending + labeling emails
- 🛑 Reply-safe logic (no follow-ups after reply)
- 🔁 Duplicate email prevention
- 📈 Easy to scale and debug

---

## 🧰 Tech Stack

- **n8n** – Workflow automation
- **Google Sheets** – Lead storage & status tracking
- **Gmail** – Email sending and labeling
- **Cron Triggers** – Scheduled execution

---

## 🗂️ Google Sheets Structure

Your Google Sheet should include at least the following columns:

| Column Name | Description |
|------------|-------------|
| email | Lead email address |
| status | Current outreach stage |
| is_replied | yes / no |
| first_msg_time | Timestamp of first email |
| first_followup_time | Timestamp of follow-up 1 |
| second_followup_time | Timestamp of follow-up 2 |

### 🔖 Recommended Status Values

- `new`
- `first_mail_sent`
- `followup_one_sent`
- `followup_two_sent`
- `completed`

> ⚠️ Do not reuse status names across steps.

---

## 🔄 Workflow Overview

The automation is divided into logical stages:

### 1️⃣ Initial Email Workflow
- Cron trigger runs daily
- Reads leads with `status = new`
- Sends first email via Gmail
- Adds Gmail label (e.g. `first-email`)
- Saves `first_msg_time`
- Updates status to `first_mail_sent`

---

### 2️⃣ Follow-Up 1 (After 2 Days)
- Cron trigger checks leads with `status = first_mail_sent`
- Calculates: `now - first_msg_time`
- If ≥ 2 days and `is_replied = no`
- Sends follow-up email
- Saves `first_followup_time`
- Updates status to `followup_one_sent`

---

### 3️⃣ Follow-Up 2 (After 5 Days)
- Checks leads with `status = followup_one_sent`
- Calculates: `now - first_followup_time`
- If ≥ 5 days and no reply
- Sends second follow-up
- Saves `second_followup_time`
- Updates status to `followup_two_sent`

---

### 4️⃣ Follow-Up 3 (After 7 Days)
- Checks leads with `status = followup_two_sent`
- Calculates: `now - second_followup_time`
- If ≥ 7 days and no reply
- Sends final follow-up
- Updates status to `completed`

---

## 🧮 Date Calculation Logic (Important)

All timing checks are done dynamically using:

```
(Date.now() - new Date(previous_step_time).getTime())
/ (1000 * 60 * 60 * 24)
```

✅ Prevents broken delays
✅ Avoids `NaN` errors
✅ Safe for workflow restarts

---

## 🏷️ Gmail Labeling

Each email adds a label automatically:

- `first-email`
- `followup-1`
- `followup-2`
- `followup-3`

This gives full visibility inside Gmail.

---

## 🛡️ Safety & Best Practices

- ✔ Always compare against **current time** (`Date.now()`)
- ✔ Never subtract two sheet fields directly
- ✔ Guard against empty date fields
- ✔ Remove placeholder values like `"="` in updates
- ✔ Use one status per workflow stage

---

## 📈 Who This Is For

- Sales teams
- Customer success managers
- Founders doing outreach
- Agencies running cold email campaigns
- Anyone who wants CRM-like automation without a CRM

---

## 🧠 Future Improvements

- Reply detection via Gmail trigger
- Single-cron unified workflow
- Lead scoring
- Slack/Telegram notifications
- CRM migration support

---

## 📌 Final Note

This workflow is designed to behave like a **disciplined human**, not a spam bot. Clean logic, respectful timing, and full visibility.

If you’re building outreach or customer success automation with n8n — this structure is a solid foundation.

---

**Built with ❤️ using n8n**

