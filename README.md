# Phishing-Detection-Email-Analysis-Tool


# 🛡️ PhishGuard — AI Email Phishing Detector

An AI-powered phishing detection and email threat analysis tool built with React and Claude AI. Paste any suspicious email and get an instant, detailed security analysis.

![PhishGuard Screenshot](https://via.placeholder.com/900x500/0a0e1a/6382ff?text=PhishGuard+AI+Email+Analyzer)

## ✨ Features

- **AI-Powered Analysis** — Uses Claude claude-sonnet-4-20250514 to deeply analyze email content
- **Risk Scoring** — 0-100 risk score with SAFE / SUSPICIOUS / PHISHING / MALICIOUS verdicts
- **Threat Indicators** — Detailed breakdown of every phishing indicator found, categorized by type and severity
- **Sender Analysis** — Detects email spoofing, display name deception, and domain impersonation
- **URL Analysis** — Identifies suspicious and malicious links within the email body
- **Attack Tactics** — Identifies social engineering techniques used (urgency, fear, authority, etc.)
- **Actionable Recommendations** — Specific steps the recipient should take
- **Technical Details** — Header anomalies, encoding tricks, urgency level assessment
- **Dual Input Modes** — Structured fields or raw EML paste with auto-parsing
- **Export Reports** — Download full analysis as JSON for documentation
- **Example Email** — Built-in phishing example to test the tool instantly

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- An [Anthropic API key](https://console.anthropic.com/api-keys)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/phishing-detector.git
cd phishing-detector

# Install dependencies
npm install

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Usage

1. Click **Set API Key** in the top right and enter your Anthropic API key
2. Paste the email content using either **Structured Input** (separate fields) or **Raw / EML Paste**
3. Click **Analyze Email** and wait a few seconds
4. Review the detailed threat analysis report

> **Note:** Your API key is stored only in your browser's `localStorage` and is sent directly to Anthropic's API — never to any third-party server.

## 🏗️ Project Structure

```
phishing-detector/
├── src/
│   ├── components/
│   │   ├── Header.jsx          # Top navigation with API key button
│   │   ├── Header.css
│   │   ├── EmailInput.jsx      # Email input form (structured + raw modes)
│   │   ├── EmailInput.css
│   │   ├── AnalysisResults.jsx # Full results display with all sections
│   │   ├── AnalysisResults.css
│   │   ├── ApiKeyModal.jsx     # API key entry modal
│   │   └── ApiKeyModal.css
│   ├── utils/
│   │   ├── anthropic.js        # Anthropic API wrapper
│   │   └── emailParser.js      # Raw email parser + quick scan utils
│   ├── App.jsx                 # Root component + state management
│   ├── App.css
│   ├── index.css               # Global styles + CSS variables
│   └── main.jsx                # React entry point
├── index.html
├── vite.config.js
└── package.json
```

## 🔍 How It Works

1. The user pastes email content (subject, sender, body, and optionally raw headers)
2. A structured prompt is sent to Claude claude-sonnet-4-20250514 via the Anthropic API
3. Claude analyzes the email for 8+ threat categories and returns a structured JSON report
4. The UI renders the results with interactive expandable indicators, visual risk scoring, and actionable recommendations

### Threat Categories Detected

| Category | Description |
|---|---|
| `SOCIAL_ENGINEERING` | Manipulation tactics exploiting human psychology |
| `SPOOFING` | Sender identity forgery or display name tricks |
| `MALICIOUS_URL` | Suspicious or dangerous links |
| `URGENCY` | Artificial time pressure to bypass critical thinking |
| `IMPERSONATION` | Pretending to be a trusted brand or person |
| `CREDENTIAL_HARVESTING` | Attempts to steal login credentials |
| `MALWARE` | Links or attachments delivering malicious software |
| `DATA_EXFILTRATION` | Requests for sensitive personal or financial data |

## 🛠️ Built With

- [React 18](https://react.dev/) — UI framework
- [Vite](https://vitejs.dev/) — Build tool
- [Lucide React](https://lucide.dev/) — Icons
- [Anthropic Claude API](https://docs.anthropic.com/) — AI analysis engine

## 🔒 Privacy & Security

- **No backend** — This is a pure frontend app. All API calls go directly from your browser to Anthropic.
- **API key stored locally** — Your key lives in `localStorage` and is never transmitted to any server other than `api.anthropic.com`.
- **No email storage** — Emails you analyze are never stored, logged, or retained.

## 📝 License

MIT License — see [LICENSE](LICENSE) for details.

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## ⚠️ Disclaimer

This tool is for educational and research purposes. While Claude AI is powerful, no automated tool can guarantee 100% phishing detection accuracy. Always exercise caution with suspicious emails regardless of analysis results.
