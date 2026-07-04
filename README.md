# 💻 Artwork App Multi-Repo Workspace

Welcome to the centralized development environment for the Artwork Platform. This workspace orchestrates the full-stack ecosystem by linking your frontend, backend, mobile application, and local infrastructure dependencies into a single, unified sandbox environment using **VS Code Dev Containers** and **Docker Compose**.

## 🏗️ Workspace Architecture
When initialized, the environment mounts and exposes four core sub-repositories:
*   `⚙️ Environment Configuration` (This configuration root)
*   `🚀 Backend (NestJS)` (Located at `../be-nestjs`)
*   `🌐 Web Frontend (Next.js)` (Located at `../fe-nextjs`)
*   `📱 Mobile App (React Native)` (Located at `../fe-react-native`)

---

## 🛠️ Prerequisites
Before starting, ensure your host machine has the following tools installed and running:
1.  **Docker Desktop** (Ensure the engine is active)
2.  **Visual Studio Code**
3.  **Dev Containers Extension** by Microsoft (Extension ID: `ms-vscode-remote.remote-containers`)

---

## 🚀 How to Open the Workspace (Step-by-Step)

> ⚠️ **IMPORTANT:** Because of how VS Code initializes multi-root folder maps inside Docker volumes, opening the `.code-workspace` file directly from your host machine will cause a blank window initialization trap. You **must** follow the two-step boot sequence below.

### Step 1: Initialize the Container Infrastructure First
1. Launch a completely fresh, empty window of **VS Code**.
2. Go to the top menu and select **File > Open Folder...**
3. Select only the **`development-environment`** repository folder directly.
4. Once the project files load locally, open the VS Code Command Palette (`Cmd + Shift + P` on macOS or `Ctrl + Shift + P` on Windows/Linux).
5. Type and select: **`Dev Containers: Reopen in Container`**.
6. Wait for Docker to pull the custom Ubuntu-Node image layers, configure your private internal network mesh, and complete the automatic background configuration scripts.

### Step 2: Load the Multi-Root Sidebar Map
Once your integrated terminal prompt shifts to `vscode ➜ /workspace/development-environment`, your core container environment is running smoothly. Now you can bring in your sibling code repositories:

1. Inside that same active container window, go to the top menu and select **File > Open Workspace from File...**
2. Select the **`artwork-app.code-workspace`** file.
3. The VS Code interface will refresh immediately.

Your sidebar file tree explorer will now render all four distinct repository modules simultaneously, running with full read/write synchronization inside your live container environment.

---

## ⚙️ Orchestrating Your Services (Launch Tasks)

You do not need to manually change directories (`cd`) or spin up multiple terminal splits to run your microservices. The workspace includes an automated compilation task layout.

### How to boot the full-stack platform:
1. Press `Cmd + Shift + P` (or `Ctrl + Shift + P`) to open the Command Palette.
2. Type and select: **`Tasks: Run Task`**.
3. Choose: **`🚀 Launch Full Stack Platform`**.

VS Code will instantly spin up three distinct, labeled background terminal panel tabs side-by-side inside your container workspace dashboard:
*   `NestJS API` — Booting your backend logic server
*   `Next.js Web` — Compiling your web frontend routing layers
*   `Metro Bundler` — Launching your React Native packaging hub on port `8081`

---

## 🛜 Local Infrastructure Endpoints

Once your environment is active, the following local services are automatically forwarded from the container network mesh directly to your host machine's browser interface:

| Port | Service Component | Internal Routing Hostname |
| :--- | :--- | :--- |
| `3000` | Next.js Web Frontend | `http://localhost:3000` |
| `3001` | NestJS Backend API Engine | `http://localhost:3001` |
| `5432` | Local PostgreSQL Database | Use hostname `postgres` inside code |
| `8081` | React Native Metro Bundler | `http://localhost:8081` |
| `9000` | MinIO Object Storage S3 API | Use hostname `minio` inside code |
| `9001` | MinIO Admin Web Console Dashboard | `http://localhost:9001` |

