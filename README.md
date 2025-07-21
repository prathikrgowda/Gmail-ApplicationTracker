# 📬 Gmail Job Application Auto‑Labeler with OpenAI & Google Apps Script

An AI-powered Gmail automation tool that reads your job-related emails, classifies them using GPT-4o, labels them in Gmail, extracts metadata (like position, date, and company), and logs everything into Google Drive CSVs — all running every 30 minutes.

---

## ✨ Features

✅ Automatically classifies **incoming** emails as:  
- `Applied`  
- `Rejected`  
- `Interview`  
- `Assessment`  
- `Other`  

✅ Classifies **outgoing** emails as:  
- `Sent/Applied`  
- `Sent/FollowUp`  
- `Sent/Other`  

✅ Extracts:
- Course/Job Title  
- Application Date  
- Company name (from both email address and content using LLM)

✅ Adds Gmail Labels and preserves read/unread status  
✅ Logs each email’s metadata to `JobAppsLog.csv` in Google Drive  
✅ Adds a daily classification summary to `JobAppsSummary.csv`  
✅ Schedules itself to run every 30 minutes  
✅ Skips processing if there's nothing new to avoid wasted tokens

---

## 🛠️ Tech Stack

- **Google Apps Script** (runs in Gmail environment)
- **OpenAI GPT-4o-mini** (for classification & extraction)
- **Google Drive** (for storing CSV logs)
- **Gmail Labels** (for organizing inbox threads)

---

## 🚀 How to Use

### 1. Create the Script in Google Apps Script
- Go to [Google Apps Script](https://script.google.com)
- Create a **new project**
- Replace the default code with contents from `Code.gs` in this repo

### 2. Configure Gmail Labels
The script will auto-create these if they don’t already exist:

JobApps/Applied
JobApps/Rejected
JobApps/Interview
JobApps/Assessment
JobApps/Other
Sent/Applied
Sent/FollowUp
Sent/Other
JobApps/Processed
Sent/Processed


No manual setup needed — just run it once and these will appear.

### 3. Set Your OpenAI API Key
- Open the Apps Script Editor  
- Click the gear icon (⚙️) → **Project Settings**  
- Scroll to **Script Properties** → click "Add script property"  

Add the following:


You can get a key from: https://platform.openai.com/account/api-keys

### 4. Enable Gmail & Drive APIs
- In the Script Editor, click **Services (+)** on the left  
- Add:
  - Gmail API  
  - Google Drive API

### 5. Authorize & Run
- Run `processThreads()` once manually to trigger permission prompts
- Then run `createScheduler()` to schedule the script to run every 30 minutes

---

**Charan Reddy Kumar**  
🔗 [LinkedIn](https://www.linkedin.com/in/charan-reddy-kumar-2b0319114/)  
💻 [GitHub](https://github.com/CharanReddyKumar)
