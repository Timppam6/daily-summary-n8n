🕒 Daily Weather & Calendar Notifier
This n8n workflow automatically sends you a daily update via Telegram with:

The current weather in Phuket, Thailand
Your upcoming events from Google Calendar
The update is triggered every day at 9:00 AM.

🔧 Workflow Overview
This workflow consists of the following nodes:

1. Schedule Trigger
Triggers the workflow every day at 9:00 AM.

2. AI Agent
Uses Google Gemini to process and format the information. It is instructed to:

Fetch weather data for Phuket, Thailand
Retrieve calendar events for the day
Format the output minimally with only relevant information
3. Google Gemini Chat Model
Provides the language model used by the AI agent.

4. OpenWeatherMap Tool
Fetches real-time weather data for Phuket.

5. Google Calendar Tool
Retrieves all events scheduled for the current day from your Google Calendar.

6. Telegram: Send a Text Message
Sends the formatted daily update as a message to a specified chat.

📦 Credentials Used
Google Gemini (PaLM) API
OpenWeatherMap API
Google Calendar OAuth2
Telegram API
🔄 Workflow Connections
1
2
3
4
5
6
7
8
9
10
11
12
plaintext
Schedule Trigger
      ↓
     AI Agent
      ↓
Send a Text Message (Telegram)

AI Agent also connected to:
├── Google Gemini Chat Model (Language Model)
├── OpenWeatherMap Tool (Weather data)
└── Google Calendar Tool (Event data)

📝 Example Output
1
2
3
4
5
6
7
8
9
text
Weather in Phuket, Thailand:
Temperature: 27.68°C
Feels like: 31.59°C
Description: few clouds

Calendar Events:
Jog today from 21:45 to 22:45

🚀 Setup Instructions
Import Workflow: Copy the JSON into your n8n instance.
Set Up Credentials:
Connect your Google Gemini, OpenWeatherMap, Google Calendar, and Telegram accounts.
Configure Telegram Chat ID:
Replace CHAT_ID in the Telegram node with your actual chat ID.
Activate Workflow: Enable and activate the workflow in n8n.
📌 Notes
Ensure all credentials are properly configured and authorized.
The AI agent is designed to be minimal and efficient, focusing only on essential data.
You can customize the prompt in the AI node to change formatting or include more/less info.
