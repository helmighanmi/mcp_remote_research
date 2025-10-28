# 🧠 MCP Research Server

A lightweight **research assistant server** built using **FastMCP** that searches for academic papers on **arXiv**, extracts summaries and metadata, and serves them as **MCP tools** and **resources** for LLM-based workflows.
## Acknowledgement
This work is carried out based on the learning from courses of Antropic and deeplearning.ai
---

## 🚀 Features

- 🔍 Search for papers from **arXiv.org**
- 📁 Save and organize paper metadata in local folders
- 📜 Extract detailed paper information
- 🧰 Expose tools and resources for use in **MCP-based AI workflows**
- 🌐 Deploy easily to **Render.com** or **Docker**

---

## 🧩 Project Structure

```
.
├── Dockerfile
├── README.md
├── main.py
├── pyproject.toml
├── requirement.txt
├── research_server.py
├── runtime.txt
├── uv.lock
└── .gitignore
```

---

## 🧠 How It Works

The server uses the [`FastMCP`](https://github.com/modelcontextprotocol/fastmcp) library to expose **MCP tools** and **resources**.

### Key Tools
| Tool | Description |
|------|--------------|
| `search_papers(topic, max_results)` | Searches arXiv for research papers related to a topic |
| `extract_info(paper_id)` | Retrieves metadata for a specific paper |
| `get_available_folders()` | Lists all saved research topics |
| `get_topic_papers(topic)` | Returns all paper summaries for a topic |
| `generate_search_prompt(topic, num_papers)` | Generates a structured research prompt for LLMs |

---

## 🧰 Installation (Local)

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2️⃣ Create a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirement.txt
```

### 4️⃣ Run the Server
```bash
python research_server.py
```

Server will start at:
```
http://localhost:8001
```

---

## 🐳 Run with Docker

### 1️⃣ Build the Image
```bash
docker build -t mcp-research-server .
```

### 2️⃣ Run the Container
```bash
docker run -p 8001:8001 mcp-research-server
```

Then visit:
```
http://localhost:8001
```

---

## ☁️ Deploy to Render.com

### 1️⃣ Go to Render.com
Create a free account and open:
👉 [https://dashboard.render.com/web/new?newUser=true](https://dashboard.render.com/web/new?newUser=true)

### 2️⃣ Create a New Web Service
- Connect your **GitHub repository**
- Choose your repo name
- Select **Python 3.12**
- Set the start command:
  ```
  python research_server.py
  ```
- Deploy 🚀

### 3️⃣ Example Live Server
Example endpoint (if deployed):
```
https://mcp-remote-research-f6yh.onrender.com
```

---

## 🧠 MCP Integration

This project is designed to be used with **Model Context Protocol (MCP)** clients such as Claude or other AI tools.

You can connect to this server to provide live research capabilities to your AI assistant.

Example usage:
```python
from mcp.client import MCPClient

client = MCPClient("http://localhost:8001")
papers = client.tools.search_papers("quantum computing", max_results=3)
print(papers)
```

---

## 🧾 Requirements

- Python **3.12+**
- `fastmcp`
- `arxiv`
- `uv` (optional for fast dependency management)
- Docker (optional for container deployment)

---

## 🧪 Testing the Repo

To test the deployment manually:

1. Visit [Render.com Web Services](https://dashboard.render.com/web/new?newUser=true)
2. Connect your GitHub repo
3. Deploy with default configuration
4. After successful deployment, test your endpoint:
   ```
   https://your-service-name.onrender.com
   ```

Objective: to demonstrate **MCP tool integration** for autonomous AI research agents.

---

## 👨‍💻 Author

**Helmi Ghanmi**  
Research Engineer in Generative AI  
[GitHub](https://github.com/helmighanmi)

Copyright : **Antropic and deeplearning.ai**
