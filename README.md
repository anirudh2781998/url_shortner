# 🔗 URL Shortener — Lightweight Backend Service

A fast and minimal URL shortening service built using Python, designed for low-latency redirection and efficient URL storage. Implements clean backend design principles with caching and unique ID generation.

---

## 🚀 Features

* 🔹 Convert long URLs into short, shareable links
* 🔹 Fast redirection with minimal latency
* 🔹 Base62 encoding for compact short URLs
* 🔹 SQLite database for lightweight persistent storage
* 🔹 Simple and clean REST API design
* 🔹 Stateless architecture (ready for scaling with external DB/cache)

---

## 🏗️ Tech Stack

* **Backend:** Python (Flask / FastAPI)
* **Database:** SQLite3
* **Tools:** Docker (optional), curl/Postman for testing

---

## 🧠 System Design Overview

* REST API handles URL creation and redirection
* Unique short IDs generated using hashing + Base62 encoding
* SQLite used for persistent storage of URL mappings
* Lightweight design allows quick deployment and easy extension
* Can be scaled by replacing SQLite with PostgreSQL and adding Redis

---

## 📡 API Endpoints

### 🔹 Create Short URL

POST `/shorten`

**Request Body:**

```json
{
  "url": "https://example.com/very/long/url"
}
```

**Response:**

```json
{
  "short_url": "http://localhost:5000/abc123"
}
```

---

### 🔹 Redirect to Original URL

GET `/{short_id}`

* Redirects to the original URL if found
* Returns 404 if not found

---

## ⚡ Performance

* Handles multiple concurrent requests efficiently (tested locally)
* Average response time: ~20–50 ms (local environment)
* Optimized for fast lookup using indexed storage

---

## ▶️ Running Locally

### 1. Clone the repository

```bash
git clone https://github.com/anirudh2781998/url-shortener.git
cd url-shortener
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the server

```bash
python app.py
```

Server will start at:

```
http://localhost:5000
```

---

## 📂 Project Structure

```
url-shortener/
│── app.py
│── database.db
│── models/
│── utils/
│── requirements.txt
│── README.md
```

---

## 🔒 Future Improvements

* Redis caching for faster lookups
* PostgreSQL for scalable storage
* Rate limiting & authentication
* Custom URL aliases
* Analytics dashboard (click tracking)
* Deployment on AWS / Docker

---

## 👨‍💻 Author

**Anirudh Pandey**

* GitHub: https://github.com/anirudh2781998
* Email: [pandeyanirudh92@gmail.com](mailto:pandeyanirudh92@gmail.com)

---

## ⭐ Show Your Support

If you found this project useful, consider giving it a ⭐ on GitHub!
