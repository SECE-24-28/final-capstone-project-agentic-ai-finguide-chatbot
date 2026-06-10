# 💰 FinLit — Financial Literacy Chatbot for Students

> An AI-powered financial literacy platform that helps students understand, track, and improve their personal finances through intelligent conversation.

---

## 🧭 Overview

FinLit is a full-stack web application featuring an AI chatbot at its core. It guides students through personalized financial questions, remembers their answers, and turns that data into actionable insights on a live dashboard — all backed by a smart spending and budget tracker.

---

## ✨ Features

### 🤖 AI Chatbot (Core Feature)
- Asks intelligent, personalized finance questions on first visit (income, expenses, goals, debts, habits)
- On return visits greets the user: *"Hey, any updates or doubts?"*
- Answers any finance-related question asked by the user
- Politely declines and redirects off-topic questions
- All answers are auto-saved and used to update the user's financial profile

### 👤 User Authentication & Profile
- Register and login with email/password (JWT-based sessions)
- Personal profile: name, age, income bracket, financial goals
- Profile can be updated at any time

### 📊 Dashboard
- Financial health score (auto-calculated from chat data)
- Charts and graphs that update automatically as new data comes in
- Spending breakdown by category (pie/bar charts)
- Budget vs actual spending comparison
- Savings goal progress tracker

### 💸 Spending & Budget Tracker
- Log daily expenses with categories (food, transport, study, entertainment, etc.)
- Set monthly budgets per category
- Visual progress bars showing spending vs budget
- Alerts when approaching or exceeding budget limits

### 🗃️ Smart Data Layer
- All chat answers auto-saved to user profile
- Profile and charts update automatically — no manual save needed
- Full chat history stored per user
- Transactions stored and linked to profile

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js / Next.js |
| Styling | Tailwind CSS |
| Backend | Node.js + Express.js |
| Database | PostgreSQL (or MongoDB) |
| Authentication | JWT + bcrypt |
| AI Chatbot | Claude API (Anthropic) |
| Charts | Recharts / Chart.js |
| Deployment | Vercel (frontend) + Render/Railway (backend) |

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18+
- PostgreSQL (or MongoDB Atlas account)
- Anthropic API key ([get one here](https://console.anthropic.com))

### 1. Clone the repository

```bash
git clone https://github.com/your-username/finlit-chatbot.git
cd finlit-chatbot
```

### 2. Install dependencies

```bash
# Install backend dependencies
cd server
npm install

# Install frontend dependencies
cd ../client
npm install
```

### 3. Set up environment variables

Create a `.env` file in the `server/` directory:

```env
PORT=5000
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret_key
ANTHROPIC_API_KEY=your_anthropic_api_key
CLIENT_URL=http://localhost:3000
```

Create a `.env.local` file in the `client/` directory:

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

### 4. Set up the database

```bash
cd server
npm run db:migrate
npm run db:seed   # optional — loads sample data
```

### 5. Run the development servers

```bash
# In one terminal — start backend
cd server
npm run dev

# In another terminal — start frontend
cd client
npm run dev
```

The app will be running at `http://localhost:3000`.

---

## 🤖 Chatbot Behaviour

The chatbot uses a strict system prompt that:

- Keeps all conversations within personal finance topics
- Asks follow-up questions based on previous answers stored in the user's profile
- Never repeats already-answered questions unless asking for updates
- Greets returning users with a contextual check-in message
- Automatically triggers a profile/dashboard update after each meaningful answer

---

## 📁 Project Structure

See [`PROJECT_STRUCTURE.md`](./PROJECT_STRUCTURE.md) for the full folder and file breakdown.

---

## 🗺️ Roadmap

- [ ] Email/OTP login
- [ ] Monthly finance report (PDF export)
- [ ] Shared goals between friends/study groups
- [ ] Bank statement upload and auto-categorization
- [ ] Mobile app (React Native)
- [ ] Multi-language support

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

[MIT](./LICENSE)

---

## 👨‍💻 Author

Built with ❤️ for student financial empowerment.
