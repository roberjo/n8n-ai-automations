# AI Agents Standalone

This folder contains independent AI agents that can operate autonomously for specific tasks and domains.

## Workflows Included

### Specialized AI Agents
- **web_developer_agent.json** - AI agent specialized in web development tasks
- **ai_gmail_agent.json** - Gmail automation and email management agent
- **dental_practice_voice_agent.json** - Voice-enabled agent for dental practice management
- **whatsapp_ai_chatbot_agent.json** - WhatsApp chatbot for customer service

### Supporting Tools
- **web_develop_agent_tool_scrape_website.json** - Website scraping tool for the web developer agent
- **web_develop_agent_tool_write_website_prd.json** - Product requirements document generator

## Dependencies & Third-Party Services

### AI/LLM Services
- **Google Gemini 2.5 Pro** - Primary language model for all agents
  - **Cost**: Pay-per-token pricing
  - **Usage**: All agent reasoning, content generation, and decision making

### Web Development Services
- **Lovable.dev** - AI-powered website builder
  - **Cost**: Pay-per-project pricing
  - **Usage**: web_developer_agent.json for website creation
- **Airtop** - Browser automation service
  - **Cost**: Pay-per-minute pricing
  - **Usage**: web_developer_agent.json for browser control

### Web Scraping & Data Collection
- **Firecrawl API** - Professional web scraping service
  - **Cost**: Pay-per-request pricing
  - **Usage**: Website analysis, content extraction
- **Google Drive API** - File storage and management
  - **Cost**: Free tier available, paid plans for more storage
  - **Usage**: Document storage, knowledge base management

### Communication Services
- **Gmail API** - Email management and automation
  - **Cost**: Free
  - **Usage**: ai_gmail_agent.json for email processing
- **WhatsApp Business API** - WhatsApp messaging
  - **Cost**: Pay-per-message pricing
  - **Usage**: whatsapp_ai_chatbot_agent.json
- **Google Calendar API** - Calendar management
  - **Cost**: Free
  - **Usage**: dental_practice_voice_agent.json for appointment scheduling

### Voice & Speech Services
- **ElevenLabs** - Text-to-speech and voice cloning
  - **Cost**: Pay-per-character pricing
  - **Usage**: dental_practice_voice_agent.json for voice responses

### Data Storage & Management
- **Google Sheets API** - Spreadsheet management
  - **Cost**: Free
  - **Usage**: Data logging, patient records, activity tracking
- **Google Docs API** - Document management
  - **Cost**: Free
  - **Usage**: Knowledge base creation, document generation

## Cost Considerations

### High-Volume Operations
- **Voice Processing**: ElevenLabs costs scale with speech generation volume
- **Web Scraping**: Firecrawl costs scale with request volume
- **Website Creation**: Lovable.dev costs per project
- **WhatsApp Messaging**: Costs scale with message volume

### Cost Optimization Tips
- Use free Google services where possible (Gmail, Calendar, Sheets, Docs)
- Cache scraped content to avoid re-scraping
- Batch operations to reduce API call overhead
- Monitor usage through service dashboards

## Agent Capabilities

### Web Developer Agent
- Website analysis and development
- Code generation and review
- Project planning and documentation
- **Dependencies**: Firecrawl API, Lovable.dev, Airtop, Google Gemini

### Gmail Agent
- Email automation and analysis
- Inbox management
- Email content generation
- **Dependencies**: Gmail API, Google Gemini, Google Drive, Google Sheets

### Dental Practice Voice Agent
- Appointment scheduling
- Patient communication
- Practice management automation
- **Dependencies**: Google Calendar API, ElevenLabs, Google Sheets, Google Gemini

### WhatsApp Chatbot
- Customer service automation
- Multi-language support
- Business process integration
- **Dependencies**: WhatsApp Business API, Google Gemini

## Usage

Each agent is designed to work independently and can be deployed for specific use cases. The web developer agent includes additional tools that enhance its capabilities for web development tasks.

## Setup Requirements

### Required Credentials
- Google Gemini API key
- Gmail OAuth credentials (for Gmail agent)
- Google Calendar API credentials (for dental agent)
- Google Drive API credentials
- Google Sheets API credentials
- Firecrawl API key (for web developer agent)
- Lovable.dev API key (for web developer agent)
- Airtop API key (for web developer agent)

### Optional Credentials
- ElevenLabs API key (for voice features)
- WhatsApp Business API credentials (for WhatsApp agent)
