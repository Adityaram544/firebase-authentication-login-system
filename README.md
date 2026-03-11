
# 🔐 Firebase Authentication Login System

> A clean, fully functional user authentication system built with Firebase — featuring secure user registration, login, and session management with a seamless single-page experience.

**🌐 Live Demo:** [firebase-authentication-login-syste.vercel.app](https://firebase-authentication-login-syste.vercel.app)

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Firebase Setup](#firebase-setup)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Deployment](#deployment)
- [Security Notes](#security-notes)
- [License](#license)

---

## About

**Firebase Authentication Login System** is a ready-to-integrate authentication template that handles the most critical part of any web application — user identity. It provides a smooth, toggling Sign Up / Sign In interface backed by Firebase's secure authentication infrastructure, with protected routing to a post-login homepage.

This project serves as both a standalone authentication solution and a practical reference for developers learning Firebase Auth integration.

---

## ✨ Features

- 📝 **User Registration** — create new accounts with email and password
- 🔑 **User Login** — authenticate existing users securely
- 🔄 **Seamless UI toggle** — switch between Sign Up and Sign In without page reloads
- 🏠 **Protected homepage** — redirects authenticated users to a dedicated landing page
- 🚪 **Sign Out** — securely ends the user session
- 🔒 **Firebase-backed security** — leverages Google's authentication infrastructure
- 📱 **Responsive design** — works across all screen sizes
- ⚡ **No framework required** — lightweight vanilla JS implementation

---

## 🛠 Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 | Page structure & markup |
| CSS3 | Styling & responsive layout |
| JavaScript (ES6+) | App logic & Firebase integration |
| [Firebase Authentication](https://firebase.google.com/docs/auth) | Secure user auth backend |
| [Firebase SDK](https://firebase.google.com/) | Client-side Firebase integration |
| [Vercel](https://vercel.com/) | Hosting & deployment |

---

## 🚀 Getting Started

### Prerequisites

- A modern web browser
- A [Firebase](https://firebase.google.com/) account (free tier is sufficient)
- A code editor (e.g., [VS Code](https://code.visualstudio.com/))

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Adityaram544/firebase-authentication-login-system.git
   cd firebase-authentication-login-system
   ```

2. **Configure Firebase** *(see [Firebase Setup](#firebase-setup) below)*

3. **Open in browser**
   ```bash
   # macOS
   open index.html

   # Windows
   start index.html
   ```

   No build step or `npm install` required.

---

## 🔥 Firebase Setup

1. Go to the [Firebase Console](https://console.firebase.google.com/) and create a new project
2. Navigate to **Authentication → Sign-in method** and enable **Email/Password**
3. Go to **Project Settings → General** and copy your Firebase config object
4. Open `firebaseauth.js` and replace the config placeholder with your own:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

5. Save the file and open `index.html` in your browser — the app is ready to use.

---

## 📁 Project Structure

```
firebase-authentication-login-system/
├── index.html          # Login & registration UI (toggling Sign Up / Sign In)
├── homepage.html       # Protected page shown after successful login
├── firebaseauth.js     # Firebase initialization & config
├── script.js           # Registration & login logic (index.html)
├── homepage.js         # Auth state check & sign-out logic (homepage.html)
├── style.css           # Styling & responsive layout
└── README.md           # Project documentation
```

---

## ⚙️ How It Works

### Authentication Flow

```
User visits index.html
        │
        ├── New user? → Fills Sign Up form → Firebase creates account → Redirect to homepage.html
        │
        └── Returning user? → Fills Sign In form → Firebase verifies credentials → Redirect to homepage.html
```

### Session & Route Protection

- `homepage.js` checks Firebase's auth state on load using `onAuthStateChanged()`
- If no authenticated user is detected, the user is immediately redirected back to `index.html`
- This prevents unauthorized access to the protected homepage without a valid session

### Sign Out

- Clicking the sign-out button on `homepage.html` calls `signOut()` from Firebase Auth
- The user is redirected back to `index.html` and the session is cleared

---

## 🌍 Deployment

This project is deployed on **Vercel** as a static site.

To deploy your own fork:

1. Push the project to your GitHub account
2. Visit [vercel.com](https://vercel.com) and import the repository
3. Vercel auto-detects it as a static site — no configuration needed
4. Your app goes live instantly at a `.vercel.app` URL

> Make sure your Firebase project's **Authorized Domains** list includes your Vercel URL.  
> Go to Firebase Console → **Authentication → Settings → Authorized domains** and add your domain.

---

## 🛡 Security Notes

- **Never commit your Firebase config with production credentials** to a public repository. Consider using environment variables or a `.env` file for sensitive values
- Firebase's client-side config is not fully secret by nature, but you can restrict API key usage in the [Google Cloud Console](https://console.cloud.google.com/) under **APIs & Services → Credentials**
- Always configure **Firebase Security Rules** appropriately if using Firestore or Realtime Database alongside this auth system

---

<div align="center">
  <p>Made with ❤️ by <a href="https://github.com/Adityaram544">Aditya Ram</a></p>
  <p>
    <a href="https://firebase-authentication-login-syste.vercel.app">🌐 Live Site</a> •
    <a href="https://github.com/Adityaram544/firebase-authentication-login-system/issues">🐛 Report Bug</a> •
    <a href="https://github.com/Adityaram544/firebase-authentication-login-system/issues">💡 Request Feature</a>
  </p>
</div>
