# 🤖 Voice-Based Expense Tracker (Telegram + AI)

**Voice-first expense tracker designed to build better money habits with minimal effort and near-zero cost.**

---

## Why I Built This

I’ve tried tracking my expenses multiple times — and failed every time.

Not because the apps were bad, but because the habit didn’t stick.

The pattern was simple:

* I’d spend money
* Tell myself I’ll log it later
* Forget
* Stop tracking within a few days

So the real problem wasn’t features. It was friction.

> Logging an expense always felt like extra work.

---

## The Idea

What if logging an expense took almost no effort?

Instead of opening an app and typing, I should just be able to say:

> “Spent 450 on dinner using credit card”

And it should get logged automatically.

---

## What This Does

This system lets you:

* 🎤 Send a voice message on Telegram
* 🧠 Convert it into structured data using AI
* 📊 Store it in Google Sheets
* ✅ Get instant confirmation

No typing. No switching apps. Just speak and move on.

---

## How It Works

```id="flow1"
Voice → Telegram Bot → Speech-to-Text → AI Parsing → Google Sheets → Confirmation Message
```

---

## What I Focused On

### 1. Remove Friction

No app to open. No forms to fill. No manual categorisation.

---

### 2. Real-Time Feedback

Every entry sends a confirmation message — builds trust and reinforces the habit.

---

### 3. Multi-User Support

Each entry is tagged with the user, so multiple people can use the same bot.

---

### 4. Reliability

If something fails:

* User gets a retry message
* System continues running
* Future inputs are not blocked

---

## Example

Input:

> “Spent 850 on groceries using UPI”

Stored in Google Sheets:

| Date   | User    | Amount | Category  | Description | Payment Mode |
| ------ | ------- | ------ | --------- | ----------- | ------------ |
| 25 Apr | Arsalan | 850    | Groceries | Groceries   | UPI          |

Telegram reply:

```id="msg1"
✅ Expense Added

₹850 | Groceries  
UPI  
25 Apr, 7:45 PM
```

---

## Key Decisions (and Trade-offs)

* **Voice over UI**
  Less control, but much higher adoption

* **Google Sheets as backend**
  Not scalable, but fast and simple for V1

* **AI parsing instead of rules**
  Flexible, but slightly imperfect

* **Resume on error**
  System continues instead of breaking

---

## What I Learned

* Friction kills habits more than lack of features
* AI is useful when it removes effort
* Error handling is critical, not optional
* Small feedback loops (like confirmations) matter a lot

---

## 🚀 Getting Started (Setup in ~10–15 minutes)

### 1. Create Telegram Bot

* Open Telegram → search **@BotFather**
* Run `/newbot`
* Copy your **Bot Token**

---

### 2. Create Google Sheet

Create a sheet with columns:

```id="cols"
Date | User | Amount | Category | Description | Payment Mode
```

---

### 3. Create Make.com Scenario

Add these modules in order:

1. Telegram Bot → Watch Updates (Webhook)
2. Telegram Bot → Download a File
3. OpenAI → Transcription (Whisper)
4. OpenAI → Chat Completion
5. JSON → Parse JSON
6. Google Sheets → Add Row
7. Telegram Bot → Send Confirmation

---

### 4. Add API Keys

* Telegram Bot Token
* OpenAI API Key
* Google account (for Sheets)

---

### 5. Turn Scenario ON

Send a voice message like:

> “Spent 500 on groceries using UPI”

---

### 6. Done

* Entry is logged
* Confirmation is sent
* System runs automatically

---

## ⚠️ Error Handling

If something goes wrong:

* You receive a message:

  ```
  ❌ Error processing your expense
  Please try again
  ```
* System continues running
* No future messages are blocked

---

## 💡 Tips for Best Results

* Speak clearly
* Mention amount + category
* Example:

  > “Spent 1200 on travel using credit card”

---

## 📉 Current Limitations

* Depends on OpenAI API
* No dashboard yet
* Category detection may not always be perfect

---

## 🚀 What I’d Build Next

* Monthly summaries
* Budget alerts
* Card-wise tracking
* Simple analytics dashboard

---

## 🧰 Tech Stack

* Make.com (automation)
* Telegram Bot
* OpenAI (speech + parsing)
* Google Sheets

---

## Why This Project Matters

This isn’t just an automation.

It’s an attempt to solve a behavioural problem:

> “How do you make expense tracking something people actually stick to?”

Instead of adding features, I focused on removing effort.

---

## Author

Built as a personal system to improve financial discipline using simple AI and automation.

---
