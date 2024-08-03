# Multithreaded Proxy Web Server

## Overview
The Multithreaded Proxy Web Server is a project implemented in C that serves as an intermediary for requests from clients seeking resources from other servers. This proxy server supports multithreading to handle multiple client requests concurrently and can operate with or without caching.

## Features
- **Multithreading**: Utilizes multiple threads to handle multiple client connections simultaneously, improving performance and responsiveness.
- **Caching (Optional)**: Can cache responses to reduce latency and load on upstream servers for frequently accessed resources.
- **HTTP Protocol**: Supports basic HTTP/1.0 and HTTP/1.1 protocols for web communication.

## File Structure
- `proxy_parse.c`: Contains functions for parsing HTTP requests and responses.
- `proxy_parse.h`: Header file for `proxy_parse.c`.
- `proxy_server_with_cache.c`: Implementation of the proxy server with caching functionality.
- `proxy_server_without_cache.c`: Implementation of the proxy server without caching functionality.

## Setup and Usage
### Prerequisites
- GCC Compiler
- POSIX Threads (pthreads) Library

### Compilation
To compile the proxy server without caching:
```bash
gcc -o proxy_server_without_cache proxy_server_without_cache.c -lpthread
```

To compile the proxy server with caching:
```bash
gcc -o proxy_server_with_cache proxy_server_with_cache.c -lpthread
```

### Running the Proxy Server
Without caching:
```bash
./proxy_server_without_cache <port>
```

With caching:
```bash
./proxy_server_with_cache <port>
```

Replace `<port>` with the desired port number on which the proxy server will listen for incoming connections.

## How It Works
1. **Client Connection**: The proxy server listens for incoming client connections on the specified port.
2. **Request Handling**: Each client request is handled in a separate thread to allow concurrent processing.
3. **Request Parsing**: The server parses the client's HTTP request to determine the target server and resource.
4. **Forwarding Request**: The proxy server forwards the request to the target server.
5. **Caching (if enabled)**: The response from the target server is cached for future requests.
6. **Response to Client**: The server sends the received response back to the client.

## Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate tests.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

For more details, visit the [Multithreaded Proxy Web Server GitHub Repository](https://github.com/Rohankumar19/Multithreaded-Proxy-Web-Server).
