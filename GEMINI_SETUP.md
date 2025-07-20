# Gemini AI Setup for Email Categorization

This application uses Google's Gemini AI to automatically categorize your emails into Urgent, FYI, and Ignored categories after connecting your Gmail account.

## Setup Instructions

### 1. Get Your Gemini API Key

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the generated API key

### 2. Configure the API Key

Create a `.env` file in the root directory of this project with the following content:

```env
# Gemini AI API Key for email categorization
GEMINI_API_KEY=your_actual_api_key_here

# Other configuration variables...
GMAIL_CLIENT_ID=your_gmail_client_id_here
GMAIL_CLIENT_SECRET=your_gmail_client_secret_here
SLACK_CLIENT_ID=your_slack_client_id_here
SLACK_CLIENT_SECRET=your_slack_client_secret_here
REPL_ID=your_replit_id_here
REPLIT_DOMAINS=your_replit_domains_here
NODE_ENV=development
```

### 3. How It Works

After connecting your Gmail account:

1. **Automatic Categorization**: The system automatically categorizes your recent emails (up to 20) when you first connect Gmail
2. **Manual Sync**: Use the "Sync Data" button in the dashboard to categorize new emails
3. **Smart Classification**: Emails are classified as:
   - **Urgent**: Requires immediate action, has deadlines, critical issues
   - **FYI**: Informational content, updates, non-actionable information
   - **Ignored**: Spam, promotional content, automated notifications

### 4. Fallback Processing

If the GEMINI_API_KEY is not configured, the system will use intelligent keyword-based fallback processing that still provides good categorization results.

### 5. Features

- **Duplicate Prevention**: The system prevents processing the same email multiple times
- **Rich Metadata**: Each categorized email includes:
  - Summary and action items
  - Urgency score (1-5)
  - Sentiment analysis
  - Business impact assessment
  - Context tags and stakeholders
  - Follow-up requirements

### 6. Troubleshooting

- **No API Key**: The system will log a warning and use fallback processing
- **API Errors**: Check your API key and internet connection
- **Rate Limits**: The system handles Gemini API rate limits gracefully

### 7. Privacy

- Email content is sent to Gemini AI for processing
- No email content is stored permanently in the AI system
- Only categorized metadata is stored in your local database
- Review Google's [AI Studio Privacy Policy](https://ai.google.dev/privacy) for more details 