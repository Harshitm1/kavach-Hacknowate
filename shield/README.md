# Kavach Privacy Extension

A comprehensive Chrome extension for enhancing your online privacy and security with ad blocking, HTTPS upgrading, anti-fingerprinting techniques, VPN integration, and AI-powered security insights.

## Features

### Core Privacy Protections
- **Ad and Tracker Blocking**: Automatically blocks known ad and tracking scripts from loading.
- **HTTPS Upgrading**: Redirects HTTP requests to HTTPS where supported.
- **Anti-Fingerprinting Techniques**: Prevents websites from uniquely identifying your browser through various techniques.
- **JavaScript Control**: Disable JavaScript on a per-site basis for enhanced security.

### Security Features
- **AI-Powered Safety Analysis**: Uses agent.ai to provide personalized security advice and threat analysis.
- **Safety Score**: Analyzes websites and provides a safety score based on multiple security factors.
- **Security Indicators**: Notifies you about potential security risks on websites.
- **Mixed Content Detection**: Identifies insecure content on secure pages.
- **VPN Integration**: Seamless integration with Shield VPN for enhanced privacy.
- **Proxy Configuration**: Optional proxy and Tor connectivity for anonymous browsing.

### User Interface
- **Privacy Dashboard**: Comprehensive statistics about blocked trackers, ads, and more.
- **Site-Specific Settings**: Configure privacy protections on a per-site basis.
- **Customizable Controls**: Toggle specific protections on or off as needed.
- **Security Chatbot**: AI assistant that answers security questions and provides advice.

## Installation

### From Chrome Web Store (Recommended - When Available)
1. Visit the Chrome Web Store
2. Search for "Kavach Privacy Extension"
3. Click "Add to Chrome"

### Manual Installation (Developer Mode)
1. Download or clone this repository
2. Open Chrome and navigate to `chrome://extensions/`
3. Enable "Developer mode" in the top-right corner
4. Click "Load unpacked" and select the Kavach extension folder
5. The extension should now be installed and active

## Usage

### Basic Usage
- Click the Kavach icon in the browser toolbar to see the current site's safety score and toggle protections.
- Use the dashboard for detailed statistics and configuration options.
- Configure site-specific settings for websites where you need custom protection levels.

### Safety Score and Detailed Breakdown
- The safety score (0-100) indicates the overall security level of a website
- Click on the safety score circle to view a detailed breakdown showing:
  - HTTPS security
  - Domain reputation
  - TLD safety level
  - Tracker prevalence
  - Phishing indicators

### AI Security Assistant
Kavach includes an AI-powered security assistant using agent.ai:

1. Click the chat icon (💬) in the bottom right of the popup
2. Ask any security-related question
3. Get personalized advice about:
   - Current website's security
   - Privacy best practices
   - Security recommendations
   - Explanation of safety scores
   - VPN/proxy usage guidance

### VPN Integration
For enhanced privacy, Kavach integrates with Shield VPN:

1. Click "Setup Shield VPN" in the popup
2. Follow the installation instructions
3. Use the "Check VPN" button to verify your connection
4. Enable "Secure Proxy Mode" for sites with low safety scores

### Dashboard
Access the full dashboard by clicking "Open Dashboard" in the popup menu. The dashboard provides:
- Protection statistics
- Global settings configuration
- Safety score details
- Top sites by safety ranking
- Security notifications history

### Site Settings
Configure site-specific settings by:
1. Clicking the Kavach icon in the toolbar
2. Selecting "Site Settings"
3. Adjust the toggles for this specific site

## Project Structure

```
kavach/
├── css/                   # Stylesheets
│   ├── popup.css          # Styles for the popup UI
│   ├── dashboard.css      # Styles for the dashboard
│   └── site-settings.css  # Styles for site-specific settings
├── icons/                 # Extension icons and UI icons
├── js/                    # JavaScript files
│   ├── background.js      # Service worker for background tasks
│   ├── content.js         # Content script injected in web pages
│   ├── popup.js           # Script for the popup UI
│   ├── chatbot-service.js # Script for agent.ai integration
│   ├── dashboard.js       # Script for the dashboard
│   └── site-settings.js   # Script for site-specific settings
├── lib/                   # Libraries
│   └── anti-fingerprint.js # Anti-fingerprinting protections
├── pages/                 # HTML pages
│   ├── popup.html         # Popup UI
│   ├── dashboard.html     # Dashboard page
│   └── site-settings.html # Site-specific settings page
└── manifest.json          # Extension manifest
```

## Technical Details

### Security Scoring
The Safety Score is calculated based on multiple factors:
- HTTPS usage (secure connection)
- Presence of tracking scripts
- Phishing indicators
- Domain reputation
- TLD security level
- Mixed content detection
- Domain age and complexity

### AI Integration with agent.ai
Kavach integrates with agent.ai to provide intelligent security analysis:

- **API Integration**: Uses the agent.ai API for generating security advice
- **Prompt Engineering**: Crafts detailed context-aware prompts with security information
- **Response Processing**: Processes and presents AI responses in a user-friendly format
- **Security Notifications**: Generates personalized security notifications for websites
- **Interactive Chatbot**: Provides a conversational interface for security questions

Key integration points:
- `js/chatbot-service.js`: Main service handling API communication
- `js/popup.js`: Integration with the UI for user interaction
- `js/background.js`: Background security analysis and notifications
- `js/content.js`: On-page security assessments and notifications

### Anti-Fingerprinting Methods
The extension employs multiple techniques to prevent browser fingerprinting:
- Canvas fingerprinting protection
- WebGL fingerprinting protection
- User agent normalization
- Audio fingerprinting protection
- Font fingerprinting protection
- Screen resolution spoofing

### Privacy Considerations
- All data is stored locally on your device
- Only security analysis queries are sent to agent.ai (no personal data)
- Export functionality allows you to save/backup your data
- VPN connection data never leaves your device

## Development

### Prerequisites
- Chrome or Chromium-based browser
- Basic knowledge of HTML, CSS, JavaScript
- Understanding of Chrome extension architecture
- agent.ai API key (for AI functionality)

### Setting Up agent.ai API
To use the AI features during development:

1. Obtain an API key from agent.ai
2. Replace the existing key in `js/chatbot-service.js`:
   ```javascript
   config: {
     apiKey: 'YOUR_API_KEY_HERE',
     apiUrl: 'https://api-lr.agent.ai/v1/action/invoke_llm',
     engine: 'gpt4o'
   }
   ```

### Building from Source
1. Clone the repository
2. Make your desired changes
3. Load the extension in developer mode for testing
4. Package the extension when ready for distribution

## License
[MIT License](LICENSE)

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## Credits
- Icons: Based on [Feather Icons](https://feathericons.com/)
- UI Framework: Custom CSS based on modern design principles
- AI Integration: Powered by agent.ai API 