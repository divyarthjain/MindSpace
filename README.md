
# MindSpace


![MindSpace Logo](https://raw.githubusercontent.com/divyarthjain/MindSpace/main/assets/logo.png)

*Your open-source companion for mental wellness*

[![GitHub last commit](https://img.shields.io/github/last-commit/divyarthjain/MindSpace?color=red)](https://github.com/divyarthjain/MindSpace/commits/main)
[![Discord](https://img.shields.io/badge/Discord-MindSpace-purple?logo=discord&logoColor=white)](https://discord.gg/AhGmsrzfUx)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)


## 🧠 About MindSpace

MindSpace is an open-source mental health tracker that provides a suite of tools to help you monitor, understand, and improve your emotional wellbeing. Built with a modern tech stack including Open WebUI, Ollama, n8n, PostgreSQL, and Qdrant.

---

## ✨ Key Features

### 📔 Personal Journal
- 🖊️ **Private writing space** for your thoughts and reflections
- 🌈 Reduce stress and gain clarity about your emotions
- 🏷️ Organize entries with customizable mood tags

### 😀 Emoji Mood Tracking
- ⚡ Log your daily mood quickly with intuitive emoji selections
- 🌱 Develop greater emotional awareness through consistent tracking
- ⏱️ Simple review system to monitor emotional patterns

### 📈 Visual Mood Analytics
- 🔍 Discover personal trends, patterns, and emotional triggers
- 🎢 Identify mood cycles and significant emotional pivot points
- 🏆 Track your progress toward greater emotional stability

### 📝 Mental Health Assessments
- 🌐 Evidence-based questionnaires for self-assessment
- 🤔 Measure stress, anxiety, depression, and other mental health factors
- 🚀 Receive personalized feedback and helpful resources

### 🤖 AI Companion
- 💬 Express yourself freely in a judgment-free environment
- 🤐 Safe space for venting and processing difficult emotions
- 🤗 24/7 AI-powered support that adapts to your needs

### 📊 Progress Dashboard
- 🏅 Comprehensive view of mood trends, journal entries, and achievements
- 🌟 Visualize your personal growth journey to stay motivated
- 🎯 Set and track mental wellness goals with actionable insights

---

## 🛠️ Technical Features

<table>
  <tr>
    <td width="33%">
      <h4>⚙️ Effortless Setup</h4>
      <p>Deploy via Docker or Kubernetes with support for both <code>:ollama</code> and <code>:cuda</code> images</p>
    </td>
    <td width="33%">
      <h4>🔗 AI Integration</h4>
      <p>Connect to Ollama, OpenAI, LMStudio, GroqCloud, Mistral, OpenRouter, and more</p>
    </td>
    <td width="33%">
      <h4>🔒 Secure Access Control</h4>
      <p>Fine-tune user permissions with granular role management</p>
    </td>
  </tr>
  <tr>
    <td width="33%">
      <h4>📱 Responsive Design</h4>
      <p>Optimized experience across desktop, laptop, and mobile devices</p>
    </td>
    <td width="33%">
      <h4>📱 PWA Support</h4>
      <p>Install as a native app with offline capabilities</p>
    </td>
    <td width="33%">
      <h4>🎤📹 Multimedia Support</h4>
      <p>Voice capabilities for more dynamic interactions</p>
    </td>
  </tr>
</table>

---

## 📊 System Architecture

MindSpace integrates several powerful components to create a comprehensive mental health tracking solution:

- **Front-end**: Open WebUI provides an intuitive user interface
- **AI Engine**: Ollama powers the AI companion and analytics
- **Automation**: n8n handles workflows, notifications and integrations
- **Database**: PostgreSQL stores user data, journal entries and assessments
- **Vector Storage**: Qdrant enables semantic search and AI memory

---

## 🚀 Installation Guide

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your system
- Basic familiarity with command line operations

### Step 1: Clone the Repository

```bash
git clone https://github.com/divyarthjain/MindSpace
cd MindSpace
```

### Step 2: Install Open WebUI with Ollama

Navigate to the Open WebUI directory:

```bash
cd open-webui
```

Choose the appropriate installation option:

#### With GPU Support
```bash
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama \
  -v open-webui:/app/backend/data --name open-webui --restart always \
  ghcr.io/open-webui/open-webui:ollama
```

#### For CPU Only
```bash
docker run -d -p 3000:8080 -v ollama:/root/.ollama \
  -v open-webui:/app/backend/data --name open-webui --restart always \
  ghcr.io/open-webui/open-webui:ollama
```

After installation, access Open WebUI at [http://localhost:3000](http://localhost:3000)

### Step 3: Setup n8n with PostgreSQL

Navigate to the n8n directory:

```bash
cd ../n8n/docker-compose/withPostgres
```

> **⚠️ IMPORTANT:** Before proceeding, update the default credentials in the `.env` file!

Start n8n with PostgreSQL:

```bash
docker compose up -d
```

To stop the service:

```bash
docker compose stop
```

### Step 4: Configure Qdrant

Pull the Qdrant image:

```bash
docker pull qdrant/qdrant
```

Start Qdrant (customize the storage path as needed):

```bash
docker run -p 6333:6333 \
  -v $(pwd)/qdrant-data:/qdrant/storage \
  qdrant/qdrant
```

Verify the installation by visiting [http://localhost:6333](http://localhost:6333)

---

## 🤝 Contributing

We welcome contributions from developers, designers, mental health professionals, and anyone passionate about mental wellness. See our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📜 License

MindSpace is released under the MIT License. See the [LICENSE](LICENSE) file for details.

## 📞 Support

Join our [Discord community](https://discord.gg/AhGmsrzfUx) for questions, discussions, and support.

---

🧠 MindSpace: Take care of your mind, one day at a time
