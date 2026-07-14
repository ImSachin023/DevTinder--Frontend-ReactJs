## 📖 About The Project

**DevTinder** is a full-stack social networking platform built for developers to discover, connect, and chat with one another — inspired by Tinder's swipe-based matching UX. This repository contains the **React frontend**.

Users can create a profile, swipe through a feed of other developers, send/accept/reject connection requests, chat in real time once matched, and unlock premium features through an integrated payment gateway.

> 🔗 This is the frontend half of a full-stack project. The [Node.js/Express backend](#) handles auth, database, sockets, and payment webhooks.

---

## ✨ Features

- 🔐 **Authentication** — Signup/login with protected routes (auto-redirect to login if not authenticated)
- 🃏 **Swipeable Feed** — Browse other developer profiles as interactive cards
- 🤝 **Connections** — Send, accept, reject, and ignore connection requests
- 📋 **My Network** — View all active connections and pending requests in dedicated pages
- 🙍 **Profile Management** — Edit profile with real-time toast notifications on save
- 💬 **Real-time Chat** — 1:1 messaging with matched users via WebSockets (Socket.io)
- 💳 **Premium Membership** — Razorpay payment gateway integration for premium upgrades
- 🎨 **Responsive UI** — Built with Tailwind CSS + daisyUI component library
- 🗃️ **Centralized State** — Global state management with Redux Toolkit

---

## 🖼️ Screenshots

<!-- Add 2-4 screenshots or a short GIF here — this is the single biggest upgrade you can make. 
Example:
| Feed | Chat | Profile |
|---|---|---|
| ![Feed](./screenshots/feed.png) | ![Chat](./screenshots/chat.png) | ![Profile](./screenshots/profile.png) |
-->

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| **Library** | React (Vite) |
| **Routing** | React Router DOM |
| **State Management** | Redux Toolkit |
| **Styling** | Tailwind CSS, daisyUI |
| **HTTP Client** | Axios |
| **Real-time** | Socket.io-client |
| **Payments** | Razorpay |
| **Deployment** | Vercel |

---

## 🏗️ Architecture Overview

```
User Action → React Component → Redux Slice (async thunk) → Axios (withCredentials) → Backend API
                                                                                            │
                                                    Socket.io-client ←── Real-time events ──┘
```

- Auth state and feed data are normalized in the Redux store and consumed across components (e.g. Navbar updates instantly on login/logout).
- All API calls use `axios` with `withCredentials: true` so the JWT cookie set by the backend is sent automatically.
- Protected routes check the Redux auth state and redirect unauthenticated users to `/login`.

---

## 📂 Project Structure

```
DevTinder--Frontend-ReactJs/
├── public/                # Static assets
├── src/
│   ├── components/        # Reusable UI components (Navbar, Footer, Card, etc.)
│   ├── pages/              # Route-level pages (Feed, Login, Profile, Chat, Connections)
│   ├── utils/              # Axios instance, socket connection, constants
│   ├── store/               # Redux Toolkit store + slices
│   └── App.jsx             # Route definitions
├── index.html
├── vite.config.ts
└── package.json
```

> ⚠️ Adjust this tree to match your actual `src/` layout before publishing — recruiters do open this folder to sanity-check it.

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- The [DevTinder backend](#) running locally or deployed (this frontend expects a running API)

### Installation

```bash
# Clone the repo
git clone https://github.com/ImSachin023/DevTinder--Frontend-ReactJs.git
cd DevTinder--Frontend-ReactJs

# Install dependencies
npm install

# Create a .env file and add your backend API base URL
echo "VITE_API_BASE_URL=http://localhost:3000" > .env

# Start the dev server
npm run dev
```

The app will be running at `http://localhost:5173`.

---

## 🔑 Environment Variables

| Variable | Description |
|---|---|
| `VITE_API_BASE_URL` | Base URL of the backend API |
| `VITE_RAZORPAY_KEY_ID` | Razorpay public key for the payment checkout |

---

## 🗺️ Roadmap

- [ ] Add unit/E2E test coverage
- [ ] Add dark/light theme toggle
- [ ] Improve chat UI with typing indicators and read receipts
- [ ] Add message pagination and search

---

## 👤 Author

**Sachin**
- Live Project: [dev-coder-nu.vercel.app](https://dev-coder-nu.vercel.app)
- GitHub: [@ImSachin023](https://github.com/ImSachin023)

---

## 📄 License
This project is open source — feel free to explore, fork, and learn from it.
