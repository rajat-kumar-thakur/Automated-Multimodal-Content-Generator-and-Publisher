# 🚀 Multi-Modal Content Generator & Publisher

An automated n8n workflow that scrapes trending Reddit posts, analyzes their viral potential using AI, and generates + publishes optimized content across multiple social media platforms.

## 📋 Overview

This workflow automatically:
1. **Scrapes** trending posts from Reddit
2. **Analyzes** content using GPT-5-mini for viral potential
3. **Generates** platform-optimized content (images, videos, captions)
4. **Publishes** automatically to Twitter/X, Instagram, YouTube, and Telegram

## ✨ Features

- **AI-Powered Content Analysis**: Uses OpenAI's GPT-5-mini to evaluate viral potential (0-100 score)
- **Multi-Platform Publishing**: Automatic cross-posting to 5+ platforms
- **Visual Content Generation**: Creates images with Google Imagen and videos with Veo 3.1
- **Smart Optimization**: Platform-specific captions, hashtags, and formatting
- **Scheduled Automation**: Runs daily at 10 AM to find and publish trending content
- **Content Strategy**: Includes audience targeting and engagement tactics

## 🛠️ Tech Stack

- **Workflow Engine**: n8n
- **AI Models**: 
  - OpenAI GPT-5-mini (content analysis)
  - Google Imagen 4.0 (image generation)
  - Google Veo 3.1 (video generation)
- **Platforms**: Reddit, Twitter/X, Instagram, YouTube, Telegram
- **Storage**: Google Drive (media backup)

## 🔧 Prerequisites

You'll need accounts and API credentials for:

- [ ] n8n instance (self-hosted or cloud)
- [ ] OpenAI API
- [ ] Google Cloud (Gemini API for Imagen & Veo)
- [ ] Reddit API
- [ ] Twitter/X API (OAuth 2.0)
- [ ] Facebook Graph API (for Instagram)
- [ ] YouTube API
- [ ] Telegram Bot Token
- [ ] Google Drive API

## 📦 Installation

1. **Import the workflow** into your n8n instance:
   ```bash
   # Import main.json into n8n
   ```

2. **Configure credentials** for each service in n8n:
   - OpenAI API
   - Google Cloud (Gemini)
   - Reddit OAuth2
   - Twitter OAuth2
   - Facebook Graph API
   - YouTube OAuth2
   - Telegram Bot API
   - Google Drive OAuth2

3. **Update workflow parameters**:
   - Set your Instagram Business Account ID (node: `17841472943134441`)
   - Configure Google Drive folder IDs for storage
   - Set your Telegram channel handle

4. **Activate the workflow** in n8n

## 🎯 How It Works

### Workflow Steps

1. **Schedule Trigger** (Daily at 10 AM)
   ↓
2. **Scrape Reddit** (`/r/all` for trending posts)
   ↓
3. **Sort by Engagement** (upvotes)
   ↓
4. **Filter Top 5 Posts**
   ↓
5. **AI Analysis** (GPT-5-mini evaluates viral potential)
   ↓
6. **Content Generation**:
   - Image: Google Imagen 4.0
   - Video: Google Veo 3.1 (8-second clips)
   ↓
7. **Multi-Platform Publishing**:
   - **Twitter/X**: Image post with viral caption
   - **Instagram**: Reel + Image post
   - **YouTube**: Short video upload
   - **Telegram**: Photo + Video to channel
   - **Google Drive**: Media backup

### Content Generated

For each trending post, the AI creates:

- ✅ **Virality Score** (0-100)
- ✅ **Twitter Image** with DALL-E-style prompt + caption
- ✅ **8-Second Video Concept** with script and visual style
- ✅ **YouTube Title & Description** (SEO-optimized)
- ✅ **Instagram Caption** with hashtags
- ✅ **Telegram Message** (formatted)
- ✅ **Content Strategy** (posting times, audience, tactics)

## 📊 Output Format

The AI generates structured JSON with:

```json
{
  "virality_score": 85,
  "twitter_image": {
    "dalle_prompt": "...",
    "viral_caption": "..."
  },
  "video_clip_8sec": {
    "concept": "...",
    "script": "...",
    "visual_style": "modern",
    "music_mood": "upbeat"
  },
  "youtube_content": { ... },
  "instagram_post": { ... },
  "content_strategy": { ... }
}
```

## ⚙️ Configuration

### Scheduling
Default: Daily at 10 AM. Modify in the **Schedule Trigger** node.

### Reddit Filtering
- Subreddit: `/r/all` (change in **Scrape Trendy post** node)
- Top posts by upvotes
- Limit: Top 5 posts

### Content Preferences
Adjust the AI prompt in the **Viral Content Generator** node to customize:
- Tone and style
- Target audience
- Platform priorities
- Content guidelines

## 🔐 Security Notes

- Store all API credentials securely in n8n
- Use OAuth 2.0 where available
- Regularly rotate API keys
- Monitor API usage and quotas

## 📈 Monitoring

Track workflow performance:
- Check n8n execution logs
- Monitor API rate limits
- Review published content engagement
- Adjust virality score thresholds

## 🐛 Troubleshooting

**Common Issues:**

1. **API Rate Limits**: Reduce frequency or post count
2. **Authentication Errors**: Refresh OAuth tokens
3. **Content Generation Fails**: Check AI model quotas
4. **Video Upload Issues**: Verify Google Drive permissions

## 🤝 Contributing

Contributions welcome! Areas for improvement:
- Additional platform integrations (LinkedIn, TikTok, etc.)
- Advanced content filtering
- A/B testing for captions
- Analytics dashboard

## 📄 License

MIT License - feel free to modify and use for your projects.

## 🙏 Acknowledgments

- n8n for the workflow automation platform
- OpenAI for GPT-5-mini
- Google for Imagen and Veo AI models
