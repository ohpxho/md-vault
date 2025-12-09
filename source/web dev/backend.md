# Backend Notes - Dec. 07, 2025

## What is a Backend

- A server or computer that host the resources and logic of an application serve to the end users
- Listens to HTTP/HTTPs, Websocket, gRPC, etc. requests.

### What is a reverse proxy

- A server that sits in the middle of the end user and the application
- It intercepts request from the client and communicate these to web servers preventing direct exposure of backend server in the internet, which greatly improve the security
- It can help at blocking access to certain contents

### Why not write backend logic in frontend?

- Security reasons, the frontend is public code and anyone can view, modify, bypass, steal api keys, and manipulate the data - You cannot hide secrets in frontend code
- Browers are sandboxed, it has limited access to the operating system which is huge resctriction and not ideal for backend servers
- Frontend runs on the client side, if the backend runs on the client side the computing power is limited to the device used by the client (E.g. PC, phone, etc.)

## HTTP/HTTPS

- A `stateless`(don't store any informatio from the clients or server) protocol and follows a `client-server`(request is initiated always by the client) model.
- The states are usually handled by cookies, token, and other state management mechanisms.
- Default port of HTTP is 80 and 443 for HTTPS
- HTTPS has the same rules of HTTP with an added security layer

## Routing

## Serialization and Deserialization

## Authentication and Authorization

## Validations and Transformations

## Controllers, Services, Repositories, Middleware, and Request Context

## REST API Design

## Database

## Caching

## Task Queues and Background Jobs

## Full Text Search using Elasticsearch

## Error Handling and Building Fault Tolerant Systems

## Production-grade Configuration Management

## Logging, Monitoring and Observability

## Graceful Shutdown

Source:
**Backend from first principles**: https://www.youtube.com/watch?v=0Rwb4Xmlcwc&list=PLui3EUkuMTPgZcV0QhQrOcwMPcBCcd_Q1
