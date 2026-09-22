# URL Shortener (Go)

A simple URL shortener built with Go's standard library only (no external frameworks or databases).

## Live Demo
https://url-shortener-s12z.onrender.com

## Features
- POST /shorten — accepts a JSON body `{"url": "..."}`, returns a short code and short URL
- GET /{code} — redirects to the original URL

## Tech Stack
- Go standard library only: net/http, encoding/json
- In-memory storage (map) — no database
- Deployed on Render

## Example Usage

Create a short URL:
​```bash
curl -X POST https://url-shortener-s12z.onrender.com/shorten \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com"}'
​```

Response:
​```json
{"short_url":"https://url-shortener-s12z.onrender.com/abc123","code":"abc123"}
​```

## Note
Data is stored in memory, so it resets when the server restarts (e.g. after Render's free-tier idle timeout).