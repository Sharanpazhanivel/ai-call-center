# 🎙️ AI-Powered Multi-Agent Call Center

An intelligent voice-enabled call center system with specialized AI agents that handle sales, technical support, billing, and appointment scheduling.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## ✨ Features

### 🤖 Four Specialized AI Agents

- **Sarah (Sales)** - Professional female voice, enthusiastic product expert
- **Lara (Tech Support)** - Calm female voice, patient troubleshooter
- **Beth (Billing)** - Energetic female voice, precise billing specialist
- **Alex (Appointments)** - Friendly male voice, efficient scheduler

### 🎯 Core Capabilities

- **AI-Powered Routing** - Automatically routes calls to the right agent
- **Smart Transfers** - Seamless agent-to-agent handoffs
- **Voice Interaction** - Full speech-to-text and text-to-speech
- **Realistic Voices** - Ultra-realistic TTS using Cartesia AI
- **Call Analytics** - Track call duration, transfers, and agent performance

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Microphone for voice input
- Internet connection
- API keys for Cerebras AI and Cartesia TTS

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ai-call-center.git
   cd ai-call-center
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up API keys**
   
   Create a `.env` file in the project root:
   ```
   CEREBRAS_API_KEY=your_cerebras_key_here
   CARTESIA_API_KEY=your_cartesia_key_here
   ```

   Or edit the API keys directly in Cell 4 of the notebook.

4. **Run the notebook**
   ```bash
   jupyter notebook "AI Voice Agent.ipynb"
   ```

5. **Start a conversation**
   - Run all cells up to Cell 35
   - Execute Cell 38 to start the voice conversation
   - Speak naturally into your microphone

## 📖 Usage

### Text-Based Testing

Run Cell 29 to test agent routing and transfers with text:

```python
# Test conversation scenarios
test_conversation(
    initial_message="I want to buy a laptop",
    follow_ups=["What's the most powerful one?"]
)
```

### Voice Conversation

Run Cell 38 to start a full voice conversation:

```python
voice_call_center.voice_conversation(max_turns=10)
```

Example queries:
- "I'm interested in buying your software"
- "My application keeps crashing"
- "I need a refund for my last payment"
- "Can I schedule a product demo?"

## 🏗️ Architecture

### Phase 1: Multi-Agent Foundation
- Base `CallCenterAgent` class
- 4 specialized agent implementations
- AI-powered intent classification
- Transfer protocol and routing

### Phase 2: Voice Integration
- `VoiceCallCenterAgent` with Cartesia TTS
- Speech recognition with Google Speech API
- Voice Activity Detection (VAD)
- Agent-specific voice profiles

## 🛠️ Configuration

### Adjusting Voice Sensitivity

Edit the VAD settings in Cell 31:

```python
self.recognizer.pause_threshold = 1.2  # Seconds of silence before stopping
self.recognizer.phrase_threshold = 0.4  # Minimum speech duration
```

### Changing Agent Voices

Modify voice profiles in Cell 31:

```python
VOICE_PROFILES = {
    "sales": {
        "voice_id": "694f9389-aac1-45b6-b726-9d9369183238",
        "name": "Professional Female",
        "rate": 1.0
    },
    # ... add custom voices
}
```

## 📊 API Keys

### Required APIs

1. **Cerebras AI** - For LLM chat completions
   - Sign up: https://cerebras.ai
   - Model: llama3.1-8b

2. **Cartesia TTS** - For realistic voice synthesis
   - Sign up: https://cartesia.ai
   - Model: sonic-english

### Optional APIs

- **OpenAI** - Alternative to Cerebras (GPT-3.5/4)
- **LiveKit** - For advanced voice infrastructure

## 🔒 Security

**⚠️ IMPORTANT**: Never commit API keys to version control!

- Use environment variables or `.env` file
- Add `.env` to `.gitignore`
- Replace placeholder keys before running
- Regenerate keys if accidentally exposed

## 📝 Project Structure

```
ai-call-center/
├── AI Voice Agent.ipynb    # Main notebook
├── context/
│   └── products.json        # Product catalog
├── requirements.txt         # Python dependencies
├── .env                     # API keys (not in repo)
├── .gitignore              # Git ignore rules
└── README.md               # This file
```

## 🤝 Contributing

Contributions are welcome! Areas for improvement:

- [ ] Call recording and transcripts
- [ ] Sentiment analysis
- [ ] CRM integration
- [ ] Multi-language support
- [ ] Analytics dashboard
- [ ] Calendar integration for appointments
- [ ] SMS/Email follow-up

## 📄 License

MIT License - feel free to use for personal or commercial projects.

## 🙏 Acknowledgments

- **Cerebras AI** - Fast and affordable LLM inference
- **Cartesia** - Ultra-realistic voice synthesis
- **Google Speech API** - Reliable speech recognition

## 📧 Contact

Questions or feedback? Open an issue or reach out!

---

**Made with ❤️ using AI and Python**
