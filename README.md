# 💻 Artwork Platform Unified Workspace

Welcome to the centralized development environment for the Artwork Platform. This workspace orchestrates our full-stack ecosystem by linking your frontend, backend, mobile application, and local infrastructure dependencies into a single, unified sandbox environment using **VS Code Dev Containers** and **Docker Compose**.

By opening the parent container root folder directly, all files across your microservices remain fully visible, writable, and perfectly synchronized in real-time.

---

## 🏗️ Workspace Directory Layout
Our development framework sits inside a single parent container directory structured as follows on your local Mac:

```text
📁 artworkapp/                   <-- OPEN THIS PARENT DIRECTORY IN VS CODE
├── 🔗 .devcontainer/            --> development-environment/.devcontainer/
├── 🔗 .vscode/                  --> development-environment/.vscode/
├── 📁 be-nestjs/                --> (Independent Git Repository)
├── 📁 development-environment/  --> (True home of infrastructure configuration files)
├── 📁 fe-nextjs/                --> (Independent Git Repository)
└── 📁 fe-react-native/          --> (Independent Git Repository)
```

---

## 🛠️ Prerequisites
Before initializing the environment, ensure your host computer has the following tools installed and active:
1.  **Docker Desktop** (Ensure the engine is running)
2.  **Visual Studio Code**
3.  **Dev Containers Extension** by Microsoft (Extension ID: `ms-vscode-remote.remote-containers`)

---

## 🚀 Initial Machine Setup (First-Time Onboarding Only)

Because our global environments (`.devcontainer` and `.vscode`) are managed inside the `development-environment` repository, you must create relative shortcuts (symbolic links) so VS Code and Docker can trace them from the project root.

Open your local Mac terminal application and run this quick initialization sequence:

```bash
# 1. Navigate into your workspace root folder
cd /Users/changhyunlee/code/artworkapp

# 2. Build the live portal link for your container configurations
ln -s development-environment/.devcontainer .devcontainer

# 3. Build the live portal link for your individual workspace tools
mkdir -p .vscode
ln -s ../development-environment/.vscode/launch.json .vscode/launch.json
ln -s ../development-environment/.vscode/tasks.json .vscode/tasks.json
```

---

## 🏁 How to Open the Dev Container

1. Launch **VS Code**.
2. Go to the top menu bar and select **File > Open Folder...**
3. Select the absolute top-level parent folder: `/Users/changhyunlee/code/artworkapp`.
4. Open the VS Code Command Palette (**`Cmd + Shift + P`** on macOS or `Ctrl + Shift + P` on Windows/Linux).
5. Type and select: **`Dev Containers: Reopen in Container`**.

The container engine will build your environment in a single phase. When the window finishes loading, your sidebar file explorer will render your full multi-repo file trees instantly with absolute read/write capabilities.

---

## ⚙️ Orchestrating Your Services (Launch Automation)

You do not need to manually change directories (`cd`) or split multiple terminal screens to run your microservices. The workspace features built-in orchestration macros.

### How to boot the full-stack platform:
1. Ensure your Dev Container environment has completed its boot sequence.
2. Press **`Cmd + Shift + B`** simultaneously on your Mac keyboard.
   *(Alternative: Open the Command Palette -> select **Tasks: Run Task** -> click **🚀 Launch Full Stack Platform**)*

VS Code will automatically open three side-by-side terminal tabs inside a single consolidated panel dashboard:
*   `NestJS API` — Booting your backend endpoints on `http://localhost:3001`
*   `Next.js Web` — Compiling your web frontend interface layers on `http://localhost:3000`
*   `Metro Bundler` — Launching your React Native mobile hub on port `8081`

---

## 🛜 Local Infrastructure Endpoints

The following local background services are automatically forwarded from the container network mesh directly to your host machine's browser interface:

| Port | Service Component | Internal Routing Hostname |
| :--- | :--- | :--- |
| `3000` | Next.js Web Frontend | `http://localhost:3000` |
| `3001` | NestJS Backend API Engine | `http://localhost:3001` |
| `5432` | Local PostgreSQL Database | Use hostname `postgres` inside code |
| `8081` | React Native Metro Bundler | `http://localhost:8081` |
| `9000` | MinIO Object Storage S3 API | Use hostname `minio` inside code |
| `9001` | MinIO Admin Web Console Dashboard | `http://localhost:9001` |
