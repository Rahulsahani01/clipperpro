# Quick Guide: Google AI Studio Setup for SupoClip

This guide walks you through getting a **100% free Google Gemini API key** and configuring it in SupoClip. No credit card is required.

---

## Step 1: Get Your Free API Key

1. Go to **[https://aistudio.google.com/](https://aistudio.google.com/)**.
2. Sign in with your Google account.
3. Click the blue **"Get API key"** button (in the left sidebar or top right).
4. Click **"Create API key"**.
5. Choose **"Create API key in new project"**.
6. Copy your generated key (it looks like `AIzaSy...`).

---

## Step 2: Configure `.env` in SupoClip

1. Open a terminal in the `supoclip` directory:
   ```bash
   cd /home/rahul/Documents/supoclip/supoclip
   ```

2. If you haven't created your `.env` file yet, copy it from the template:
   ```bash
   cp .env.example .env
   ```

3. Open `.env` and set these exact lines:

   ```env
   # 1. Google Gemini (Paste your key here)
   LLM=google-gla:gemini-2.5-flash
   GOOGLE_API_KEY=AIzaSy_YOUR_COPIED_KEY_HERE

   # 2. Free Transcription (Uses YouTube captions, 0% CPU/RAM)
   TRANSCRIPTION_PROVIDER=youtube_captions

   # 3. CPU Mode (Required for machines with 8 GB RAM and no GPU)
   BACKEND_CPU_ONLY=true

   # 4. Auth Secrets (Any random text)
   BETTER_AUTH_SECRET=supoclip_secret_auth_key_12345
   BACKEND_AUTH_SECRET=supoclip_secret_backend_key_12345
   ```

---

## Step 3: Start SupoClip

Run the start script:

```bash
./start.sh
```

*(Or run: `docker compose up -d`)*

> **Note:** The first startup takes 3–5 minutes while Docker downloads and builds the components.

---

## Step 4: Open the App

1. Open your browser and visit: **[http://localhost:3107](http://localhost:3107)**
2. Click **Sign Up** to create your local account.
3. Paste any YouTube video link (podcasts, talks, interviews).
4. Click **Generate Clips**.

---

## Summary of Free Quota
* **Cost:** $0.00 (No credit card needed).
* **Daily Limit:** Up to 1,500 requests per day (resets every 24 hours).
* **Expiration:** Never expires.
