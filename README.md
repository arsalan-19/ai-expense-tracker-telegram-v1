# 🤖 Voice-Based Expense Tracker (Telegram + AI)

**A simple system designed to make expense tracking effortless — so better money habits actually stick, without adding cost or complexity.**

---

## 🧭 Problem

I repeatedly failed at tracking my expenses — not because tools were lacking, but because the habit didn’t stick.

The pattern was consistent:

* Logging required effort
* I postponed it
* Then stopped entirely

> The real problem wasn’t features. It was friction.

---

## 💡 Insight

If logging an expense takes even a few extra steps, most people won’t do it consistently.

So instead of improving the interface, I focused on removing the need for one.

---

## 🎯 Solution

A voice-first system where users can simply say:

> “Spent 450 on dinner using credit card”

And it automatically:

* Converts speech → text
* Extracts structured data
* Logs it into Google Sheets
* Sends a confirmation

All in real time.

---

## 🏗 How It Works

```id="flow"
Voice → Telegram Bot → Speech-to-Text → AI Parsing → Google Sheets → Confirmation
```

---

## ⚙️ Product Decisions & Trade-offs

### Voice over UI

* Less precision, but significantly higher adoption
  → Chose usage over control

---

### Google Sheets as Backend

* Not scalable, but fast to build and transparent
  → Chose speed and accessibility for V1

---

### AI Parsing vs Rule-Based Logic

* Slight unpredictability, but handles real language better
  → Chose flexibility over rigidity

---

### Resume on Error

* May skip failed entries, but system never blocks
  → Chose reliability over strict correctness

---

## 🔑 Key Capabilities

* 🎤 **Frictionless input** — no typing or app switching
* ⚡ **Real-time logging** — captured at the moment of spend
* 👥 **Multi-user support** — tracks user identity
* ⚠️ **Fault-tolerant flow** — system continues even on errors
* 🔁 **Instant feedback loop** — confirmation reinforces habit

---

## 📊 Example

Input:

> “Spent 850 on groceries using UPI”

Output:

| Date   | User    | Amount | Category  | Description | Payment Mode |
| ------ | ------- | ------ | --------- | ----------- | ------------ |
| 25 Apr | Arsalan | 850    | Groceries | Groceries   | UPI          |

Telegram reply:

```id="msg"
✅ Expense Added

₹850 | Groceries  
UPI  
25 Apr, 7:45 PM
```
<img width="318" height="188" alt="image" src="https://github.com/user-attachments/assets/dd59b977-7834-46d2-a720-d92e96e2c6cf" />



---

## 📈 What Changed (Outcome)

* Reduced friction → increased consistency
* Logging shifted from “later” → “instant”
* Improved visibility into spending behaviour

---

## 🚀 Getting Started (10–15 mins)

### 1. Create Telegram Bot

Use @BotFather → `/newbot` → copy token

---

### 2. Create Google Sheet

```id="cols"
Date | User | Amount | Category | Description | Payment Mode
```

---

### 3. Build Make.com Scenario

1. Telegram → Watch Updates
2. Telegram → Download File
3. OpenAI → Transcription
4. OpenAI → Chat Completion
5. JSON → Parse
6. Google Sheets → Add Row
7. Telegram → Send Message

---

### 4. Add API Keys

* Telegram
* OpenAI
* Google

---

### 5. Turn ON & Test

> “Spent 500 on groceries using UPI”

---

## ⚠️ Error Handling

* Failures trigger a retry message
* Scenario continues running
* No blocking for future inputs

---

## 🧠 What I Learned

* Reducing friction is often more valuable than adding features
* AI is most useful when it simplifies user behaviour
* Reliability (handling failure) is core product design
* Small feedback loops improve habit formation

---

## 🔭 What’s Next

* Monthly summaries
* Budget alerts
* Card-wise tracking
* Simple analytics layer

---

## 🧰 Tech Stack

* Make.com
* Telegram Bot
* OpenAI
* Google Sheets

---

## 🧪 Why This Matters

This project focuses on a simple question:

> How do you design a system people actually continue using?

Instead of adding features, I focused on removing effort — and that changed how the product behaves.

---

## 👤 Author

Built to improve my own financial discipline and explore how AI can simplify everyday workflows.

---
