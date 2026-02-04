# 🔐 Token Rotation Auth v1.0

> **Never write authentication from scratch again.**  
> Plug this backend into any frontend and enjoy **secure, seamless authentication with automatic token rotation**.

**Token Rotation Auth v1.0** is a **reusable, production-ready authentication backend** that handles:

- Access tokens  
- Refresh tokens  
- Secure token rotation  
- Session management  

Built so developers can **focus on product features instead of auth plumbing**.

---

## 🚀 Why This Project Exists

Most projects end up:

- Rewriting authentication logic repeatedly  
- Mishandling refresh tokens  
- Storing tokens insecurely  
- Skipping token rotation entirely (a serious security risk)  

This project solves those problems by providing:

- A **plug-and-play authentication backend**
- **Automatic refresh token rotation**
- Secure **HTTP-only cookie-based sessions**
- A clean API that works with **any frontend**

> Think of this as your **personal Auth Service** you can reuse forever.

---

## ✨ Features

- ✅ JWT-based Access & Refresh Tokens  
- 🔁 **Single-use Refresh Token Rotation**  
- 🔐 HTTP-only cookies for refresh tokens  
- 🧠 Stateless, short-lived access tokens  
- 🧾 Persistent and secure sessions  
- 🔄 Seamless re-authentication (no forced logout)  
- 🧩 Frontend-agnostic (Web, Mobile, SSR)  
- 🛠 Modular and easy to extend  

---

## 🧱 Tech Stack

| Layer | Technology |
|-----|-----------|
| Backend | Node.js, Express.js |
| Authentication | JSON Web Tokens (JWT) |
| Database | MongoDB |
| Security | HTTP-only cookies, token invalidation |
| Architecture | Modular & reusable |

---

## 🧠 How Token Rotation Works

1. User logs in  
2. Server issues:  
   - Short-lived **Access Token**  
   - Long-lived **Refresh Token**  
3. Access token expires  
4. Frontend calls `/auth/refresh`  
5. Server:  
   - Verifies refresh token  
   - **Invalidates the old refresh token**  
   - Issues a new access token and refresh token  
6. User remains logged in securely  

> Even if a refresh token is stolen, it becomes useless after one use.

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
├── middleware/
│   └── auth.middleware.js
├── utils/
│   └── token.utils.js
├── config/
│   └── db.js
├── app.js
├── server.js
└── package.json
