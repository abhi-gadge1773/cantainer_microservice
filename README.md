# 🧱 Containerized Microservices Project with Docker & Python

This project demonstrates how to build, containerize, and run a simple **Python-based microservice** using **Docker**. The goal is to illustrate a modular architecture where services are deployed as isolated containers.

---

## 📌 Project Objective

✅ Build a Python microservice using Flask  
✅ Containerize it using Docker  
✅ Expose endpoints for HTTP interaction  
✅ Run and test the service in isolated environments  

---

## 🚀 Tech Stack

| Tool     | Purpose                        |
|----------|--------------------------------|
| Python   | Core programming language      |
| Flask    | Micro web framework            |
| Docker   | Containerization & packaging   |
| GitHub   | Version control & collaboration |

---

## 🗂 Project Structure

```

.
├── app/
│   ├── main.py
│   └── requirements.txt
├── Dockerfile
└── README.md

````

- `main.py`: Contains the Flask microservice logic  
- `Dockerfile`: Instructions to build the container  
- `requirements.txt`: Python package dependencies  

---

## 🐳 Dockerfile Example

```dockerfile
# Use Python base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy files
COPY app/ .

# Install dependencies
RUN pip install -r requirements.txt

# Expose port
EXPOSE 5000

# Start Flask service
CMD ["python", "main.py"]
````

---

## 🔧 How to Build and Run

### 1. Clone the Repository

```bash
git clone https://github.com/abhi-gadge1773/cantainer_microservice.git
cd cantainer_microservice
```

### 2. Build Docker Image

```bash
docker build -t python-microservice .
```

### 3. Run the Container

```bash
docker run -d -p 5000:5000 python-microservice
```

### 4. Test the API

Visit: [http://localhost:5000](http://localhost:5000)

Or use `curl`:

```bash
curl http://localhost:5000
```

---

## ✅ Example Output

```json
{
  "message": "Hello from the Python Microservice!"
}
```

---

## 🔁 Extend the Microservice

You can extend the service by adding more endpoints inside `main.py`, e.g.:

```python
@app.route("/health")
def health_check():
    return jsonify({"status": "UP"}), 200
```

---

## 📦 requirements.txt

```text
Flask==2.1.0
```

---

## 📌 GitHub Repository

👉 [Container Microservice Repository](https://github.com/abhi-gadge1773/cantainer_microservice)

---

## 👨‍💻 Author

**Abhijeet Gadge**
📧 [abhijeetgadge100@gmail.com](mailto:abhijeetgadge100@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/abhijeetgadge/)
🔗 [GitHub](https://github.com/abhi-gadge1773)

---

## ⭐ Support

If you found this helpful, consider ⭐ starring the repository and sharing it with your network!

```



