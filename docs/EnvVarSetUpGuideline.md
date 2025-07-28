# 🛠️ Environment Variable Setup Guideline

This document will guide you through setting up the necessary environment variables required to run the **PrivGPT-Studio** project in your local development environment.

---

## 📂 Environment Variables

Environment variables are used to securely manage sensitive configuration data such as API keys and database URLs. This project uses `.env` files for both frontend (`client`) and backend (`server`) setups.

### 📍 Locations:
- `client/.env`
- `server/.env`

You will find example files:
- `client/.env.example`
- `server/.env.example`

---

## 🧩 How to Setup

To get started with local development:

```bash
# 1. Clone the repository
git clone https://github.com/<your-repo>/PrivGPT-Studio.git
cd PrivGPT-Studio

# 2. Create your .env files using the example files
cd client
cp .env.example .env   # For Linux/macOS. Use `copy .env.example .env` on Windows

cd ../server
cp .env.example .env   # For Linux/macOS. Use `copy .env.example .env` on Windows
```

3. Fill in the required values in both .env files by referring to the details below.


Backend(server/.env)
```bash
MONGODB_URL=mongodb://localhost:27017/privgpt
GEMINI_API_KEY=your_gemini_api_key_here

```
Frontend(client/.env)
```bash
NEXT_PUBLIC_BACKEND_URL=http://localhost:5000
```

Optional Setup (Local LLMs using Ollama)

If you are using Ollama to run LLMs locally:

```bash
ollama serve
ollama pull llama3
```


⚠️ Important Notes
Never commit .env files to version control.

Keep your .env values secret and secure.

If you're facing issues with MongoDB access or Gemini keys, double-check values and permissions.

## 🔐 Required Environment Variables

### 🔧 Backend (`server/.env`)

```env
MONGODB_URL=mongodb://localhost:27017/privgpt
GEMINI_API_KEY=your_gemini_api_key_here

```
### Frontend (`client/.env`)

```env
NEXT_PUBLIC_BACKEND_URL=http://localhost:5000

```
### Optional Setup (Local LLMs using Ollama)
```bash
ollama serve
ollama pull llama3

```
### Important Notes
❌ Never commit .env files to version control.

🔒 Keep your .env values secret and secure.

✅ If you're facing issues with MongoDB access or Gemini keys, double-check your values, spelling, and permissions.