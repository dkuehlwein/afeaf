# Message Broker Service

## Overview
The Message Broker service provides asynchronous communication capabilities for AFEAF components using ZeroMQ as the underlying message broker. It supports pub/sub messaging patterns with no central broker required.

## Key Features
- Asynchronous message publishing
- Topic-based subscriptions
- Zero-copy message passing
- No central broker needed
- Low latency communication
- Error handling and recovery
- Built-in metrics collection

## Architecture

### Components
1. **Socket Manager**
   - ZeroMQ socket creation
   - Socket lifecycle management
   - Port allocation

2. **Topic Manager**
   - Topic validation
   - Subscription management
   - Message routing

3. **Message Handler**
   - Message validation
   - Schema enforcement
   - Error handling

4. **Metrics Collector**
   - Message delivery tracking
   - Error rate monitoring
   - Performance metrics

### Message Types
1. **Task Messages**
   - New task assignments
   - Progress updates
   - Completion notifications

2. **System Messages**
   - Health checks
   - Configuration updates
   - Control commands

### Topic Structure
```
afeaf/
  tasks/
    new/          # New task submissions
    progress/     # Task progress updates
    complete/     # Completed task results
  system/
    health/       # Component health updates
    config/       # Configuration changes
    control/      # System control messages
```

## Message Schema
```python
{
    "message_id": "uuid",
    "timestamp": "datetime",
    "sender": {
        "id": "string",
        "type": "string"
    },
    "payload": {
        "type": "string",
        "content": "object",
        "metadata": "object"  # Optional
    }
}
```

## API Endpoints

### Publishing
- `POST /publish/{topic}`
  - Publishes a message to specified topic
  - Validates message schema
  - Returns message ID and status

### Subscription
- `GET /subscribe/{topic}`
  - WebSocket endpoint for real-time updates
  - Direct ZeroMQ subscription
  - Automatic reconnection
  - Message persistence and replay

### Monitoring
- `GET /health`
  - Service health status
  - Topic statistics
  - Socket status
  - Connection count

- `GET /metrics`
  - System-wide metrics
    - Total messages
    - Error rates
    - Active topics
    - Subscriber counts
  - Per-topic metrics
    - Message counts
    - Delivery times
    - Error counts
    - Subscriber counts

## Error Handling
1. **Socket Errors**
   - Automatic socket recreation
   - Port reallocation
   - Connection recovery

2. **Message Errors**
   - Invalid topic handling
   - Schema validation
   - Error metrics collection

## Message Persistence
1. **Storage**
   - In-memory message store
   - Message acknowledgment tracking
   - Delivery attempt tracking

2. **Reliability**
   - Message redelivery for new subscribers
   - Dead letter handling
   - Periodic cleanup of old messages

## Windows Setup
1. Install Visual C++ Redistributable
   ```powershell
   # Download from Microsoft's website
   Start-Process "https://aka.ms/vs/17/release/vc_redist.x64.exe"
   ```

2. Environment Variables
   ```
   SERVICE_HOST=0.0.0.0
   SERVICE_PORT=8001
   PUB_BASE_PORT=5555
   SUB_BASE_PORT=6555
   ```

## Development Guidelines
1. Use async sockets
2. Handle socket lifecycle
3. Validate message schemas
4. Implement proper cleanup
5. Log important events
6. Monitor socket status
7. Handle reconnection gracefully

## Testing
1. Unit tests for message handling
2. Integration tests with ZeroMQ
3. Load tests for performance
4. Failure scenario testing

## Monitoring
1. Message rates
2. Error rates
3. Socket status
4. Memory usage
5. Response times 