# Surface

A voice chat application that lets you have spoken conversations with AI through OpenRouter.

## Features

- **Voice input/output**: Speak to the AI and hear responses read aloud
- **OpenRouter OAuth**: Log in with your OpenRouter account (PKCE flow)
- **Streaming responses**: Text appears as it's generated, speech starts immediately
- **Web search**: Say "please search for..." to use the online model variant
- **Interruption**: Start speaking to interrupt the AI mid-response
- **Voice selection**: Choose from available system voices
- **Keyboard shortcut**: Press Space to start/stop listening

## Tech Stack

- Single HTML file, no build step
- Web Speech API for speech recognition (STT) and synthesis (TTS)
- OpenRouter API with Gemini 3 Flash Preview model
- GitHub Pages compatible

## Limitations

- **Chrome recommended**: Speech recognition uses Google's cloud service, which Brave blocks for privacy
- **Mobile**: Works on Android Chrome; iOS Safari doesn't support Web Speech API for recognition
- **Not private**: Speech recognition audio is sent to Google's servers

## Usage

1. Open https://martinpllu.github.io/surface/voice-chat.html
2. Click "Connect with OpenRouter" and log in
3. Click the mic button or press Space to start talking
4. Click again or press Space to send your message
5. The AI will respond in text and speech

## Local Development

```bash
python3 -m http.server 3000
# Open http://localhost:3000/voice-chat.html
```

## Files

- `voice-chat.html` - Main application
- `web-speech-demo.html` - Standalone Web Speech API demo for testing
