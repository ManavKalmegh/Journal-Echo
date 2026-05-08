# 🧘 Journal Echo

> An AI-powered journaling companion that listens, reflects, summarizes, and emotionally responds to your thoughts.

Journal Echo is an intelligent journaling application built using **Python**, **Streamlit**, and **Google Gemini AI**.  
It combines reflective journaling with conversational AI to create a safe emotional space where users can:

- Write journal entries freely
- Talk with an empathetic journaling mentor
- Generate emotional summaries of journal sessions
- Reflect on emotional patterns over time
- Receive heartfelt “letters from past self”
- Use voice-to-text journaling
- Chat with an emotionally aware AI companion based on previous journal history

---

# ✨ Features

## 📔 1. Free Writing Mode
Users can write journal entries independently without AI interruption.

### Features
- Minimal distraction writing experience
- Session-based journaling
- Automatic JSON storage
- Timestamped entries

---

## 🤝 2. Journaling Mentor Mode
An emotionally intelligent AI mentor interacts with the user in real time.

The mentor:
- Responds warmly and briefly
- Encourages deeper reflection
- Avoids lecturing or over-analyzing
- Maintains a safe emotional tone

Example:
```text
User: I feel anxious lately.

Mentor: That sounds heavy to carry around every day.
What do you think has been sitting with you the most?
```

---

## 🧠 3. AI Session Summarization

At the end of every session, Gemini AI generates a concise emotional summary.

The summary includes:
- Emotional tone
- Personality observations
- Mood changes
- Important reflections

Example:
```text
You began the session feeling overwhelmed and emotionally tired.
As the conversation progressed, you became more open and reflective.
There seems to be a strong need for reassurance and emotional grounding.
```

---

## 💬 4. Echo Chat

After journaling, users can start an emotionally contextual AI conversation.

The chatbot:
- Reads previous summaries
- Understands emotional context
- Responds like a caring friend
- References past emotional patterns gently

This creates continuity between journaling sessions.

---

## 💌 5. Letter From Past Self

One of the most unique features of Journal Echo.

The system:
- Finds emotionally similar journal summaries
- Detects recurring emotional themes
- Generates a heartfelt letter from the “past self” to the current self

Example:
```text
You’ve survived difficult nights before.
Remember how scared you felt in April, and yet you still kept going.
You are softer now, but also stronger.
```

---

## 🪞 6. Self Reflection Engine

Analyzes long-term emotional patterns across journal summaries.

The AI reflects on:
- Recurring emotional states
- Growth patterns
- Emotional habits
- Internal behavioral shifts

Unlike summaries, this module focuses on emotional self-awareness.

---

## 🎤 7. Voice-to-Text Journaling

Users can journal using speech input.

Implemented using:
- `speech_recognition`
- `vosk`
- microphone audio streams

Useful for:
- accessibility
- quick emotional capture
- natural journaling flow

---

# 🏗️ Project Architecture

```text
                    ┌────────────────────┐
                    │     User Input      │
                    └─────────┬──────────┘
                              │
             ┌────────────────┴────────────────┐
             │                                 │
     ┌───────▼────────┐              ┌────────▼────────┐
     │ Text Journaling │              │ Voice Journaling │
     └───────┬────────┘              └────────┬────────┘
             │                                 │
             └────────────────┬────────────────┘
                              │
                     ┌────────▼────────┐
                     │ Streamlit UI App │
                     └────────┬────────┘
                              │
         ┌────────────────────┼────────────────────┐
         │                    │                    │
 ┌───────▼────────┐  ┌────────▼────────┐  ┌────────▼────────┐
 │ Mentor Chat AI │  │ Session Storage │  │ Summary Engine  │
 └───────┬────────┘  └────────┬────────┘  └────────┬────────┘
         │                    │                    │
         │                    │             ┌──────▼──────┐
         │                    │             │ JSON Files  │
         │                    │             └──────┬──────┘
         │                    │                    │
         │          ┌─────────▼──────────┐         │
         │          │ Emotional Analysis │◄────────┘
         │          └─────────┬──────────┘
         │                    │
 ┌───────▼────────┐  ┌────────▼────────┐
 │ Echo Chat Mode │  │ Self Reflection │
 └────────────────┘  └─────────────────┘
```

---

# 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core backend |
| Streamlit | Frontend UI |
| Gemini AI | Conversational + summarization AI |
| JSON | Journal storage |
| SpeechRecognition | Voice input |
| Vosk | Offline speech recognition |
| dotenv | Environment management |

---

# 📂 Project Structure

```text
Journal-Echo/
│
├── journalling.py              # Main Streamlit application
├── summary.py                  # Session summarization engine
├── Summarize.py                # Alternate summarizer
├── ChatBot.py                  # Echo AI chat system
├── Self_reflection.py          # Emotional reflection engine
├── Letter_from_past.py         # Letter generation system
├── VoiceToText.py              # Voice recognition module
│
├── journal_entries.json        # Raw journal sessions
├── journal_summary.json        # Generated summaries
│
├── .env                        # Gemini API key
│
└── README.md
```

---

# ⚙️ How It Works

## Step 1 — User Journals
The user either:
- writes freely
- chats with the journaling mentor
- uses voice journaling

---

## Step 2 — Session Storage
All entries are saved in:
```json
journal_entries.json
```

Each session contains:
- timestamps
- user input
- mentor responses

---

## Step 3 — AI Summary Generation
When the session ends:
- all entries are combined
- Gemini AI analyzes emotional tone
- a short emotional summary is generated

Stored in:
```json
journal_summary.json
```

---

## Step 4 — Reflection Systems
The summaries are then used by:
- Echo Chat
- Self Reflection
- Letter from Past Self

This creates long-term emotional continuity.

---

# 🚀 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/journal-echo.git
cd journal-echo
```

---

## 2. Create Virtual Environment

### Windows
```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / Mac
```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If `requirements.txt` does not exist:

```bash
pip install streamlit google-generativeai python-dotenv speechrecognition vosk sounddevice
```

---

## 4. Add Gemini API Key

Create a `.env` file:

```env
GEMINI_API_KEY=your_api_key_here
```

Get your API key from:
https://aistudio.google.com/app/apikey

---

# ▶️ Running the Project

## Run Main Application

```bash
streamlit run journalling.py
```

---

## Run Individual Modules

### Summary Generator
```bash
python summary.py
```

### Echo Chat
```bash
python ChatBot.py
```

### Self Reflection
```bash
python Self_reflection.py
```

### Letter From Past Self
```bash
python Letter_from_past.py
```

### Voice Recognition
```bash
python VoiceToText.py
```

---

# 🧪 Example Workflow

```text
1. User writes journal entries
2. AI mentor responds empathetically
3. Session ends
4. Gemini generates emotional summary
5. Summary stored in JSON
6. Reflection systems analyze history
7. Echo Chat responds using emotional memory
```

---

# 📸 UI Overview

## Main Journaling Interface
- Clean Streamlit interface
- Chat bubbles for mentor mode
- Sidebar session history
- Emotional summaries

## Echo Chat
- Context-aware emotional conversations
- Personalized AI interaction

## Summary Dashboard
- Displays latest emotional summaries
- Past emotional history
- Reflective insights

---

# 🔒 Privacy Note

Journal Echo stores journal entries locally in JSON files.

No external database is used.

However:
- Gemini API requests are sent to Google AI services
- Avoid storing highly sensitive personal data in production environments

---

# 🌱 Future Improvements

Potential future features:
- User authentication
- Encrypted journal storage
- Mood graphs and analytics
- Vector memory search
- Fine-tuned emotional models
- Mobile application
- Cloud sync
- Multi-language support
- Daily reminders
- Emotion trend visualization

---

# 🧠 AI Design Philosophy

Journal Echo was designed around:
- emotional safety
- reflective thinking
- non-judgmental conversation
- calm AI interaction

The AI intentionally:
- avoids harsh advice
- avoids toxic positivity
- avoids over-analysis
- prioritizes emotional validation

---

# 📜 Sample Data Format

## Journal Entry

```json
{
  "timestamp": "2025-04-21T00:08:28.630144",
  "user_input": "I feel overwhelmed today",
  "mentor_response": "That sounds difficult to carry alone. What feels the heaviest right now?"
}
```

---

## Journal Summary

```json
{
  "timestamp": "2025-04-21T00:24:19.489213",
  "summary": "You seemed emotionally exhausted at the beginning but gradually became more reflective and open during the session."
}
```

---

# 🙌 Acknowledgements

- Google Gemini AI
- Streamlit
- Vosk Speech Recognition
- Python Open Source Community

---

# 👨‍💻 Author

Built with care as an emotionally intelligent journaling assistant project.

If you like the project, consider giving it a ⭐ on GitHub.
