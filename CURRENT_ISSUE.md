# Current Issue: Android Speech Recognition Duplication

## Problem
On Android Chrome, speech recognition shows heavily duplicated text while speaking (e.g., "what's the best" becomes "what'swhat's thewhat's the bestwhat's the best thing..."). When the stop button is pressed, the text disappears.

## What's Been Tried
1. Changed interim result handling to not accumulate (use latest only)
2. Simplified result processing to just concatenate all results
3. Disabled `continuous` mode on mobile devices (current approach in v3)

## Relevant Code
The speech recognition is set up in `setupSpeechRecognition()` around line 1082 in `voice-chat.html`:

```javascript
recognition.continuous = !isMobile; // Disabled on mobile
recognition.interimResults = true;
```

Result handling is in `recognition.onresult` around line 1117.

## To Test
- Live: https://martinpllu.github.io/surface/voice-chat.html
- Check version number (v3) next to Voice button to confirm deployment
- Test on Android Chrome - speak a sentence and see if duplication occurs

## Possible Next Steps
- Try disabling `interimResults` on mobile (will lose live preview but may fix duplication)
- Debug actual result structure on Android (resultIndex, results length, isFinal values)
- Consider different approach for mobile: single utterance mode instead of continuous
