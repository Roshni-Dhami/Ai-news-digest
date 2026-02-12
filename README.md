# Ai-news-digest
# 🤖 AI-Powered News Digest

Automate your daily tech news with n8n and Groq AI. Get personalized, AI-curated news digests delivered to your inbox every morning.

## 📸 Preview

![Email Sample](<img width="950" height="391" alt="screenshots-email-sample1" src="https://github.com/user-attachments/assets/f038cf02-d2a7-4fc3-9c2d-94ff7f1abda1" />
)

## ✨ What It Does

- 📰 Aggregates news from 10+ tech RSS feeds
- 🤖 AI filters to your top 10 most relevant articles using Groq
- ✍️ Generates smart summaries and key insights
- 📧 Sends beautiful HTML email digest daily
- ⏱️ **Saves 4+ hours per week** of manual reading

## 🛠️ Tech Stack

- **n8n** - Workflow automation
- **Groq API** - AI filtering (Llama 3.3 70B) - FREE
- **Gmail** - Email delivery
- **RSS Feeds** - News sources

## 🚀 Quick Setup (5 Minutes)

### Prerequisites

- n8n installed ([self-hosted](https://docs.n8n.io/hosting/) or [cloud](https://n8n.io))
- Free Groq API key from [console.groq.com](https://console.groq.com)
- Gmail account

### Installation

1. **Download the workflow**
```bash
   git clone https://github.com/yourusername/ai-news-digest.git
   cd ai-news-digest
```

2. **Import to n8n**
   - Open n8n
   - Click **"Import from File"**
   - Select `workflow.json`
   - Workflow will be imported!

3. **Set up credentials**
   
   **Groq API:**
   - Get free API key: https://console.groq.com
   - In n8n, find the "HTTP Request" node
   - Add your Groq API key in Authentication

   **Gmail:**
   - Option A: Use Gmail OAuth (more secure)
   - Option B: Use SMTP with App Password (easier)
   - See [Gmail Setup Guide](#gmail-setup)

4. **Configure preferences**
   - Find the "Set" or "Edit Fields" node
   - Update `userInterests` with your topics
   - Update `excludeTopics` with topics to avoid

5. **Activate workflow**
   - Click **"Active"** toggle at top
   - Workflow runs daily at 8 AM automatically!

## 📋 RSS Feeds Included

- OpenAI Blog
- Anthropic News  
- VentureBeat AI
- TechCrunch AI
- Hacker News
- GitHub Blog
- Hugging Face
- arXiv AI
- YourStory
- Moneycontrol Tech

**Want to add more?** Just duplicate an RSS node and change the URL!

## ⚙️ Customization

### Change Interests

Edit the "Set" node:
```javascript
userInterests: "Your topics here"
excludeTopics: "Topics to avoid"
maxArticles: 10
```

### Change Schedule

Edit the "Schedule Trigger" node:
- Change time (default: 8:00 AM)
- Change days (default: Daily)

### Add More RSS Feeds

1. Copy any RSS Feed node
2. Paste it
3. Change the URL
4. Connect to Merge node

### Change AI Model

In HTTP Request node, change:
```json
"model": "llama-3.3-70b-versatile"
```

To any [Groq model](https://console.groq.com/docs/models):
- `mixtral-8x7b-32768` - Faster, cheaper
- `llama-3.3-70b-versatile` - Best quality (recommended)

## 📊 How It Works
```
RSS Feeds (100+ articles)
    ↓
Merge All Sources
    ↓
Format Articles
    ↓
Your Preferences
    ↓
Groq AI Filters → Top 10 Articles
    ↓
Sort by Relevance
    ↓
Generate HTML Email
    ↓
Send to Gmail ✉️
```

## 🎯 Example Email Output

**Subject:** 📰 Your Daily Digest: 10 Articles - February 12, 2025

**Content:**
- Digest intro (AI-generated)
- 3 key insights from all articles
- 10 articles sorted by relevance (8-10 score)
  - Each with AI summary
  - Source and date
  - Direct link to article

## 🐛 Troubleshooting

**Only getting 2 articles?**
- Update Groq prompt to say "select exactly 10 articles"
- Check Parse Response takes first 10 regardless

**Getting [object Object] in email?**
- Update Parse Response to convert objects to strings
- See code in workflow.json

**Email not sending?**
- Check Gmail credentials
- Verify Gmail node is configured
- Test with Execute Workflow button

## 📈 Performance

- **Execution Time:** ~30 seconds
- **Articles Scanned:** 100-120 per day
- **Articles Delivered:** 10 most relevant
- **Filtering Rate:** ~90%
- **Time Saved:** 4-6 hours per week


**Built with:**
- [n8n](https://n8n.io) - Workflow automation
- [Groq](https://groq.com) - AI inference

---

⭐ **Like this project? Give it a star!**

Made with ❤️ by [Your Name]
