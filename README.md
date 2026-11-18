# ðŸ“ˆ Learn2Invest â€” AI-Guided Virtual Simulator for Learning Indian Investments

> A full-stack **MERN** gamified financial literacy platform where students and first-time investors practise with **virtual money** across Fixed Deposits, Mutual Funds, Government Schemes, and Banking â€” with zero real financial risk.

---

## ðŸŒ Live Demo

> ðŸš§ Deployment in progress â€” run locally using the steps below.

---

## ðŸŽ® What is Learn2Invest?

Learn2Invest is a **3D interactive investment education platform** built for Indian students and first-time investors. Users explore a fully animated 3D school campus, watch financial literacy video lessons, take MCQ quizzes, run virtual investment simulations, and practice filling real Indian bank slips â€” all without risking any real money.

The platform uses **gamification** (XP points, leaderboards, badges, level progression) to make financial education engaging and approachable.

---

## ðŸ—ºï¸ Learning Journey

```
ðŸ« Login â†’ School Yard â†’ Classroom 101 (5 Video Lessons)
        â†’ Exam Room 103 (10-Question MCQ Quiz)
        â†’ Floor 2 Computer Lab (3 Investment Simulators)
        â†’ School Exit â†’ ðŸ¦ Futuristic City Bank
        â†’ Bank Sections (Deposit Slips, Cyber Safety)
        â†’ ðŸŽ‰ Journey Complete
```

---

## âœ¨ Key Features

### ðŸ« Level 1 â€” School World (3D)
- Fully hand-crafted **3D school campus** using React Three Fiber + Three.js (no game engine)
- Animated player characters **Luna** (girl) and **Leo** (boy) with walking, seated, and idle animations
- 8 autonomous **NPC students** patrolling the campus on waypoint routes
- **5 financial literacy video lessons** played on a 3D classroom projector
- Video stall **auto-recovery** â€” detects freezes and resumes automatically
- **Fullscreen cinema mode** for immersive video viewing
- **10-question MCQ exam** with persistent attempt saving (resume mid-quiz)
- Key Takeaways card shown after each lesson video
- Functional **wall clock**, financial wisdom **poster wall**, and chalkboard diagrams
- Day / Night mode toggle with dynamic lighting

### ðŸ’» Level 2 â€” Government Investment Lab
- **Computer 1** â€” 6 Indian Government Scheme Simulators: PPF (7.1%), FD (7.25%), NSC (7.7%), Sukanya Samriddhi Yojana (8.2%), Recurring Deposit (6.5%), Post Office MIS (7.4%)
- **Computer 2** â€” Savings Mixer Studio with custom allocation sliders across 5 schemes
- **Computer 3** â€” Portfolio Simulator with Smart Allocation algorithm, Gap Period Analysis, and save-to-vault feature
- Saved simulations manager â€” view, edit, recalculate, and delete saved portfolios

### ðŸ¦ Level 3 â€” Futuristic City Bank
- Practice filling **authentic Indian bank slips** for 5 real banks: SBI, PNB, Canara Bank, Karnataka Bank, Post Office Savings Bank
- Slip types: **Cash Deposit Pay-In Slip** (with counterfoil), **Withdrawal Slip**, **Cheque**
- Real-time **Razorpay IFSC API** validation for branch code verification
- **India Post PIN Code API** for branch location lookup
- **Digital Cyber Safety** â€” interactive scam detection (phishing SMS, fake lottery calls, OTP protection)

### ðŸ¤– AI Chatbot (AIRA)
- Context-aware AI mentor powered by **Google Gemini API**
- Knows the user's current screen, XP, lessons watched, and quiz score
- 3-tier fallback: Gemini â†’ Pollinations AI â†’ Local Knowledge Engine
- **Voice input** (Web Speech API) and **voice output** (Speech Synthesis API)
- Answers financial questions in plain language with â‚¹ formatting

### ðŸŽ® Gamification
- **XP system** â€” earn points by watching lessons, passing quizzes, saving simulations
- **Global leaderboard** with community rankings
- **Badges** and achievement tracking
- **Performance Report** â€” comprehensive scorecard
- **Theme Vault** â€” unlock custom color themes with XP
- **Character customization** â€” 5 outfit color themes (Classic, Emerald Mint, Royal Indigo, Sunset Coral, Cyber Gold)
- **Ice cream stall** â€” buy virtual ice cream, character holds it for 30 seconds ðŸ¦

---

## ðŸ§° Technology Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 18, Vite, Tailwind CSS, Framer Motion |
| **3D Engine** | Three.js, React Three Fiber, @react-three/drei |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB Atlas, Mongoose |
| **Auth** | JWT (JSON Web Tokens), bcryptjs |
| **AI** | Google Gemini API (`@google/genai`) |
| **3rd Party APIs** | Razorpay IFSC API, India Post PIN API |
| **Browser APIs** | Web Speech API (voice input + output) |
| **Animations** | GSAP, CSS animations |

---

## ðŸ—ï¸ Project Structure

```
Learn2Invest/
â”œâ”€â”€ src/                        # React frontend
â”‚   â”œâ”€â”€ App.jsx                 # Root component & global state
â”‚   â”œâ”€â”€ three/                  # 3D world components
â”‚   â”‚   â”œâ”€â”€ Level1SchoolWorld.jsx      # Complete Level 1 (12,000+ lines)
â”‚   â”‚   â”œâ”€â”€ Level2GovernmentWorld.jsx  # Level 2 environment
â”‚   â”‚   â”œâ”€â”€ Level3FuturisticWorld.jsx  # Level 3 bank environment
â”‚   â”‚   â”œâ”€â”€ Level3BankZone3D.jsx       # 3D bank building
â”‚   â”‚   â””â”€â”€ Level2ComputerScreens.jsx  # Investment simulator UIs
â”‚   â”œâ”€â”€ screens/                # Additional screen components
â”‚   â”œâ”€â”€ components/             # Reusable UI components
â”‚   â”‚   â”œâ”€â”€ AIRAChatPanel.jsx   # AI chatbot with voice I/O
â”‚   â”‚   â””â”€â”€ ...
â”‚   â”œâ”€â”€ utils/
â”‚   â”‚   â””â”€â”€ soundEngine.js      # Ambient music & SFX controller
â”‚   â””â”€â”€ data.js                 # Quiz question bank & helpers
â”‚
â”œâ”€â”€ server/                     # Express.js backend
â”‚   â”œâ”€â”€ server.js               # Main API server (Express + all routes)
â”‚   â”œâ”€â”€ models.js               # Mongoose schemas (User, UserState)
â”‚   â”œâ”€â”€ db.js                   # MongoDB Atlas connection
â”‚   â”œâ”€â”€ localDb.js              # Local JSON fallback (adapter pattern)
â”‚   â”œâ”€â”€ financialKnowledge.js   # Offline AI knowledge engine
â”‚   â””â”€â”€ .env                    # â† NOT committed (see .env.example)
â”‚
â”œâ”€â”€ public/
â”‚   â”œâ”€â”€ videos/                 # Lesson MP4 files (video1â€“5.mp4)
â”‚   â””â”€â”€ images/                 # Character and UI images
â”‚
â”œâ”€â”€ .env.example                # Template for environment variables
â””â”€â”€ package.json                # Root scripts (concurrently runs both servers)
```

---

## ðŸ”Œ Backend API Endpoints

| Method | Route | Auth | Description |
|---|---|---|---|
| `POST` | `/api/register` | âŒ | Register new user |
| `POST` | `/api/login` | âŒ | Login and receive JWT |
| `POST` | `/api/state/save` | âœ… JWT | Save user progress (XP, lessons, quiz) |
| `GET` | `/api/state/load` | âœ… JWT | Load saved user progress |
| `GET` | `/api/leaderboard` | âŒ | Fetch top players by XP |
| `POST` | `/api/chat` | âŒ | AI chatbot (Gemini + fallback) |
| `GET` | `/api/admin/users` | âœ… JWT | Admin â€” list all users |
| `DELETE` | `/api/admin/users/:email` | âœ… JWT | Admin â€” delete a user |

---

## âš™ï¸ Local Setup

### Prerequisites
- Node.js 18+
- npm
- MongoDB Atlas account (free tier) **OR** run without it (uses local JSON fallback automatically)

### 1. Clone the repository
```bash
git clone https://github.com/K1V25A/Learn2Invest.git
cd Learn2Invest
```

### 2. Install frontend dependencies
```bash
npm install
```

### 3. Install backend dependencies
```bash
cd server
npm install
cd ..
```

### 4. Configure environment variables
```bash
cp server/.env.example server/.env
```
Edit `server/.env`:
```env
MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/learn2invest
JWT_SECRET=your_secure_random_secret_key
GEMINI_API_KEY=your_google_gemini_api_key
PORT=5000
```

> **Note:** If `MONGODB_URI` is unavailable, the app automatically falls back to a local `server/local_db.json` file â€” no data is lost.

### 5. Add lesson videos
Place MP4 files in `public/videos/`:
```
public/videos/video1.mp4
public/videos/video2.mp4
public/videos/video3.mp4
public/videos/video4.mp4
public/videos/video5.mp4
```

### 6. Run the application
```bash
npm run dev
```
This starts both servers concurrently:
- **Frontend** â†’ http://localhost:5173
- **Backend API** â†’ http://localhost:5000

---

## ðŸ—ƒï¸ Database Schema

### User (Authentication)
```js
{
  email: String (unique, required),
  name: String (required),
  passwordHash: String (bcrypt hashed),
  startLevel: String ('beginner' | 'intermediate')
}
```

### UserState (Progress)
```js
{
  email: String,
  xp: Number,
  lessonsWatched: [String],
  completedModules: [String],
  quizScore: Number,
  quizAttempt: Mixed,       // flexible quiz state object
  level1Completed: Boolean,
  level2Completed: Boolean,
  level3Completed: Boolean,
  intermediateUnlocked: Boolean,
  allocations: Map<String, Number>
}
```

---

## ðŸ” Security Features

- Passwords hashed with **bcryptjs** (salt rounds: 10) â€” never stored in plain text
- **JWT tokens** (7-day expiry) for stateless authentication
- Protected API routes via `authenticateToken` middleware
- `.env` with secrets excluded from version control via `.gitignore`
- MongoDB error handling â€” graceful fallback prevents server crashes
- AI chatbot system prompt prevents prompt injection and credential exposure

---

## ðŸ¤– AI Chatbot Fallback Chain

```
1. Google Gemini API (primary â€” tries 5 model variants)
        â†“ (if unavailable)
2. Pollinations AI (secondary â€” zero API key required)
        â†“ (if unavailable)
3. Local Knowledge Engine (offline â€” pre-written financial Q&A)
        â†“ (if no match)
4. Default guidance message
```
The chatbot **never fails with a 500 error** â€” always returns a useful response.

---

## ðŸ“¸ Screenshots

> _Coming soon â€” screenshots of the 3D school world, classroom projector, investment simulators, and bank slip practice._

---

## ðŸ‘©â€ðŸ’» Author

**Kavya P** — [GitHub](https://github.com/K1V25A)

---

## ðŸ“„ License

This project is for educational purposes. All investment amounts and returns shown are **virtual simulation only** â€” no real money is involved.

> âš ï¸ **Disclaimer:** Learn2Invest is a 100% educational platform. All investments, returns, and balances are simulated with virtual money. This is not financial advice.

