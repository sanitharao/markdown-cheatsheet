# 📘 BookTrack API Documentation (Sample)

## Overview
The BookTrack API allows users to manage their personal library and track reading progress across multiple books. This RESTful API supports CRUD operations on books, shelves, and reading sessions.

## Base URL
```
https://api.booktrack.io/v1
```

---

## 🔐 Authentication
All requests must include an API key in the header.

**Header Example:**
```
Authorization: Bearer YOUR_API_KEY
```

---

## 📚 Endpoints

### 1. Get All Books
**GET** `/books`

**Description:** Retrieve a list of all books in the user’s library.

**Query Parameters:**

| Parameter | Type   | Description       |
|-----------|--------|-------------------|
| genre     | string | Filter by genre   |
| limit     | int    | Limit the results |

**Response:**
```json
[
  {
    "id": "123",
    "title": "Atomic Habits",
    "author": "James Clear",
    "status": "Reading"
  }
]
```

---

### 2. Add a New Book
**POST** `/books`

**Request Body:**
```json
{
  "title": "Deep Work",
  "author": "Cal Newport",
  "genre": "Productivity"
}
```

**Response:**
```json
{
  "message": "Book added successfully",
  "id": "456"
}
```

---

### 3. Update Reading Progress
**PATCH** `/books/{book_id}/progress`

**Request Body:**
```json
{
  "current_page": 120
}
```

**Response:**
```json
{
  "message": "Progress updated",
  "current_page": 120
}
```

---

## 🧪 Error Handling

| Status Code | Message              |
|-------------|----------------------|
| 401         | Unauthorized         |
| 404         | Book not found       |
| 500         | Internal Server Error|

---

## 🔧 Example Use Case

**Scenario:** A user wants to add a new book and start tracking progress.

1. `POST /books` to add the book.
2. `PATCH /books/{book_id}/progress` to update current page.

---
