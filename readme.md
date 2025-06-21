# 📚 Library Management

A RESTful API built with **Node.js**, **Express**, and **MongoDB** using **TypeScript**, designed to manage books and borrowing records for a simple library system.

## 🧩 Introduction

This API allows for the creation, retrieval, update, and deletion (CRUD) of books and tracking of borrowed books with quantity summaries. Built with **Express v5**, it connects to MongoDB using **Mongoose** and is structured with modular routing and model files.

---

## 🚀 Features

* 📘 Add, view, update, and delete books
* 📈 Borrow book copies and track borrow records
* 🧮 Aggregate borrow statistics per book
* 🔍 Filter and sort books with query parameters
* ✅ Built using TypeScript with ESLint integration

---

## 🛠 Installation

```bash
# Clone the repository
git clone <your-repo-url>
cd l2-a3-node-express

# Install dependencies
npm install
```

---

## ▶️ Usage

To start the development server:

```bash
npm run dev
```

To build the TypeScript project:

```bash
npm run build
```

---

## 📡 API Endpoints

### 📘 Books

#### `POST /books`

Create a new book.

```json
{
  "title": "Book Title",
  "author": "Author Name",
  "genre": "Fiction",
  "copies": 5,
  "isbn": "123-456-789"
}
```

#### `GET /books`

Retrieve all books. Supports query parameters:

* `filter` — genre
* `sortBy` — field name (e.g., `title`)
* `sort` — `asc` or `desc`
* `limit` — number of results

#### `GET /books/:bookId`

Retrieve a single book by ID.

#### `PUT /books/:bookId`

Update book details. If `copies > 0`, `available` is automatically set to `true`.

#### `DELETE /books/:bookId`

Delete a book by ID.

---

### 🔄 Borrow

#### `POST /borrow`

Borrow book copies.

```json
{
  "book": "bookId",
  "quantity": 2
}
```

Checks for available copies before allowing borrowing.

#### `GET /borrow`

Returns aggregated borrow data:

```json
[
  {
    "book": {
      "title": "Example Title",
      "isbn": "123-456-789"
    },
    "totalQuantity": 5
  }
]
```

---

## 📦 Dependencies

### Runtime

* **express** `^5.1.0`
* **mongoose** `^8.16.0`

### Dev

* **typescript** `^5.8.3`
* **ts-node-dev** `^2.0.0`
* **@types/express** `^5.0.3`
* **@eslint/js**, **typescript-eslint**

---

## 📜 Development Scripts

```bash
npm run dev     # Run in development with ts-node-dev
npm run build   # Compile TypeScript to JS
```
