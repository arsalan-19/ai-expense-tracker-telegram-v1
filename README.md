# 🤖 Voice-Based Expense Tracker (Built on Telegram + AI)

## The Problem I Was Trying to Solve

I’ve tried tracking my expenses multiple times. Every time, I stopped.

Not because the apps were bad — but because the habit was hard.

The pattern was always the same:

* I’d spend money
* Tell myself I’ll log it later
* Forget
* Stop tracking completely within a week

So the problem wasn’t “lack of features”.
It was this:

> **Logging an expense always felt like extra work.**

---

## The Core Insight

If logging takes even 10–15 seconds of effort, people will skip it.

So instead of building a better interface, I asked:

> “What if logging an expense required *almost zero effort*?”

That led to a simple idea:
👉 Let users just **speak**, and the system does the rest.

---

## The Solution

I built a system where I can say:

> “Spent 450 on dinner using credit card”

And it automatically:

* Converts voice → text
* Extracts structured data (amount, category, etc.)
* Logs it into Google Sheets
* Sends a confirmation back on Telegram

All in a few seconds.

---

## How It Works (Simplified)

```id="flow1"
Voice → Telegram Bot → Speech-to-Text → AI Parsing → Google Sheets → Confirmation Message
```

No UI. No typing. No switching apps.

---

## What I Focused On While Building

### 1. Reduce Friction as Much as Possible

This was the main goal.

* No app to open
* No forms to fill
* No manual categorisation

Just speak and move on.

---

### 2. Real-Time Feedback

Every entry sends a confirmation like:

```id="msg1"
✅ Expense Added

₹850 | Groceries  
UPI  
25 Apr, 7:45 PM
```

This seems small, but it:

* Builds trust
* Reinforces the habit
* Confirms nothing was lost

---

### 3. Make It Multi-User

I added user tracking so:

* Different people can use the same bot
* Each entry is tagged with who added it

This opens up use cases like:

* Family expense tracking
* Shared budgets

---

### 4. Make It Hard to Break

Early versions had a big issue:
👉 If one step failed, the entire system stopped.

So I added:

* Error handling with fallback messages
* “Resume” logic so the system never stops
* Ability to process multiple inputs without blocking

Now even if something fails:

* User gets a message to retry
* System continues working

---

## Example

Input:

> “Spent 1200 on travel using UPI”

Stored as:

| Date   | User    | Amount | Category | Description | Payment Mode |
| ------ | ------- | ------ | -------- | ----------- | ------------ |
| 25 Apr | Arsalan | 1200   | Travel   | Travel      | UPI          |

---

## Key Decisions (and Trade-offs)

### Voice over UI

* Less control, more ambiguity
* But dramatically higher usage probability

👉 I chose usage over precision.

---

### Google Sheets as Backend

* Not scalable long-term
* But extremely fast to build and iterate

👉 I chose speed over scale (for V1).

---

### AI Parsing vs Rule-Based

* Slightly unpredictable
* But handles real-world language much better

👉 I chose flexibility over strict rules.

---

### Resume on Error

* Might skip some failed entries
* But system never blocks

👉 I chose reliability over strict correctness.

---

## What I Learned

* The biggest problem in many products is not capability — it’s friction
* AI is most useful when it removes effort, not when it adds features
* Error handling is not edge-case work — it *is* core product design
* Small feedback loops (like confirmations) matter a lot for habit formation

---

## What’s Missing / Next Steps

If I continue building this:

* Monthly summaries (“You spent ₹X on food”)
* Budget alerts
* Card-wise tracking (important for real usage)
* Simple dashboard on top of the data

---

## Tech Stack (Kept Simple)

* Make.com (automation)
* Telegram Bot
* OpenAI (speech + parsing)
* Google Sheets

---

## Why This Project Matters

This is not just an automation project.

It’s an attempt to solve a behavioural problem:

> “How do you make expense tracking something people actually stick to?”

Instead of adding features, I focused on removing effort.

That shift changed how the product works entirely.

---

## About Me

Built this as a personal system to improve financial discipline and to explore how AI can simplify everyday workflows.

---
