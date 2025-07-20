# WorkflowSync2

**WorkflowSync2** is a modern productivity dashboard that connects to your Gmail and Slack accounts, uses Gemini AI to categorize and summarize your messages, and helps you organize and prioritize your work efficiently.

## 🚀 Features
- **Gmail & Slack Integration:** Connect your email and workspace for unified task management.
- **AI-Powered Categorization:** Uses Google Gemini AI to classify messages as Urgent, FYI, or Ignored.
- **Smart Summaries & Action Items:** Extracts key points and action items from your messages.
- **Secure Authentication:** OAuth2-based login with robust session management.
- **Beautiful UI:** Responsive, modern dashboard built with React, TailwindCSS, and Framer Motion.
- **Privacy-First:** Your data is processed securely; secrets are never committed to the repository.

## 🛠️ Getting Started

### 1. Clone the Repository
```sh
git clone https://github.com/yourusername/WorkflowSync2.git
cd WorkflowSync2
```

### 2. Install Dependencies
```sh
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the project root (never commit this file!). Example:
```env
# Google Gemini API Key
GEMINI_API_KEY=your_gemini_api_key_here

# Google OAuth
GMAIL_CLIENT_ID=your_gmail_client_id_here
GMAIL_CLIENT_SECRET=your_gmail_client_secret_here

# Slack OAuth
SLACK_CLIENT_ID=your_slack_client_id_here
SLACK_CLIENT_SECRET=your_slack_client_secret_here

# OIDC / Replit Auth
REPL_ID=your_oidc_client_id_here
REPLIT_DOMAINS=localhost,127.0.0.1

# Other
NODE_ENV=development
```

**Never commit your `.env` file or secrets!**

### 4. Run the App
```sh
npm run dev
```
The app will be available at [http://localhost:3001](http://localhost:3001)

## 🧑‍💻 Contributing
1. Fork the repo and create your branch: `git checkout -b feature/your-feature`
2. Commit your changes: `git commit -am 'Add new feature'`
3. Push to the branch: `git push origin feature/your-feature`
4. Open a Pull Request

## 📝 License
MIT

## 🙏 Acknowledgements
- [Google Gemini AI](https://ai.google.dev/)
- [Google Cloud Console](https://console.cloud.google.com/)
- [Slack API](https://api.slack.com/)
- [React](https://react.dev/), [TailwindCSS](https://tailwindcss.com/), [Framer Motion](https://www.framer.com/motion/)

---
**For any issues or questions, please open an issue on GitHub.** 