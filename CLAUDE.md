# CLAUDE.md - AI Intelligence Platform

## Project Overview
Dynamic AI Intelligence Platform for real-time news analysis and strategic synthesis. Built to transform AI information overload into actionable strategic intelligence.

## Core Architecture

### Intelligence Pipeline
```yaml
Sources: NewsAPI | arXiv | Academic Papers | Government APIs
Processing: AI Synthesis | Pattern Recognition | Confidence Scoring
Output: Strategic Intelligence | Market Analysis | Regulatory Impact
```

### Key Components
- **AIIntelligenceService**: Core intelligence gathering and synthesis engine
- **Multi-source Integration**: News APIs, academic papers, regulatory documents
- **Real-time Analysis**: Dynamic AI-powered synthesis and strategic insights
- **Regional Intelligence**: Geopolitical analysis across major AI markets

## Development Context

### Technology Stack
```yaml
Backend: Node.js + Express + Winston + Axios + Cheerio
Frontend: Vanilla JS + HTML5 + CSS3 (no framework dependencies)
APIs: OpenAI/Anthropic (optional) | NewsAPI | Google Custom Search
Cache: In-memory with configurable expiry
Security: Helmet + CORS + Rate Limiting
```

### Performance Optimizations
- Parallel source querying for speed
- Intelligent caching (30min default)
- Progressive loading UI
- Memory-efficient result processing

## Operational Commands

### Development
```bash
npm run dev     # Start development server (port 3000 frontend, 3001 backend)
npm run build   # Build production assets
npm start       # Production server
npm run lint    # Code quality check
```

### Key Endpoints
```yaml
POST /api/analyze: Main intelligence analysis endpoint
GET /api/trending: Current AI trend detection
GET /api/health: Service health monitoring
```

## Intelligence Features

### Analysis Modes
- **Strategic**: Executive-level synthesis and implications
- **Technical**: Deep-dive technical analysis and innovation vectors
- **Market**: Investment flows, competitive dynamics, market intelligence
- **Comprehensive**: Full-spectrum analysis across all dimensions

### Regional Analysis
- **China**: Efficiency leadership, open-source strategies
- **USA**: Strategic repositioning, competitive responses
- **EU**: Regulatory leadership, compliance-first architecture
- **Global**: Cross-regional trend synthesis

### Data Sources Integration
```javascript
// Example: Adding new intelligence source
async searchNewSource(query) {
  const response = await axios.get(sourceAPI, { params: { q: query }});
  return this.standardizeResults(response.data);
}
```

## AI Integration Strategy

### Current Implementation
- Mock analysis for development/demo
- Structured prompts for AI synthesis
- Confidence scoring and validation
- Source attribution and relevance ranking

### Production AI Integration
```javascript
// OpenAI Integration Example
async callOpenAI(prompt) {
  const response = await openai.chat.completions.create({
    model: 'gpt-4-turbo-preview',
    messages: [{ role: 'user', content: prompt }],
    temperature: 0.3,
    max_tokens: 2000
  });
  return response.choices[0].message.content;
}
```

### Analysis Prompt Structure
```yaml
Context: Search results + regional focus + time frame
Instructions: Analysis depth + output format requirements
Output: JSON structured insights + confidence scores
```

## Security & Performance

### Security Measures
```yaml
Rate Limiting: 100 requests/minute per IP
Input Validation: Query sanitization and length limits
CORS: Configured for frontend-backend communication
Headers: Security headers via Helmet middleware
Logging: Structured logging without sensitive data
```

### Caching Strategy
```yaml
Key Pattern: search_${query}_${timeFrame}
Expiry: 30 minutes (configurable)
Storage: In-memory Map with timestamp validation
Invalidation: Automatic on expiry, manual clear option
```

## Customization Points

### Adding Intelligence Sources
1. Implement search method in AIIntelligenceService
2. Add to Promise.allSettled in searchWebSources
3. Ensure standardized output format
4. Update relevance scoring if needed

### Custom Analysis Models
```javascript
// Custom synthesis engine
async generateCustomAnalysis(searchResults, query, depth) {
  const prompt = this.buildCustomPrompt(searchResults, query, depth);
  const analysis = await this.callCustomAI(prompt);
  return this.parseCustomResponse(analysis);
}
```

### UI Customization
- Tab system for different analysis views
- Real-time progress indicators
- Responsive design with mobile support
- Dark theme with gradient accents

## Environment Configuration

### Required for Production
```env
NEWS_API_KEY=your_key_here        # NewsAPI.org access
OPENAI_API_KEY=your_key_here      # AI analysis (optional)
ANTHROPIC_API_KEY=your_key_here   # Alternative AI (optional)
```

### Optional Enhancements
```env
GOOGLE_SEARCH_API_KEY=your_key    # Enhanced web search
GOOGLE_SEARCH_ENGINE_ID=your_id   # Custom search engine
```

## Monitoring & Debugging

### Logging Structure
```yaml
Levels: error, warn, info, debug
Format: JSON with timestamps
Files: logs/error.log, logs/combined.log
Console: Development friendly format
```

### Health Monitoring
```javascript
GET /api/health
Response: { status: 'ok', timestamp: '2025-01-XX' }
```

### Performance Metrics
- Response times per endpoint
- Cache hit/miss ratios
- Source availability tracking
- Analysis quality scores

## Future Enhancements

### Intelligence Pipeline
- Real-time WebSocket updates
- Trend prediction algorithms
- Sentiment analysis integration
- Cross-source fact verification

### Data Sources
- Patent database integration
- Regulatory filing analysis
- Social media sentiment tracking
- Company earnings call analysis

### Analysis Capabilities
- Multi-language source support
- Historical trend comparison
- Competitive intelligence scoring
- Risk assessment frameworks

## Deployment Considerations

### Production Setup
```yaml
Server: Node.js 18+ with PM2 process management
Database: Consider Redis for distributed caching
CDN: Static asset delivery optimization
Monitoring: Application performance monitoring (APM)
```

### Scaling Strategy
- Horizontal scaling with load balancers
- Database-backed caching for multi-instance setups
- Queue-based processing for heavy analysis tasks
- Microservice architecture for source-specific processing

---
*AI Intelligence Platform - Strategic Analysis at Scale*