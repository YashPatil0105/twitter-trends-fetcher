# Twitter Trends Fetcher

An enterprise-grade Flask application for automated Twitter trends analysis, leveraging Selenium-based web scraping and MongoDB persistence.

## Overview

This application provides real-time tracking of Twitter's trending topics through automated data collection and persistence. It employs robust proxy rotation via ProxyMesh to ensure reliable data gathering while maintaining operational security.

## Core Features

- Real-time trend extraction using Selenium-powered web scraping
- Secure data persistence in MongoDB with IP tracking
- Automated proxy rotation through ProxyMesh integration
- Responsive web interface built on Bootstrap
- Comprehensive error handling and recovery mechanisms

## Technical Requirements

### System Dependencies
- Python 3.10.12+
- Chrome/Chromium browser
- ChromeDriver (matching browser version)
- MongoDB 4.4+ (local or Atlas)

### External Services
- Twitter account credentials
- ProxyMesh subscription
- MongoDB Atlas cluster (recommended) or local instance

## Installation Guide

1. Clone the repository:
```bash
git clone git@github.com:your-username/twitter-trends-fetcher.git
cd twitter-trends-fetcher
```

2. Set up Python virtual environment:
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# Unix/MacOS
source .venv/bin/activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

4. Configure environment variables:
```bash
# .env file configuration
PROXY_USERNAME="proxy_user"
PROXY_PASSWORD="proxy_pass"
PROXY_HOST="proxy.proxymesh.com"
PROXY_PORT="31280"
TWITTER_USERNAME="twitter_user"
TWITTER_PASSWORD="twitter_pass"
TWITTER_EMAIL="twitter_email"
MONGODB_URI="mongodb+srv://..."
```

## Architecture
twitter-trends-fetcher/
├── app/
│   ├── services/
│   │   ├── __pycache__/
│   │   ├── mongodb_service.py    # MongoDB operations
│   │   └── selenium_service.py   # Web scraping logic
│   ├── templates/
│   │   ├── dashboard.html        # Trends dashboard
│   │   ├── index.html           # Main interface
│   │   └── layout.html          # Base template
│   ├── __init__.py              # App initialization
│   ├── config.py                # Configuration settings
│   └── routes.py                # Route handlers
├── venv/                        # Virtual environment
├── .env                         # Environment variables
├── .gitignore                   # Git ignore rules
├── README.md                    # Documentation
├── requirements.txt             # Dependencies
└── run.py                       # Entry point

## Deployment

1. Verify environment configuration:
```bash
python -c "from app import create_app; create_app().test_client().get('/')"
```

2. Launch application:
```bash
python run.py
```

3. Access web interface:
```
http://localhost:5000
```

## Operational Flow

1. User initiates trend collection via web interface
2. System authenticates with Twitter using provided credentials
3. ProxyMesh handles IP rotation for request routing
4. Selenium extracts trending topics
5. Data persists to MongoDB with metadata
6. Interface updates with retrieved trends

## Error Handling Mechanisms

The application implements comprehensive error handling for:

- Multi-factor authentication flows
- Rate limiting scenarios
- Network connectivity issues
- Database operation failures
- Proxy routing problems

## Security Considerations

- Credentials stored in environment variables
- Proxy rotation for request anonymization
- MongoDB access restricted by network rules
- Input sanitization for all user interactions

## Performance Optimizations

- Connection pooling for MongoDB operations
- Selenium session reuse
- Proxy connection caching
- Minimal DOM manipulation

## Screenshots

![Dashboard Interface](./images/image-1.png)
![Trend Analysis View](./images/image.png)
![Historical Data](./images/image-2.png)
![Error Handling](./images/image-3.png)

## Development Workflow

1. Fork repository
2. Create feature branch (`git checkout -b feature/enhancement`)
3. Commit changes (`git commit -am 'Add enhancement'`)
4. Push branch (`git push origin feature/enhancement`)
5. Submit Pull Request

## License

This project is licensed under the MIT License - see LICENSE.md for details.

## Acknowledgments

- Selenium WebDriver community
- MongoDB Atlas team
- ProxyMesh service
- Flask framework contributors# twitter-trends-fetcher
