<!-- Banner -->

<p align="center">
  <h1 align="center">📁 Incremental Google Drive Backup with n8n</h1>
  <p align="center">Teaching Google Drive to back up only <b>new</b> files — automatically.</p>
</p>

---

## 🚀 Overview

This project is a **personal n8n automation workflow** that performs **incremental backups** of a Google Drive folder.

Instead of copying everything again and again, the workflow:

* Detects **only new files**
* Backs them up once
* Keeps a clean, time‑stamped history
* Avoids duplicates and empty folders

It’s a small workflow, but a great real‑world example of using **logic, conditions, and loops** in automation.

---

## 🎯 Problem

All my study materials live in a Google Drive folder called:

```
n8n_courses
```

Manual backups caused several issues:

* Duplicate copies
* Forgotten backups
* No history of *when* a file first appeared

I wanted a solution that was:

* Automatic
* Incremental
* Easy to understand just by looking at the folder names

---

## 💡 Solution

An **incremental backup system** built with **n8n** that:

* Runs every **12 hours**
* Creates a new backup folder using the current date & time
* Copies **only files that have never been backed up before**
* Deletes empty backup folders if nothing new is found

Each backup folder represents the moment new files entered the system.

---

## 🧠 How the Workflow Thinks

For every file in `n8n_courses`, the workflow asks:

> “Does this file exist in *any* previous backup folder?”

* ✅ **No** → Copy it into the newest backup folder
* ⏭️ **Yes** → Skip it (already safe)

This decision is based on checking **empty search results** using truthy / falsy logic.

---

## 🧩 Workflow Steps

1. **Schedule Trigger** – Runs every 12 hours
2. **Date & Time Node** – Generates formatted timestamp
3. **Create Folder (Google Drive)** – Creates `BackUp/<timestamp>`
4. **List Files** – Reads all files from `n8n_courses`
5. **Loop Over Items** – Processes files one by one
6. **Search Files** – Looks for file name inside all backup folders
7. **IF Node** – Checks if search result is empty
8. **Download + Upload** – Copies only new files
9. **Cleanup Step** – Deletes backup folder if it remains empty

---

## 🗂️ Resulting Folder Structure

```
BackUp/
 ├─ 2025-12-15_11-30/
 │   └─ test.doc
 ├─ 2025-12-15_23-30/
 │   └─ test2.doc
```

Each folder shows **when a file first appeared** — no duplicates, no noise.

---

## ✨ What I Learned

* Boolean logic turns copy‑paste into decision‑making
* Automation is about **reducing mental load**, not just saving time
* Edge cases (empty results, empty folders) matter
* Small personal workflows are perfect for learning n8n deeply

---

## 🛠️ Tools Used

* **n8n** – Workflow automation
* **Google Drive API** – File storage & search
* **Expressions & IF logic** – Decision making

---

## 📌 Why This Project Matters

This isn’t an enterprise backup system.

It’s a reminder that:

> Good automation doesn’t just repeat actions faster —
> it remembers decisions so you don’t have to.

Now when I add a new file to `n8n_courses`, I don’t think about backups anymore.

A workflow is paying attention.

---

## 📬 Author

Built by **Asenaky**

If you’re learning **n8n**, automation, or no‑code logic — feel free to explore, adapt, and improve this workflow.

---

⭐ If this helped you, consider starring the repo
