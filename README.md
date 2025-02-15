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

## Documentation

- [Vision and Concepts](docs/vision.md) - Detailed overview of AFEAF's vision and implementation examples
- [Architecture Guidelines](docs/architecture.md) - Technical guidelines and patterns
- [Registry Service](docs/registry.md) - Component registration and discovery
- [Message Broker](docs/broker.md) - Communication patterns
- [LLM Integration](docs/llm.md) - Language model integration
- [Tools](docs/tasks/README.md) - Available tools and capabilities
  - [Memory](docs/tools/memory.md) - Memory and persistence capabilities
