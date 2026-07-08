# Subscription API Contract

## Overview
The MVP exposes a minimal API for managing subscriptions in memory.

## Endpoints

### GET /api/subscriptions
Returns the current list of subscriptions.

**Response**
```json
[
  {
    "id": "1",
    "url": "https://example.com/feed.xml"
  }
]
```

### POST /api/subscriptions
Adds a new subscription to the current list.

**Request Body**
```json
{
  "url": "https://example.com/feed.xml"
}
```

**Success Response**
- Status: 201 Created
- Body: the created subscription object

**Error Responses**
- Status: 400 Bad Request when the URL is empty
- Status: 409 Conflict when the same URL is already present in the current session
