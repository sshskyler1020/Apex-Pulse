# ⚡ APEX PULSE — Calisthenics System

> *"The system has analyzed your data. Your ascent begins now."*

A Solo Leveling-inspired **AI-powered calisthenics web app** with camera-verified workouts, rank progression, and cloud-synced accounts. No equipment. No manual logging. No cheating.

---

## 🚀 Live Demo

Hosted on GitHub Pages → **[your-username.github.io/apex-pulse](https://your-username.github.io/apex-pulse)**

---

## ✨ Features

### 🤖 AI-Generated Training Plans
- Enter your age, weight, height, gender, experience level, and goals
- Claude AI generates a personalized 7-day calisthenics program
- Goals include: Look Better, Get Stronger, Build Muscle, Lose Fat, Endurance, Flexibility, Learn Skills, Confidence

### 📹 Camera-Verified Workouts
- Every session must be **recorded on camera** — no manual logging allowed
- 8 frames are extracted from your recording and sent to **Groq Vision AI** (`meta-llama/llama-4-scout-17b-16e-instruct`)
- AI strictly verifies: real movement, correct exercises, visible effort
- Verdicts: **VERIFIED** ✓ / **SUSPICIOUS** ⚠ / **FAILED** ✗

### ⚠️ Punishment System
- Failed verification = **punishment issued** and **-50 XP penalty**
- A random punishment exercise is assigned (push-ups, burpees, jump squats, etc.)
- The app is **locked** until the punishment is recorded and AI-verified
- Punishment attempts are tracked — every failed attempt adds another strike
- No way around it. The system does not forget.

### 🏆 Rank System (G → S)
| Rank | Title | XP Required |
|------|-------|------------|
| G | Grunt | 0 XP |
| F | Fighter | 150 XP |
| E | Enforcer | 350 XP |
| D | Drifter | 650 XP |
| C | Combatant | 1,100 XP |
| B | Berserker | 1,750 XP |
| A | Ace | 2,800 XP |
| S | Sovereign | 4,500 XP |

- Dramatic rank-up overlay with particle effects on advancement
- Full rank showcase with unlock status and XP requirements

### ⚡ XP & Progression
- **AI Verified session:** 50 XP + 5 per exercise
- **Suspicious session:** 20 XP + 5 per exercise
- **Failed session:** 0 XP + punishment
- Streak tracking, session history, achievements

### 🔥 Achievements
- First Blood, Awakening, Devoted, Relentless, Obsessed
- Chain Breaker, Unstoppable, Iron Will
- Rank milestone achievements up to S

### 🔐 Firebase Accounts
- Email/Password sign-up and login
- Google Sign-In
- All progress syncs to **Firestore** in real-time
- Access your data from any device

---

## 🛠️ Setup

### 1. Firebase
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project
3. Add a **Web App** and copy the `firebaseConfig`
4. Enable **Authentication** → Email/Password + Google
5. Enable **Firestore Database** (start in test mode)
6. Paste your config into `index.html` where marked:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### 2. Groq API Key
1. Go to [console.groq.com](https://console.groq.com) and create a free account
2. Generate an API key
3. Enter it in the **GROQ KEY** field inside the camera modal before recording

> The Groq key is entered at runtime — it is never stored or sent anywhere except directly to Groq's API.

### 3. Deploy to GitHub Pages
1. Upload `index.html` to your repository root
2. Go to **Settings → Pages**
3. Source: **Deploy from branch → main → / (root)**
4. Your app will be live at `https://YOUR-USERNAME.github.io/REPO-NAME/`

---

## 📁 File Structure

```
apex-pulse/
├── index.html      ← entire app (HTML + CSS + JS, single file)
└── README.md       ← this file
```

Everything is self-contained in one HTML file. No build tools, no dependencies to install, no `node_modules`.

---

## 🎮 How It Works

```
Sign Up / Log In
       ↓
Build Profile (age, weight, height, gender, goals, experience)
       ↓
AI generates your 7-day plan
       ↓
Select a workout day → Open Camera
       ↓
Record yourself completing the workout
       ↓
8 frames extracted → sent to Groq Vision AI
       ↓
VERIFIED → XP awarded → Day marked complete
FAILED   → Punishment issued → App locked
       ↓
Complete punishment (also camera-verified)
       ↓
App unlocked → Continue training
```

---

## 🔒 Anti-Cheat Design

- No manual logging — every session requires camera
- Groq Vision AI checks all 8 frames independently
- Minimum 10-second recording enforced
- Punishment system blocks all app features until cleared
- Punishment verification also requires camera + AI approval
- Failed punishments stack — attempts are tracked
- XP penalties applied immediately on failure

---

## 🎨 Design

Inspired by **Solo Leveling** — dark navy base, electric blue and purple glows, Orbitron + Rajdhani fonts, scan-line animations, hexagonal clip-paths, status-screen UI panels.

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML, CSS, JavaScript |
| AI Plan Generation | Anthropic Claude API (`claude-sonnet-4-20250514`) |
| Workout Verification | Groq API (`meta-llama/llama-4-scout-17b-16e-instruct`) |
| Auth & Database | Firebase Auth + Firestore |
| Camera | MediaRecorder Web API |
| Hosting | GitHub Pages |

---

## ⚙️ Browser Requirements

- **Chrome 80+** or **Edge 80+** — recommended
- **Firefox 75+** — supported
- **Safari 15.4+** — supported
- Camera and microphone permissions required
- HTTPS required for camera access (GitHub Pages provides this automatically)

---

## 📄 License

MIT — free to use, modify, and deploy.

---

<div align="center">
  <strong>Built with ⚡ for those who don't make excuses.</strong>
</div>
