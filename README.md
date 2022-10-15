# easy-socketio
Wrapper around python-socketio that handles a simple que and threading.

Example with default configs:

```python
from easy_socketio import socketio

socketio.start_server()

# Wait for connections....

# Send message to all clients

socketio.send("Hello clients")

```

Example with more detailed configuration:


```python
from easy_socketio import socketio

# Threaded flag starts the server in a background thread, default is True

socketio.start_server(host="127.0.0.1", port=5000, threaded=True, cors=True, static_files={'/': {'content_type': 'text/html'}})

# Wait for connections....

# Send message to a specific client

socketio.send(msg="Hello client", event="message", to="client_sid_here")
```