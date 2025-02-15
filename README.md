# AFEAF: Agent-First Enterprise AI Framework

AFEAF is a framework that empowers AI agents to become capable digital coworkers while maintaining enterprise-grade reliability and security.

## Overview

We envision a future where AI agents work seamlessly alongside humans in enterprises, forming a collaborative ecosystem that amplifies human capabilities rather than replacing them. For a detailed exploration of our vision and implementation examples, see [docs/vision.md](docs/vision.md).

## Core Components

### Services
- **Registry**: Central hub for discovering and managing AI capabilities
- **Message Broker**: Reliable communication backbone between components
- **LLM Service**: Centralized gateway for AI reasoning and decision-making
- **Authentication**: Security and access control infrastructure

### Databases
- **Project Database**: Core project and operational data
- **Knowledge Bases**: Shared enterprise knowledge and context

### Applications & Tools
- **Applications**: Event monitors and enterprise solutions
- **Tools**: 
  - Memory Tools: Agent knowledge and conversation persistence
  - Integration Tools: Email, calendar, etc.
  - Analysis Tools: Data processing and insights
- **Agents**: AI entities that perform complex tasks

## Project Structure

```
afeaf/
├── docs/                   # Architecture, patterns, interfaces
├── registry/              # Central service registry
├── broker/                # Message broker service
├── auth/                  # Authentication service
├── databases/             # Database implementations
├── applications/          # Applications and monitors
├── tools/                 # Reusable tool implementations
│   └── memory/           # Memory persistence tools
├── agents/                # AI agents
└── README.md
```

## Getting Started

1. Clone the repository
2. Install dependencies (requirements coming soon)
3. Follow setup guides in the documentation

## Documentation

- [Vision and Concepts](docs/vision.md) - Detailed overview of AFEAF's vision and implementation examples
- [Architecture Guidelines](docs/architecture.md) - Technical guidelines and patterns
- [Registry Service](docs/registry.md) - Component registration and discovery
- [Message Broker](docs/broker.md) - Communication patterns
- [LLM Integration](docs/llm.md) - Language model integration
- [Tools](docs/tasks/README.md) - Available tools and capabilities
  - [Memory](docs/tools/memory.md) - Memory and persistence capabilities

## Contributing

We welcome contributions! Please see our [contribution guidelines](docs/contributing.md) for details on how to get involved.

## License

[License information coming soon]

## Installation

1. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create `.env` file:
```
OPENAI_API_KEY=your-openai-api-key-here
REDIS_URL=redis://localhost:6379  # Optional: if using cache
```

4. Start the service:
```bash
uvicorn main:app --reload
``` 