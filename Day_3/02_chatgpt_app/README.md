# ChatGPT-Style Application

This folder contains the main workshop application that participants will build during the 2-hour session.

## Files Structure

- **app.py** - The main application file (complete implementation)
- **requirements.txt** - Python dependencies
- **deployment_guide.md** - Hugging Face Spaces deployment instructions
- **chat_history/** - Directory storing persistent chat conversations (auto-created)
- **.streamlit/secrets.toml** - Local API key storage (create this file for local development)

## Quick Start

### Local Development
```bash
# Install dependencies
pip install -r requirements.txt

# Create secrets file for local development
mkdir -p .streamlit
echo 'OPENROUTER_API_KEY = "your-api-key-here"' > .streamlit/secrets.toml

# Run the application
streamlit run app.py
```

### Deployment
Follow the instructions in `deployment_guide.md` to deploy to Hugging Face Spaces.

## API Key Setup

### For Local Development
- Get your OpenRouter API key from [openrouter.ai](https://openrouter.ai)
- Create `.streamlit/secrets.toml` file with:
  ```toml
  OPENROUTER_API_KEY = "your-api-key-here"
  ```
- The app will automatically load the API key from secrets

### For Production Deployment
- Add your API key to Hugging Face Spaces secrets as `OPENROUTER_API_KEY`
- The app will automatically use it from the secrets

## Features Included

### Core Chat Features
✅ Modern chat interface with Streamlit components  
✅ OpenRouter API integration (GPT-OSS-120B model)  
✅ Streaming responses for real-time interaction  
✅ Error handling and user feedback  

### Chat Management
✅ **Multiple Conversations** - Create and manage multiple chat sessions  
✅ **Persistent Chat History** - All chats are saved to disk as JSON files  
✅ **Chat Navigation** - Switch between conversations via sidebar  
✅ **Auto-Save** - Conversations are automatically saved after each message  
✅ **Chat Deletion** - Delete unwanted conversations  

### User Experience
✅ **Dark Mode Toggle** - Switch between light and dark themes  
✅ **Chat Summarization** - Generate summaries of entire conversations  
✅ **Feedback System** - Thumbs up/down buttons for assistant responses  
✅ **Auto-Title Generation** - Chat titles automatically generated from first message  

### Technical Features
✅ Session state management for chat history  
✅ Persistent storage using JSON files  
✅ Production-ready deployment configuration  

## Chat History Storage

Chats are automatically saved to the `chat_history/` directory as JSON files. Each chat file contains:
- Chat ID (timestamp-based unique identifier)
- Title (auto-generated from first message or user-defined)
- Complete message history
- Creation and update timestamps

The app automatically loads the most recent chat when you start it.

## Usage Tips

1. **Create New Chat**: Click "➕ New Chat" in the sidebar
2. **Switch Chats**: Click on any chat in the "Chat History" section
3. **Delete Chat**: Click the 🗑️ button next to any chat
4. **Summarize**: Expand "📝 Summarize Conversation" to generate a summary
5. **Dark Mode**: Toggle dark mode in the Settings section
6. **Clear Current Chat**: Use "🗑️ Clear Current Chat" to reset the current conversation

## Model Information

The app uses **OpenAI GPT-OSS-120B** model via OpenRouter API. This model provides:
- High-quality conversational responses
- Fast streaming output
- Free tier availability

This application serves as the foundation for the breakout session challenges where participants will add translation, personality selection, and export features.