# 📬 Daily Software Engineering Trends Newsletter Agent

## 🤖 Overview
An automated n8n workflow agent that curates daily software engineering trends, summarizes them using AI, formats them into a beautiful HTML email, and delivers them directly to your inbox every morning.

## 🌟 Features
- **Daily Automation**: Runs automatically every 24 hours
- **Trend Discovery**: Searches for latest software engineering trends using Serper.dev
- **AI Summarization**: Uses Google Gemini to generate concise summaries
- **Beautiful Formatting**: Transforms content into responsive HTML/CSS templates
- **Email Delivery**: Sends curated newsletter directly to your email
- **Fully Automated**: Zero manual intervention required

## 🛠️ Technology Stack
- **Workflow Engine**: n8n
- **Search API**: Serper.dev
- **AI Processing**: Google Gemini
- **Email Delivery**: SMTP or n8n Email Trigger
- **Formatting**: HTML5 + CSS3
- **Scheduling**: n8n Schedule Trigger

## 🔧 Workflow Structure

### 1. **Trigger**
- Schedule Trigger: Runs daily at 6:00 AM (configurable)

### 2. **Trend Discovery**
- HTTP Request node to Serper.dev API
- Searches for queries like:
  - "latest software engineering trends"
  - "new programming frameworks"
  - "developer tools updates"
  - "tech industry news"

### 3. **Content Processing**
- Filter nodes to remove duplicates
- Data organization nodes
- Content validation and cleaning

### 4. **AI Summarization**
- Google Gemini API integration
- Prompt engineering for concise summaries
- Key points extraction
- Trend analysis and insights

### 5. **HTML Generation**
- Template nodes for HTML structure
- CSS styling for readability
- Responsive design for mobile viewing
- Branding and visual elements

### 6. **Email Delivery**
- SMTP node configuration
- Email template integration
- Attachment handling (optional PDF version)
- Delivery confirmation

## 📋 Prerequisites

### API Keys Required:
1. **Serper.dev API Key**
   - Get from: [serper.dev](https://serper.dev)
   - Used for Google search results

2. **Google Gemini API Key**
   - Get from: [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Used for AI summarization

3. **Email Service Credentials**
   - SMTP settings (Gmail, Outlook, etc.)
   - Or n8n Email Trigger setup

### n8n Setup:
- n8n instance running (self-hosted or cloud)
- Workflow storage configured
- Webhook/Schedule capabilities enabled

## 🚀 Installation & Setup

### Step 1: Clone/Import Workflow
```bash
# Export your workflow from n8n and save as JSON
# Or import the provided workflow template
```

### Step 2: Configure API Credentials
1. Open n8n workflow editor
2. Configure Serper.dev node with your API key
3. Set up Gemini node with Google API key
4. Configure email node with SMTP details

### Step 3: Customize Search Parameters
- Edit search queries in Serper.dev node
- Adjust result count (default: 10 articles)
- Modify date filters if needed

### Step 4: Schedule Configuration
- Set desired daily execution time
- Configure timezone
- Set up error handling and retries

### Step 5: Email Template Customization
- Modify HTML/CSS in template nodes
- Update sender/recipient information
- Add personal branding

## ⚙️ Configuration Variables

### Environment Variables (Optional):
```bash
SERPER_API_KEY=your_serper_api_key
GEMINI_API_KEY=your_gemini_api_key
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
```

### Workflow Parameters:
- `searchQuery`: Software engineering trend keywords
- `maxResults`: Number of articles to fetch (5-15)
- `summaryLength`: Word count for AI summaries (100-200)
- `scheduleTime`: Daily execution time (HH:MM)
- `emailRecipient`: Your email address

## 📊 Workflow Nodes Breakdown

1. **Schedule Trigger**
   - Type: Cron expression (0 6 * * *)
   - Timezone: Your local timezone

2. **Serper.dev Search**
   - Method: POST
   - Endpoint: https://google.serper.dev/search
   - Query: Custom search parameters

3. **Data Processing**
   - Split/merge nodes
   - Filter duplicates
   - Sort by relevance

4. **Gemini AI Processing**
   - Model: gemini-pro
   - Temperature: 0.7
   - Max tokens: 500

5. **HTML Template**
   - Custom HTML/CSS
   - Responsive design
   - Dark/light mode support

6. **Email Node**
   - SMTP configuration
   - HTML content
   - Subject line formatting

## 🎨 Customization Options

### Content Customization:
- Modify search keywords
- Adjust summary tone/format
- Add/remove content sections
- Include personal commentary

### Design Customization:
- Edit CSS in template nodes
- Change color scheme
- Modify layout structure
- Add logos/images

### Delivery Customization:
- Change schedule frequency
- Add multiple recipients
- Include attachments
- Add unsubscribe option

## 🔒 Security Considerations

1. **API Keys**: Store securely in n8n credentials
2. **Email Security**: Use app passwords, not main passwords
3. **Data Privacy**: No personal data collection
4. **Rate Limiting**: Respect API rate limits

## 📈 Monitoring & Maintenance

### Logs to Monitor:
- API response times
- Email delivery status
- Error rates
- Content quality metrics

### Regular Updates:
- Update API keys when necessary
- Refresh search queries monthly
- Test email deliverability
- Review AI summarization quality

## 🐛 Troubleshooting

### Common Issues:

1. **No Results Found**
   - Check Serper.dev API key
   - Verify search queries
   - Check rate limits

2. **AI Summarization Fails**
   - Verify Gemini API key
   - Check prompt formatting
   - Review content length

3. **Email Not Sending**
   - Check SMTP settings
   - Verify email credentials
   - Check spam folder

4. **Schedule Not Triggering**
   - Verify n8n scheduler
   - Check timezone settings
   - Review workflow activation status

### Debug Steps:
1. Test each node individually
2. Check n8n execution logs
3. Verify API responses
4. Test with sample data

## 📝 Example Output

**Email Subject:** 
`Daily Software Engineering Trends - Dec 18th`

**Email Content Includes:**
- Top 5-10 trending topics
- Concise AI-generated summaries
- Source links for each trend
- Key takeaways section
- Visual formatting with CSS

## 🔄 Future Enhancements

### Planned Features:
- [ ] Multiple language support
- [ ] Topic categorization
- [ ] Sentiment analysis
- [ ] Trending GitHub repos
- [ ] Podcast/video content
- [ ] Personalization based on interests
- [ ] Analytics dashboard
- [ ] Social media sharing

### Integration Possibilities:
- Slack/Teams notifications
- RSS feed generation
- PDF report generation
- Database storage for history
- Web dashboard for viewing

## 📄 License
Customize as needed for your organization

## 👥 Contributors
- Bouzid Kobchi

## 🙏 Acknowledgements
- [n8n](https://n8n.io) for workflow automation
- [Serper.dev](https://serper.dev) for search API
- [Google Gemini](https://ai.google.dev) for AI capabilities

## 📞 Support
For issues with this workflow:
1. Check n8n community forums
2. Review API documentation
3. Test with simplified workflow
4. Contact workflow maintainer

---

**Last Updated**: Dec 18th 2025
**Version**: 1.0.0
**Workflow Status**: ✅ Active & Running

*Enjoy your daily dose of software engineering trends!* 🚀
