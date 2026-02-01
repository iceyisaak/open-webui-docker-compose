# Open WebUI Docker Deployment

Repo: 

This repository contains a simple **Docker Compose** configuration to deploy **Open WebUI**, a user-friendly, feature-rich interface for interacting with LLMs. This specific setup is pre-configured to communicate with a local **Ollama** instance running on your host machine.

## 🚀 Quick Start

### Prerequisites

* **Docker** and **Docker Compose** installed.
* **Ollama** installed and running on your host machine (outside of Docker).

### Deployment

1. Clone this repository or copy the `docker-compose.yml` file.
2. Navigate to the directory in your terminal.
3. Run the following command:
```bash
docker compose up -d

```


4. Open your browser and navigate to: `http://localhost:11430`

---

## ⚙️ Configuration Details

This setup uses the following key configurations:

| Feature | Detail |
| --- | --- |
| **Port** | Accessible at `11430` (mapped from container port `8080`). |
| **Backend** | Connects to Ollama via `host.docker.internal`. |
| **Persistence** | Uses a named volume `open-webui` to save your chats and settings. |
| **Restart Policy** | `unless-stopped` (starts automatically on boot). |

### Connecting to Ollama

The environment variable `OLLAMA_BASE_URL` is set to `http://host.docker.internal:11434`.

> **Note for Linux Users:** If you encounter connection issues, ensure your Ollama service is listening on all interfaces by setting `OLLAMA_HOST=0.0.0.0` in your host's environment variables.

---

## 🛠️ Maintenance

**To stop the service:**

```bash
docker compose down

```

**To update to the latest version:**

```bash
docker compose pull
docker compose up -d

```

**To view logs:**

```bash
docker compose logs -f

```

---