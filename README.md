# 🚀 Node.js Express API with CI/CD, Docker & Kubernetes

A simple Express.js API designed for beginners to learn how to:

- Develop a backend API with Node.js + Express
- Containerize the app using Docker
- Automate builds and tests with GitHub Actions CI/CD
- Deploy to Kubernetes with YAML manifests (works on Minikube or cloud)

---

## 📦 Tech Stack

| Tool / Platform   | Purpose                            |
|-------------------|-------------------------------------|
| Node.js + Express | Backend API development             |
| Docker            | Containerize the application        |
| GitHub Actions    | CI/CD pipeline for automation       |
| Kubernetes (k8s)  | App deployment and service management |

---

## 🗂 Project Structure

```

simple-node-api/
├── .github/
│   └── workflows/
│       └── ci-cd.yml         # GitHub Actions CI/CD workflow
├── k8s/
│   ├── deployment.yaml       # Kubernetes Deployment config
│   └── service.yaml          # Kubernetes Service config
├── src/
│   └── index.js              # Express app source
├── Dockerfile                # Docker build config
├── .dockerignore             # Ignore files from Docker build
├── package.json              # NPM metadata and scripts
└── README.md                 # Project documentation

````

---

## 🚀 Getting Started Locally

### 1. Clone the Project
```bash
git clone https://github.com/your-username/simple-node-api.git
cd simple-node-api
````

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the App

```bash
npm start  # App runs on http://localhost:3000
```

---

## 🐳 Run with Docker

### Build the Docker Image

```bash
docker build -t simple-node-api .  # Build image locally
```

### Run the Container

```bash
docker run -p 3000:3000 simple-node-api  # Run on localhost:3000
```

---

## 🤖 GitHub Actions CI/CD

The CI/CD pipeline is defined in `.github/workflows/ci-cd.yml`

### Trigger:

* Automatically runs on `push` to `main`

### Actions:

1. Checkout the code
2. Setup Node.js environment
3. Install dependencies
4. Run tests (`npm test`)
5. Build Docker image (locally in GitHub runner)

---

## ☸️ Deploy to Kubernetes

### Requirements:

* Docker image pushed to Docker Hub
* Kubernetes cluster (e.g. Minikube or cloud)
* `kubectl` CLI installed

### Build & Push Docker Image

```bash
docker build -t your-dockerhub/simple-node-api .
docker push your-dockerhub/simple-node-api
```

### Apply K8s Manifests

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### Access the App

* For Minikube:

```bash
minikube service simple-node-service
```

* For cloud:

```bash
kubectl get svc  # Get external LoadBalancer IP
```

---

## 🧪 Test the App

```bash
curl http://localhost:3000
# Output:
🚀 Hello from GitHub Actions CI/CD!
```

---

## 🔧 What's Next?

* Add real unit tests using Jest
* Add health/liveness probes in Kubernetes
* Use Helm for managing K8s charts
* Add auto-deployment to a staging/production environment

---

## 👨‍💻 Author

**Nur Ariff**
GitHub: [@your-username](https://github.com/your-username)

---

## 📄 License

MIT License – free to use, modify, and share.

```

---

Would you like me to:
- Zip the full project folder?
- Add liveness/readiness probes?
- Add Helm chart template?

Let me know, we can take this all the way to a real-world deployment 🚢
```
