# 🔐 Token Rotation Auth v1.0

> **Never write authentication from scratch again.**  
> Plug this backend into any frontend and get **secure, seamless authentication with automatic token rotation**.

**Token Rotation Auth v1.0** is a **reusable, production-ready authentication backend** that handles:
- Access tokens
- Refresh tokens
- Secure token rotation
- Session management

Built so developers can **focus on product features instead of auth plumbing**.

---

## 🚀 Why This Exists

Most projects:
- Rewrite auth logic every time
- Handle refresh tokens incorrectly
- Store tokens insecurely
- Skip rotation (huge security risk)

This project solves that by giving you:
- A **drop-in authentication backend**
- **Automatic refresh token rotation**
- Secure cookie-based sessions
- A clean API usable by **any frontend**

> Think of this as your personal Auth Service.

---

## ✨ Features

- ✅ JWT-based Access & Refresh Tokens
- 🔁 **Refresh Token Rotation (single-use refresh tokens)**
- 🔐 HTTP-only cookies for refresh tokens
- 🧠 Stateless access tokens
- 🧾 Persistent sessions
- 🔄 Seamless login without forced logout
- 🧩 Frontend-agnostic
- 🛠 Easy to extend & customize

---

## 🧱 Tech Stack

- **Backend:** Node.js, Express.js
- **Auth:** JSON Web Tokens (JWT)
- **Database:** MongoDB
- **Security:** HTTP-only cookies, token invalidation
- **Architecture:** Modular & reusable

---

## 🧠 Token Rotation Flow

1. User logs in
2. Server issues:
   - Short-lived **Access Token**
   - Long-lived **Refresh Token**
3. Access token expires
4. Frontend calls `/auth/refresh`
5. Server:
   - Verifies refresh token
   - **Invalidates old refresh token**
   - Issues new access + refresh tokens
6. User stays logged in securely

> A stolen refresh token is useless after one use.

---

## 📂 Project Structure

```txt
token-rotation-auth/
├── controllers/
│   └── auth.controller.js
├── models/
│   └── user.model.js
├── routes/
│   └── auth.routes.js
├── utils/
│   └── token.utils.js
├── middleware/
│   └── auth.middleware.js
├── config/
│   └── db.js
├── app.js
├── server.js
└── package.json
```
##⚙️ Installation & Setup

##1️⃣ Clone the Repository
git clone https://github.com/Adam2053/token-rotation-auth-adam.git
cd token-rotation-auth-adam

##2️⃣ Install Dependencies
npm install

##3️⃣ Environment Variables
Create a .env file in the root directory:
PORT=5000
MONGO_URI=mongodb://localhost:27017/token-auth
ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret
ACCESS_TOKEN_EXPIRES_IN=15m
REFRESH_TOKEN_EXPIRES_IN=7d

##4️⃣ Run the Server
Development
npm run dev
Production
npm start
Server will run on:
http://localhost:PORT (from env) 

##📜 NPM Scripts
Script	Description
npm run dev	Start server with nodemon
npm start	Start production server
🔌 API Endpoints
Method	Endpoint	Description
POST	/auth/register	Register a new user
POST	/auth/login	Login and receive tokens
POST	/auth/refresh	Rotate refresh token
POST	/auth/logout	Logout and invalidate session
GET	/auth/me	Get current authenticated user

##🧑‍💻 Frontend Usage (Recommended Pattern)
Call /auth/login
Store access token in memory (NOT localStorage)
Refresh token stays in HTTP-only cookie
On 401 Unauthorized:
Call /auth/refresh
Retry failed request
User remains logged in seamlessly
Secure by default. No token leaks.

##🔐 Security Notes
Refresh tokens are single-use
Old refresh tokens are invalidated
Cookies are HTTP-only
Access tokens are short-lived
Prevents replay attacks

##🧪 Who Should Use This?
SaaS builders
Indie hackers
Startup MVPs
Full-stack developers
Anyone tired of rewriting auth

##🛣 Future Updates
🔍 Request & data validation using Zod
🧪 Better error handling & typed responses
📦 Docker support
🔐 Role-based access control (RBAC)
📄 Swagger / OpenAPI docs
🔄 Advanced session management
🤝 Contributing & Collaboration
This project is open for collaboration.
Have:

Suggestions?
Improvements?
Security ideas?
Feel free to:
Open an issue
Submit a pull request
Start a discussion
Let’s build an auth system developers can truly rely on.
⭐ Support
If this project saved you time:
Star ⭐ the repo
Share it with others
Use it in your projects
Built to be reused.
Built to be secure.
Built so you never write auth again.

---

If you want **next**:
- README badges  
- Architecture diagram  
- Next.js example client  
- Convert this into an **npm package / SaaS auth service**

Say it straight — we move fast.
