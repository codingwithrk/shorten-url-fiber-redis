# Shorten URL

Shorten URL is a simple web application that allows users to shorten long URLs. It is built using GO and Redis.

## Features

- Shorten long URLs
- Redirect to original URL
- Have a rate limiter
- Store shortened URLs in Redis

## Requirements

- Go 1.18 or later
- Redis
- Docker (optional, for running Redis in a container)

## Installation

1. Clone the Repository

```bash
https://github.com/codingwithrk/shorten-url-fiber-redis.git
```

2. Change to the project directory

```bash
cd shorten-url-fiber-redis
```

3. Build the application using docker (If you have docker installed)

```bash
docker-compose up -d
```

4. If you don't have docker installed, you can run Redis locally. Make sure Redis is running on port 6379.

5. Install the required Go packages

```bash
go mod tidy
```

6. Run the application (Change the directory to api)

```bash
go run main.go
```

7. Open postman and test the API

### Base URL

- http://localhost:3000

- POST /api/v1

  - Request Body:
    ```json
    {
      "url": "https://example.com"
    }
    ```
  - Response:
    ```json
    {
      "url": "https://example.com",
      "short": "localhost:3000/abc123",
      "expiry": 24,
      "rate_limit": 9,
      "rate_limit_reset": 30
    }
    ```

## Made by

[CodingwithRK](https://codingwithrk.com)
