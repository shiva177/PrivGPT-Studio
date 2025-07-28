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

1. **`DBURL (Mongo URL)`**

   - **Description:** The MongoDB connection string.
   - **How to Obtain:**

     1. Go to MongoDB Atlas and sign up or log in.
     2. Create a new cluster if you don't have one already.
     3. Navigate to Database Access and create a new database user with the appropriate permissions (e.g., readWrite).
     4. In the Network Access tab, allow connections from your IP address (or use 0.0.0.0/0 for all IPs for testing).
     5. Go to Clusters, click on Connect, and select Connect your application.
     6. Copy the connection string provided (it should look like `mongodb+srv://<username>: <password>@cluster0.mongodb.net/test?retryWrites=true&w=majority`).
     7. Replace <username> and <password> with the credentials you created in step 3.
     8. Set the DBURL variable in your env file with the full MongoDB Atlas URL.

     For a local MongoDB setup, you can install MongoDB locally and use
     `mongodb://localhost:27017/your-database-name`

2. **`GEMINI_API_KEY`**
- **Description:** The API key used to authenticate requests to Google's Gemini API (also known as Google AI Studio or Generative AI API).

- **How to Obtain:**

   1. Visit Google AI Studio and log in with your Google account.
   2. Click on the "Get API Key" or navigate to Google Cloud Console.
   3. Create a new project or use an existing one.
   4. Enable the "Generative Language API" from the API Library.
   5. Search for “Generative Language API”.
   6. Go to APIs & Services > Credentials from the left sidebar.
   7. Click “+ Create Credentials” → select API Key.
   8. Copy the newly generated key.

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