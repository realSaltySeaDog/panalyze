# PicklePro Analyzer

AI-powered video analysis tool for pickleball players. Analyze your game footage from YouTube and get personalized coaching tips to improve your play.

## Features

- **YouTube Integration**: Load any YouTube pickleball video directly
- **Frame Capture**: Capture specific moments from the video for analysis
- **AI-Powered Analysis**: Uses Claude's vision capabilities to analyze your technique
- **Personalized Tips**: Get advice tailored to your skill level
- **Focus Areas**: Choose specific aspects of your game to analyze
- **Export Results**: Save your analysis as a markdown file

## Quick Start

1. **Open the app**: Open `index.html` in your browser
   ```bash
   # Option 1: Direct file open
   open index.html

   # Option 2: Local server (recommended for best compatibility)
   npx serve .
   # or
   python3 -m http.server 8000
   ```

2. **Configure API Key**: Click the settings icon (gear) and enter your Anthropic API key
   - Get an API key from [console.anthropic.com](https://console.anthropic.com)
   - Your key is stored locally in your browser

3. **Load a Video**: Paste a YouTube URL of a pickleball match

4. **Capture Frames**: Use the "Capture Frame" button to capture key moments
   - Pause the video at moments you want analyzed
   - Capture 3-5 frames for best results
   - Press `C` as a keyboard shortcut

5. **Configure Analysis**:
   - Select which player you are (if doubles)
   - Choose your skill level
   - Optionally select focus areas

6. **Analyze**: Click "Analyze with AI" and wait for results

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Anthropic API key with access to Claude's vision capabilities
- Internet connection for YouTube and API access

## Technical Notes

- **Frame Capture**: Due to YouTube's security restrictions, frames are captured using YouTube's thumbnail API. For exact frame analysis, consider using a video recording tool.
- **API Usage**: Each analysis uses Claude's vision API. Multiple frames will increase API costs.
- **Privacy**: Your API key and video data stay in your browser. Nothing is sent to our servers.

## Project Structure

```
pick/
├── index.html      # Main HTML file
├── README.md       # This file
└── src/
    ├── styles.css  # All styling
    ├── app.js      # Main application logic
    └── analyzer.js # AI analysis module
```

## Customization

### Changing the AI Model

Edit `src/analyzer.js` and modify the `model` property:
```javascript
this.model = 'claude-sonnet-4-20250514'; // or another Claude model
```

### Adding Focus Areas

Edit `index.html` and add new checkboxes in the focus areas section:
```html
<label class="checkbox-label">
    <input type="checkbox" name="focus" value="new-area"> New Area
</label>
```

## Troubleshooting

**"API key not configured"**
- Click the settings icon and enter your Anthropic API key

**"Invalid YouTube URL"**
- Make sure you're using a full YouTube URL (not shortened or embedded)
- Supported formats: `youtube.com/watch?v=...`, `youtu.be/...`

**Analysis fails**
- Check your API key is valid and has credits
- Try capturing fewer frames
- Check browser console for detailed errors

**CORS errors**
- Use a local server instead of opening the file directly
- Try `npx serve .` or `python3 -m http.server`

## License

MIT License - Feel free to modify and use for your own projects.
