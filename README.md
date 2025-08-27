# 🚀 Prompt Improver (AI-Powered)

A minimal, aesthetically pleasing web app that takes any user prompt and improves/expands it using an AI model (via **n8n backend + Google Gemini 1.5 Flash**).  

This project was built as an experimental tool to explore:
- Building and deploying workflows in **n8n**.  
- Connecting a frontend website to a backend automation using **webhooks**.  
- Hosting a static site on **GitHub Pages**.  
- Adding simple usage limits without requiring authentication.

---

## ✨ Features
- 🌐 **Frontend Website**:  
  - Users can enter any prompt in a clean UI.  
  - Prompt is sent to an **n8n webhook** which calls an AI model.  
  - Returns the improved prompt as plain text on the same page.  
  - Local storage enforces a limit of **3 prompts per user** (to avoid exceeding free trial execution limits).  
  - When users hit the limit, they’re shown a friendly message explaining this is a personal project.  

- ⚙️ **Backend (n8n)**:  
  - **Webhook node** receives input from frontend.  
  - **AI Node (Google Gemini)** improves and expands the given prompt.  
  - **Respond to Webhook node** sends improved text back to frontend.  
  - No database needed — fully stateless.  

- 🎨 **UI/UX**:  
  - Minimal, modern HTML + CSS (no frameworks).  
  - Fully responsive.  
  - 200 lines of lightweight, maintainable code.  

---

## 🛠️ Tech Stack

### Frontend
- **HTML5 + CSS3 + JavaScript**  
- Uses `fetch()` to send POST requests to n8n webhook.  
- LocalStorage API to track per-user prompt usage.  
- Hosted on **GitHub Pages**.  

### Backend
- **n8n (Cloud, free trial)**  
- **Google Gemini 1.5 Flash** AI model for text processing.  
- Webhook trigger + Set node + AI node + Respond to Webhook node.  

---

## 🧑‍💻 What We Learned
1. How to create backend workflows in **n8n**:
   - Webhook setup.  
   - Passing request JSON through nodes.  
   - Calling AI models (Gemini API).  
   - Sending responses back via Respond to Webhook node.  

2. How to connect a **frontend website** to n8n:
   - Sending prompts via `fetch()` with JSON body.  
   - Parsing AI response and rendering to user.  

3. How to **deploy websites on GitHub Pages**:  
   - Repository setup.  
   - Enabling GitHub Pages from root folder.  
   - Accessing live website via `https://username.github.io/repo-name`.  

4. Handling **limits and constraints**:
   - Used browser localStorage to allow only 3 free uses per user.  
   - Added graceful fallback messaging when limit is reached.  

5. Importance of **prompt engineering**:
   - Direct instructions vs meta-instructions (teaching AI *how* to behave).  
   - Crafting efficient prompts for best AI results.  

---

## 🚦 How to Use
1. Open the website (hosted on GitHub Pages).  
2. Type any prompt you want to improve.  
3. Get back an **expanded, more effective version** of your prompt.  
4. Each new visitor has **3 free improvements** (tracked via browser storage).  

---

## ⚠️ Notes
- Backend runs on **n8n Cloud Free Trial** (14 days, 1000 executions).  
- If backend is offline or trial ends, the website won’t work.  
- No login system → purely local, anonymous usage.  

---

## 📌 Future Improvements
- Add a proper authentication system with user accounts.  
- Implement global usage tracking (not just per-browser).  
- Deploy n8n backend permanently on a VPS (e.g. DigitalOcean).  
- Add multiple AI models for users to choose from.  

---

## 👨‍💻 Author
Built by Muhammad Ali as a personal experimental project.  
