# 🕒 Daily Weather & Calendar Notifier

This n8n workflow automatically sends you a daily update via Telegram with:
- The current weather in your location
- Your upcoming events from Google Calendar

The update is triggered every day at **9:00 AM**.

## 🔧 Workflow Overview

This workflow consists of the following nodes:

### 1. **Schedule Trigger**
Triggers the workflow every day at 9:00 AM.

### 2. **AI Agent**
Uses Google Gemini to process and format the information. It is instructed to:
- Fetch weather data for your location
- Retrieve calendar events for the day
- Format the output minimally with only relevant information

### 3. **Google Gemini Chat Model**
Provides the language model used by the AI agent.

### 4. **OpenWeatherMap Tool**
Fetches real-time weather data.

### 5. **Google Calendar Tool**
Retrieves all events scheduled for the current day from your Google Calendar.

### 6. **Telegram: Send a Text Message**
Sends the formatted daily update as a message to a specified chat.

## 📦 Credentials Used

- **Google Gemini (PaLM) API**
- **OpenWeatherMap API**
- **Google Calendar OAuth2**
- **Telegram API**

## 🔄 Workflow Connections

```plaintext
Schedule Trigger
      ↓
     AI Agent
      ↓
Send a Text Message (Telegram)

AI Agent also connected to:
├── Google Gemini Chat Model (Language Model)
├── OpenWeatherMap Tool (Weather data)
└── Google Calendar Tool (Event data)
```

## 📝 Example Output

```text
Weather in [Location]:
Temperature: 27.68°C
Feels like: 31.59°C
Description: few clouds

Calendar Events:
Jog today from 21:45 to 22:45
```

## 🚀 Setup Instructions

1. **Import Workflow**: Copy the JSON into your n8n instance.
2. **Set Up Credentials**:
   - Connect your **Google Gemini**, **OpenWeatherMap**, **Google Calendar**, and **Telegram** accounts.
3. **Configure Location**:
   - Update the location in the OpenWeatherMap node.
4. **Configure Telegram Chat ID**:
   - Replace `CHAT_ID` in the Telegram node with your actual chat ID.
5. **Activate Workflow**: Enable and activate the workflow in n8n.

## 📌 Notes

- Ensure all credentials are properly configured and authorized.
- The AI agent is designed to be minimal and efficient, focusing only on essential data.
- You can customize the prompt in the AI node to change formatting or include more/less info.
