
# 🐳 Containerized Microservice Architecture

This project demonstrates a simple containerized microservice architecture using Docker and Docker Compose. It consists of multiple services that communicate with each other to perform user registration and information retrieval, along with caching support.

---

## 🚀 Project Structure

```

containerized-microservice/
├── docker-compose.yml
├── register/           # User registration service (port 5000)
│   └── app.py
├── userinfo/           # User info service with caching (port 5001)
│   └── app.py
└── redis/              # Redis for caching

````

---

## 🛠️ Prerequisites

- Docker installed: [Get Docker](https://docs.docker.com/get-docker/)
- Docker Compose installed

---

## ⚙️ Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/piyushbankhede/containerized-microservice.git
cd containerized-microservice
````

### 2️⃣ Launch the Services

```bash
docker-compose up --build -d
```

This command will:

* Build the images for the microservices
* Start the following containers:

  * `register` (Flask app on port `5000`)
  * `userinfo` (Flask app on port `5001`)
  * `redis` (on default port `6379`)

---

## 📬 Usage

### ✅ Register a User

```bash
curl -X POST -H "Content-type:application/json" http://13.232.22.100:5000/register -d '{"name":"joy", "email":"joy123@gmail.com"}'
```

**Response:**

```json
{"message":"User registered"}
```

---

### 🔎 Get User Info

```bash
curl http://13.232.22.100:5001/user/joy
```

**First call (not cached):**

```json
{"cached": false, "info": "User info for joy", "name": "joy"}
```

**Subsequent calls (cached):**

```json
{"cached": true, "info": "User info for joy", "name": "joy"}
```

---

## 📦 Microservice Responsibilities

| Service    | Port | Description                           |
| ---------- | ---- | ------------------------------------- |
| `register` | 5000 | Registers a user with name and email  |
| `userinfo` | 5001 | Fetches user info, caches using Redis |
| `redis`    | 6379 | In-memory data store for caching      |

---

## 🧹 Stopping the Services

```bash
docker-compose down
```

---

## ✍️ Author

**Vaibhavi Sugandhi**
GitHub: [@piyushbankhede](https://github.com/piyushbankhede)

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

```


