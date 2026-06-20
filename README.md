# Telegram AI Appointment Booking Agent (n8n & Google Sheets)

A smart, fully automated Medical Appointment Booking System built using **n8n (Advanced AI Agent Node)**, **Telegram Bot API**, and **Google Sheets** as a dynamic database. 

The AI agent naturally interacts with users in Bengali, manages schedules, checks for existing bookings, calculates available 30-minute slots for the next 7 days, and allows users to view, reschedule, or cancel their bookings seamlessly.

---

## 🚀 Features

* **Intelligent AI Slot Calculation:** Automatically calculates free slots between 8:00 AM - 11:00 PM (excluding Fridays and already booked times) for the next 7 days.
* **Dynamic Menu-Driven Flow:** Main menu triggers automatically upon greetings or process completion.
* **4 Core Operations:**
  1. **New Booking:** Collects patient data, validates slots, and registers the user.
  2. **My Upcoming Bookings:** Checks and displays active appointment times using the mobile number.
  3. **Reschedule Booking:** Allows users to pick a new time from available slots and updates the database.
  4. **Cancel Booking:** Updates the booking status to "Cancelled" securely.
* **Single-Step Database Write:** Efficient data entry process to reduce tool-calling conflicts for LLMs.

---

## 🛠️ Tech Stack & Tools

* **Automation Platform:** [n8n](https://n8n.io/) (Advanced AI Agent, Window Buffer Memory, Telegram Trigger)
* **LLM Model:** Google Gemini Chat Model
* **Database:** Google Sheets
* **Interface:** Telegram Bot

---

## 📊 Database Schema (Google Sheets)

Create a Google Sheet with the following exact headers in `Sheet1`:

| name | age | gender | mobile | time | status |
|------|-----|--------|--------|------|--------|
| Jarif| 19  | Male   | 1973859825 | 21 June, 10:00 AM | Active |

---

## ⚙️ Workflow Architecture

1. **Telegram Trigger Node:** Listens for incoming messages from the Telegram Bot.
2. **AI Agent Node:** Act as the brain using custom system instructions to parse user intent and handle steps.
3. **Google Sheets Tools:** 
   * `show patient list` (Read rows)
   * `add new patient` (Append row)
   * `Reschedule patient` (Update Row matching by mobile)
   * `cancel booking` (Update Status Row matching by mobile)

---

## 📝 How to Use

1. Clone this repository or copy the n8n workflow JSON.
2. Import the JSON into your n8n instance.
3. Configure your **Telegram Bot Token** and connect your **Google Sheets Credentials**.
4. Paste your AI System Prompt into the n8n AI Agent node.
5. Publish the workflow and start messaging your Telegram bot!

---
Developed by **Kazi Md. Jarif** 🚀
