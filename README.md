# J.A.R.V.I.S.

## Overview
J.A.R.V.I.S. is an **n8n workflow** that processes messages from Telegram, distinguishing between text and voice messages. The workflow transcribes voice messages using AssemblyAI, translates text messages, and provides AI-generated responses using Google Gemini and Anthropic AI models. It also integrates a J.A.R.V.I.S.-styled assistant.

## Features
- **Telegram Integration**: Receives and sends messages via Telegram.
- **Voice Message Processing**: Downloads voice messages, transcribes them using AssemblyAI, and converts text responses to speech.
- **Text Processing**: Detects text messages, processes them, and can translate text.
- **AI Assistance**: Uses Google Gemini and Anthropic AI to generate intelligent responses.
- **J.A.R.V.I.S. Mode**: Formats responses in the style of Tony Stark's AI assistant.
- **Wikipedia and Calculator Integration**: Searches for information and performs calculations when needed.

## Workflow Breakdown
1. **Receiving Messages**: A Telegram Trigger node detects incoming messages.
2. **Message Classification**: A Switch node categorizes input as either:
   - **Audio** (voice message)
   - **Text**
   - **Error**
3. **Voice Message Processing**:
   - The voice file is downloaded from Telegram.
   - Uploaded to AssemblyAI for transcription.
   - The transcribed text is processed and optionally translated.
4. **Text Processing**:
   - Text messages are assigned for further AI processing.
   - Google Gemini or Anthropic AI generates responses.
   - J.A.R.V.I.S. formatting can be applied.
5. **Response Generation & Delivery**:
   - The response is sent back to the user via Telegram.
   - If J.A.R.V.I.S. mode is enabled, the response mimics its style.
   - For voice responses, ElevenLabs is used to generate speech.

## API Keys & Credentials
The workflow requires the following credentials:
- **Telegram API** (for receiving and sending messages)
- **AssemblyAI API Key** (for transcription)
- **Google Gemini API Key** (for AI responses)
- **Anthropic API Key** (for AI responses)
- **ElevenLabs API Key** (for voice synthesis)

## Installation & Setup
1. Install **n8n** on your system:
   ```sh
   npm install -g n8n
   ```
2. Import the provided JSON workflow into n8n.
3. Configure your API credentials in n8n.
4. Start the n8n server:
   ```sh
   n8n start
   ```
5. Set up a Telegram bot and connect it to your n8n instance.

## Usage
- Send a text or voice message to the Telegram bot.
- Receive an AI-generated response in text or voice.
- Use the J.A.R.V.I.S. mode for stylized responses.
## Notes
- Ensure API keys are kept secure.
- The ElevenLabs integration is disabled by default and must be enabled for voice output.
- The workflow includes a wait node to allow time for transcriptions to process.
## Action points
- Keeping your attention
- Clear division of tasks
- Regular progress checks
