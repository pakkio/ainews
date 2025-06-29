# AI Intelligence Platform

Real-time AI news analysis and strategic intelligence synthesis platform that dynamically aggregates, analyzes, and synthesizes AI developments from multiple sources.

## Features

### 🧠 Dynamic Intelligence Analysis
- Real-time search and aggregation from multiple sources (News APIs, arXiv, academic papers)
- AI-powered synthesis and strategic analysis
- Confidence scoring and source validation
- Multi-dimensional analysis (Strategic, Technical, Market, Regulatory)

### 🌍 Multi-Regional Intelligence
- Geopolitical analysis across China, USA, EU, and global markets
- Regional regulatory landscape tracking
- Cross-regional competitive intelligence

### 📊 Strategic Insights
- Market dynamics and investment flow analysis
- Technology trend identification and forecasting
- Regulatory compliance impact assessment
- Competitive landscape mapping

### ⚡ Real-time Processing
- Live data ingestion and processing
- Intelligent caching for performance
- Rate limiting and error handling
- Progressive loading and real-time updates

## Architecture

### Backend (Node.js/Express)
```
server.js                 # Main server with API endpoints
├── AIIntelligenceService # Core intelligence gathering service
├── News API integration  # Multiple news source aggregation
├── arXiv integration     # Academic paper search
├── AI Analysis Engine    # Strategic synthesis and insights
└── Caching & Rate Limit  # Performance and security
```

### Frontend (Vanilla JS/HTML)
```
index.html               # Interactive dashboard interface
├── Multi-tab navigation # Analysis Results, Geopolitical, Technology, Market, Regulatory
├── Real-time UI updates # Loading states, progress tracking
├── Dynamic content      # AI-generated insights and synthesis
└── Responsive design    # Mobile-first adaptive layout
```

## Installation & Setup

### Prerequisites
- Node.js 18+
- npm 8+

### Quick Start
```bash
# Clone and setup
git clone <repository-url>
cd ai-intelligence-platform
npm install

# Setup environment (optional but recommended)
cp .env.example .env
# Edit .env with your API keys

# Development mode
npm run dev

# Production mode
npm run build
npm start
```

### API Keys (Optional)
The platform works without API keys using mock data, but for production use:

```env
NEWS_API_KEY=your_news_api_key_here           # NewsAPI.org
GOOGLE_SEARCH_API_KEY=your_google_api_key     # Google Custom Search
OPENAI_API_KEY=your_openai_key               # OpenAI GPT models
ANTHROPIC_API_KEY=your_anthropic_key         # Claude models
```

## Usage

### Basic Analysis
1. Open `http://localhost:3000`
2. Enter analysis topic (e.g., "generative AI developments last week")
3. Select time frame and analysis depth
4. Click "Analyze" for real-time intelligence synthesis

### Advanced Queries
- **Regional Focus**: "AI regulation updates EU"
- **Technical Deep-dive**: "small language models efficiency gains"
- **Market Intelligence**: "AI funding rounds Q1 2025"
- **Regulatory Analysis**: "EU AI Act implementation timeline"

### Tab Navigation
- **Analysis Results**: Main synthesis and insights
- **Geopolitical**: Regional power dynamics and strategies
- **Technology**: Technical innovation vectors and trends
- **Market**: Investment flows and competitive dynamics
- **Regulatory**: Compliance landscape and policy evolution

## API Endpoints

### POST /api/analyze
Strategic intelligence analysis endpoint.

**Request:**
```json
{
  "query": "generative AI developments last week",
  "timeFrame": "week",
  "analysisDepth": "strategic",
  "region": "global"
}
```

**Response:**
```json
{
  "query": "generative AI developments last week",
  "searchResults": {
    "results": [...],
    "totalFound": 15
  },
  "analysis": {
    "summary": "Analysis of 15 sources reveals...",
    "insights": [...],
    "trends": [...],
    "implications": [...],
    "confidence": 0.85
  }
}
```

### GET /api/trending
Current trending AI topics and developments.

### GET /api/health
Service health check endpoint.

## Development

### Project Structure
```
ai-intelligence-platform/
├── package.json          # Dependencies and scripts
├── server.js            # Backend API server
├── index.html           # Frontend interface
├── .env.example         # Environment template
├── vite.config.js       # Build configuration
├── tailwind.config.js   # Styling configuration
├── logs/                # Application logs
└── dist/               # Production build
```

### Scripts
```bash
npm run dev        # Development server with hot reload
npm run build      # Production build
npm run start      # Production server
npm run lint       # Code linting
npm run test       # Run tests
```

### Customization

#### Adding New Data Sources
```javascript
// In AIIntelligenceService class
async searchNewSource(query) {
  // Implement new source integration
  // Return standardized result format
}

// Add to searchWebSources method
const results = await Promise.allSettled([
  this.searchNewsAPI(query, timeFrame),
  this.searchArxiv(query),
  this.searchNewSource(query)  // Add here
]);
```

#### Custom Analysis Models
```javascript
// Implement custom AI analysis
async generateCustomAnalysis(searchResults, query, depth) {
  // Your custom analysis logic
  // Return standardized analysis format
}
```

## Production Deployment

### Environment Setup
```bash
export NODE_ENV=production
export PORT=3001
# Set API keys in production environment
```

### Docker Deployment
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build
EXPOSE 3001
CMD ["npm", "start"]
```

### Security Considerations
- Rate limiting implemented (100 requests/minute per IP)
- Input validation and sanitization
- CORS and security headers via Helmet
- No sensitive data logging
- Environment variable isolation

## Performance

### Caching Strategy
- 30-minute intelligent caching for search results
- Memory-based cache with LRU eviction
- Configurable cache expiry times

### Rate Limiting
- IP-based rate limiting
- Configurable limits per endpoint
- Graceful degradation under load

### Optimization
- Parallel source querying
- Lazy loading for UI components
- Compressed responses
- Static asset optimization

## Monitoring

### Logging
- Structured logging with Winston
- Error tracking and performance metrics
- Configurable log levels
- Separate error and combined logs

### Health Checks
- `/api/health` endpoint for monitoring
- Service dependency validation
- Performance metrics tracking

## Contributing

### Development Workflow
1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Code Standards
- ESLint configuration for code quality
- Consistent error handling patterns
- Comprehensive API documentation
- Unit test coverage for core functionality

## License

MIT License - see LICENSE file for details.

## Support

For issues and feature requests, please use the GitHub issue tracker.

---

**Built for real-time AI intelligence and strategic analysis**