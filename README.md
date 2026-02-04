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
- Skipping token rotation entirely  

This project solves those problems by providing:

- A **plug-and-play authentication backend**
- **Automatic refresh token rotation**
- Secure **HTTP-only cookie-based sessions**
- A clean API that works with **any frontend**

---

## ✨ Features

- ✅ JWT-based Access & Refresh Tokens  
- 🔁 **Single-use Refresh Token Rotation**  
- 🔐 HTTP-only cookies for refresh tokens  
- 🧠 Stateless, short-lived access tokens  
- 🧾 Persistent and secure sessions  
- 🔄 Seamless re-authentication  
- 🧩 Frontend-agnostic  
- 🛠 Modular and extensible  

---

## 🧱 Tech Stack

| Layer | Technology |
|------|-----------|
| Backend | Node.js, Express.js |
| Authentication | JWT |
| Database | MongoDB |
| Security | HTTP-only cookies |
| Architecture | Modular |

---

## 🧠 Token Rotation Flow

1. User logs in  
2. Server issues:
   - Short-lived **Access Token**
   - Long-lived **Refresh Token**
3. Access token expires  
4. Frontend calls `/auth/refresh`  
5. Server rotates refresh token  
6. User stays authenticated  

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
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Adam2053/token-rotation-auth-adam.git
cd token-rotation-auth-adam
```

---

### 2️⃣ Install Dependencies

Install all required Node.js dependencies using npm:

```bash
npm install
```

---

### 3️⃣ Environment Variables

Create a `.env` file in the root directory of the project and add the following variables:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/token-auth

ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret

ACCESS_TOKEN_EXPIRES_IN=15m
REFRESH_TOKEN_EXPIRES_IN=7d
```
---

### 4️⃣ Run the Application

After configuring the environment variables, start the server using one of the following commands:

#### Development Mode

```bash
npm run dev
```

### Production Mode

```bash
npm start
```

### Once the Server is running it will be accesed at

```bash
http://localhost:PORT/
```

replace the PORT with the env variable

---

## 📜 NPM Scripts

| Script | Description |
|------|------------|
| `npm run dev` | Start server with nodemon |
| `npm start` | Start production server |

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|------|----------|-------------|
| POST | `/auth/register` | Register a new user |
| POST | `/auth/login` | Login and receive tokens |
| POST | `/auth/refresh` | Rotate refresh token |
| POST | `/auth/logout` | Logout and invalidate session |
| GET  | `/auth/me` | Get the authenticated user |

---

## 🧑‍💻 Frontend Integration Guide

Follow this recommended pattern for secure authentication:

1. Call `/auth/login`
2. Store the **access token in memory** (❌ do not use localStorage)
3. Refresh token remains in an **HTTP-only cookie**
4. On `401 Unauthorized`:
   - Call `/auth/refresh`
   - Retry the original request
5. User remains logged in seamlessly

> Secure by default. No token leakage.

---

## 🔐 Security Notes

- Refresh tokens are **single-use**
- Old refresh tokens are invalidated immediately
- Refresh tokens are stored in **HTTP-only cookies**
- Access tokens are **short-lived**
- Protects against replay attacks

---

## 🧪 Who Should Use This?

- SaaS builders
- Startup MVPs
- Indie hackers
- Full-stack developers
- Anyone tired of rewriting authentication logic

---

## 🛣 Future Roadmap

- 🔍 **Request & data validation using Zod**
- 🧪 Improved error handling & typed responses
- 📦 Docker support
- 🔐 Role-based access control (RBAC)
- 📄 Swagger / OpenAPI documentation
- 🔄 Advanced session management

---

## 🤝 Contributing & Collaboration

This project is **open for collaboration**.

If you have:
- Feature ideas
- Security improvements
- Performance optimizations
- General suggestions

Feel free to:
- Open an issue
- Submit a pull request
- Start a discussion

---

## ⭐ Support

If this project helped you:

- ⭐ Star the repository
- 📢 Share it with other developers
- 🚀 Use it in your projects

---

**Built to be reused.**  
**Built to be secure.**  
**Built so you never write authentication again.**

