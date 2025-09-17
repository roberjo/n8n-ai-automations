# Free Alternatives to Firecrawl API

This document outlines free alternatives to the Firecrawl API that can be used in your n8n workflows to reduce costs while maintaining functionality.

## Current Firecrawl Usage in Project

The following workflows currently use Firecrawl API:
- **Marketing Ecosystem**: `write_newsletter_tool.json`, `email_research_report_tool.json`
- **Content Pipeline**: `ai_scraping_pipeline.json`, `ai_news_data_ingestion.json`
- **AI Agents**: `web_develop_agent_tool_scrape_website.json`, `ai_gmail_agent.json`
- **Utility Tools**: `firecrawl_scrape_url.json`, `firecrawl_email_scraper.json`, `local_podcast_generator.json`

## Free Alternatives

### 1. **n8n Built-in HTML Extract Node** ⭐ **RECOMMENDED**
- **Cost**: Completely free (built into n8n)
- **Setup**: No additional setup required
- **Features**: 
  - Extract data from HTML using CSS selectors
  - Built-in HTML parsing
  - Works with HTTP Request node
- **Limitations**: 
  - No JavaScript rendering
  - Manual selector configuration required
- **Best For**: Simple HTML scraping, static content extraction

### 2. **n8n HTTP Request + Cheerio Node**
- **Cost**: Completely free (built into n8n)
- **Setup**: Use HTTP Request node + Cheerio for HTML parsing
- **Features**:
  - Full HTML parsing capabilities
  - CSS selector support
  - JSON output formatting
- **Limitations**: No JavaScript rendering
- **Best For**: Static websites, API responses

### 3. **Crawl4AI** (Open Source)
- **Cost**: Free (self-hosted)
- **Setup**: Requires Docker deployment
- **Features**:
  - Clean Markdown generation
  - Advanced browser control
  - LLM integration
  - Proxy support
- **Limitations**: Requires technical setup and maintenance
- **Best For**: Complex scraping with AI integration

### 4. **GPT-Crawler** (Open Source)
- **Cost**: Free (self-hosted)
- **Setup**: Requires Node.js deployment
- **Features**:
  - AI-powered content structuring
  - Headless browser support
  - Knowledge file generation
- **Limitations**: Infrastructure costs, technical setup
- **Best For**: AI-focused scraping workflows

### 5. **LLM-Scraper** (Open Source)
- **Cost**: Free (self-hosted)
- **Setup**: TypeScript library deployment
- **Features**:
  - Structured data extraction
  - LLM integration
  - TypeScript support
- **Limitations**: Complex setup, limited support
- **Best For**: Developers with TypeScript knowledge

### 6. **Firecrawl Self-Hosted** (Open Source)
- **Cost**: Free (self-hosted)
- **Setup**: Docker deployment from GitHub
- **Features**:
  - Full Firecrawl functionality
  - No API limits
  - Customizable
- **Limitations**: Requires server infrastructure
- **Best For**: High-volume usage, full control

## Implementation Recommendations

### For Simple Scraping (Immediate Implementation)
Replace Firecrawl API calls with:
1. **HTTP Request Node** → **HTML Extract Node**
2. Configure CSS selectors for data extraction
3. Use n8n's built-in HTML parsing

### For Complex Scraping (Medium-term Implementation)
1. **Deploy Crawl4AI** as a self-hosted service
2. Create custom n8n workflows that call your Crawl4AI instance
3. Maintain full control over scraping logic

### For High-Volume Usage (Long-term Implementation)
1. **Self-host Firecrawl** using their open-source version
2. Deploy on your own infrastructure
3. No API limits or costs

## Migration Strategy

### Phase 1: Quick Wins (1-2 days)
- Replace simple Firecrawl calls with n8n HTML Extract node
- Update workflows that only need basic HTML parsing
- Test with static websites first

### Phase 2: Advanced Features (1-2 weeks)
- Deploy Crawl4AI for JavaScript-heavy sites
- Update complex scraping workflows
- Implement error handling and retry logic

### Phase 3: Full Migration (1 month)
- Self-host Firecrawl for complete feature parity
- Migrate all remaining workflows
- Implement monitoring and maintenance

## Cost Savings Analysis

### Current Firecrawl Costs
- **Pay-per-request pricing** (varies by plan)
- **High-volume operations** can be expensive
- **Multiple workflows** using the same service

### Free Alternative Benefits
- **Zero API costs** for built-in n8n nodes
- **No rate limits** for self-hosted solutions
- **Full control** over scraping logic
- **Customizable** for specific needs

## Code Examples

### n8n HTML Extract Node Example
```json
{
  "nodes": [
    {
      "parameters": {
        "url": "https://example.com",
        "options": {}
      },
      "type": "n8n-nodes-base.httpRequest",
      "name": "HTTP Request"
    },
    {
      "parameters": {
        "extractionValues": {
          "values": [
            {
              "key": "title",
              "cssSelector": "h1",
              "returnValue": "text"
            },
            {
              "key": "content",
              "cssSelector": ".content",
              "returnValue": "html"
            }
          ]
        }
      },
      "type": "n8n-nodes-base.htmlExtract",
      "name": "HTML Extract"
    }
  ]
}
```

### Crawl4AI Integration Example
```json
{
  "parameters": {
    "url": "https://api.your-crawl4ai-instance.com/crawl",
    "method": "POST",
    "sendBody": true,
    "jsonBody": {
      "url": "{{ $json.url }}",
      "formats": ["markdown", "json"]
    }
  },
  "type": "n8n-nodes-base.httpRequest",
  "name": "Crawl4AI Request"
}
```

## Next Steps

1. **Test n8n HTML Extract node** with your current workflows
2. **Identify which workflows** can be easily migrated
3. **Plan deployment** of self-hosted alternatives for complex needs
4. **Update documentation** with new implementation details
5. **Monitor performance** and adjust as needed

## Support and Resources

- **n8n HTML Extract Documentation**: [n8n.io/docs](https://n8n.io/docs)
- **Crawl4AI GitHub**: [github.com/unclecode/crawl4ai](https://github.com/unclecode/crawl4ai)
- **Firecrawl Self-Hosted**: [github.com/firecrawl/firecrawl](https://github.com/firecrawl/firecrawl)
- **GPT-Crawler**: [github.com/builderio/gpt-crawler](https://github.com/builderio/gpt-crawler)
