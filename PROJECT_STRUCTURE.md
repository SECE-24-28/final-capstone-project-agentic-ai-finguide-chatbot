# 📁 FinLit — Project Structure

```
finlit-chatbot/
│
├── README.md
├── PROJECT_STRUCTURE.md
├── .gitignore
├── LICENSE
│
├── client/                          # Frontend — Next.js / React
│   ├── .env.local
│   ├── next.config.js
│   ├── tailwind.config.js
│   ├── package.json
│   │
│   ├── public/
│   │   ├── logo.svg
│   │   └── favicon.ico
│   │
│   └── src/
│       ├── app/                     # Next.js App Router
│       │   ├── layout.jsx           # Root layout (fonts, providers)
│       │   ├── page.jsx             # Landing / redirect to login
│       │   ├── (auth)/
│       │   │   ├── login/
│       │   │   │   └── page.jsx     # Login page
│       │   │   └── register/
│       │   │       └── page.jsx     # Register page
│       │   └── (app)/               # Protected routes (auth required)
│       │       ├── layout.jsx       # App shell with sidebar/nav
│       │       ├── chat/
│       │       │   └── page.jsx     # Chatbot main page (hero)
│       │       ├── dashboard/
│       │       │   └── page.jsx     # Dashboard with charts
│       │       ├── tracker/
│       │       │   └── page.jsx     # Spending & budget tracker
│       │       └── profile/
│       │           └── page.jsx     # User profile (editable)
│       │
│       ├── components/
│       │   ├── auth/
│       │   │   ├── LoginForm.jsx
│       │   │   └── RegisterForm.jsx
│       │   │
│       │   ├── chat/
│       │   │   ├── ChatWindow.jsx   # Main chat UI
│       │   │   ├── ChatBubble.jsx   # Single message bubble
│       │   │   ├── ChatInput.jsx    # Input + send button
│       │   │   └── TypingIndicator.jsx
│       │   │
│       │   ├── dashboard/
│       │   │   ├── HealthScoreCard.jsx
│       │   │   ├── SpendingPieChart.jsx
│       │   │   ├── BudgetBarChart.jsx
│       │   │   ├── SavingsGoalCard.jsx
│       │   │   └── StatCard.jsx
│       │   │
│       │   ├── tracker/
│       │   │   ├── AddExpenseForm.jsx
│       │   │   ├── ExpenseList.jsx
│       │   │   ├── BudgetSetupForm.jsx
│       │   │   ├── CategoryProgressBar.jsx
│       │   │   └── OverspendAlert.jsx
│       │   │
│       │   ├── profile/
│       │   │   ├── ProfileForm.jsx
│       │   │   └── AvatarUpload.jsx
│       │   │
│       │   └── ui/                  # Reusable UI primitives
│       │       ├── Button.jsx
│       │       ├── Input.jsx
│       │       ├── Modal.jsx
│       │       ├── Badge.jsx
│       │       ├── Spinner.jsx
│       │       └── Navbar.jsx
│       │
│       ├── hooks/
│       │   ├── useAuth.js           # Auth state and actions
│       │   ├── useChat.js           # Chat session logic
│       │   ├── useProfile.js        # Profile fetch/update
│       │   ├── useTransactions.js   # Expense CRUD
│       │   └── useBudget.js         # Budget CRUD
│       │
│       ├── context/
│       │   ├── AuthContext.jsx      # Global auth state
│       │   └── ChatContext.jsx      # Chat history state
│       │
│       ├── lib/
│       │   ├── api.js               # Axios instance + interceptors
│       │   └── utils.js             # Formatters, helpers
│       │
│       └── styles/
│           └── globals.css
│
│
├── server/                          # Backend — Node.js / Express
│   ├── .env
│   ├── package.json
│   ├── server.js                    # Entry point
│   │
│   ├── config/
│   │   ├── db.js                    # Database connection
│   │   └── anthropic.js             # Claude API client setup
│   │
│   ├── routes/
│   │   ├── auth.routes.js           # POST /register, POST /login
│   │   ├── user.routes.js           # GET/PUT /profile
│   │   ├── chat.routes.js           # POST /chat, GET /chat/history
│   │   ├── transaction.routes.js    # CRUD /transactions
│   │   └── budget.routes.js         # CRUD /budgets
│   │
│   ├── controllers/
│   │   ├── auth.controller.js
│   │   ├── user.controller.js
│   │   ├── chat.controller.js       # Handles Claude API calls
│   │   ├── transaction.controller.js
│   │   └── budget.controller.js
│   │
│   ├── middleware/
│   │   ├── auth.middleware.js       # JWT verification
│   │   ├── validate.middleware.js   # Request validation
│   │   └── error.middleware.js      # Global error handler
│   │
│   ├── models/                      # DB models (Sequelize or Mongoose)
│   │   ├── User.model.js            # id, name, email, password, profile_data
│   │   ├── ChatMessage.model.js     # id, user_id, role, content, timestamp
│   │   ├── UserAnswer.model.js      # id, user_id, question_key, answer, updated_at
│   │   ├── Transaction.model.js     # id, user_id, amount, category, date, note
│   │   └── Budget.model.js          # id, user_id, category, limit, month
│   │
│   ├── services/
│   │   ├── chat.service.js          # System prompt builder + Claude call
│   │   ├── profile.service.js       # Auto-update profile from chat answers
│   │   └── analytics.service.js     # Compute health score, budget stats
│   │
│   ├── prompts/
│   │   └── system.prompt.js         # Finance-only system prompt for Claude
│   │
│   └── db/
│       ├── migrations/              # SQL migration files
│       │   ├── 001_create_users.sql
│       │   ├── 002_create_chat_messages.sql
│       │   ├── 003_create_user_answers.sql
│       │   ├── 004_create_transactions.sql
│       │   └── 005_create_budgets.sql
│       └── seeds/
│           └── demo_user.js         # Optional sample data
│
│
└── docs/                            # Extra documentation
    ├── api-endpoints.md             # All REST API routes
    ├── db-schema.md                 # Database table diagrams
    └── chatbot-flow.md              # Conversation flow logic
```

---

## 🔑 Key File Descriptions

| File | Purpose |
|---|---|
| `server/prompts/system.prompt.js` | The Claude system prompt — enforces finance-only scope, loads user profile context, sets greeting logic |
| `server/services/chat.service.js` | Builds message history + calls Claude API; triggers profile auto-update |
| `server/services/profile.service.js` | Parses chatbot answers and writes structured data back to `user_answers` table |
| `client/src/components/chat/ChatWindow.jsx` | Main chatbot UI — the hero component of the whole app |
| `client/src/hooks/useChat.js` | Manages streaming responses, chat history, and return-visit greeting logic |
| `client/src/components/dashboard/` | All chart components — re-render automatically when profile data changes |

---

## 🗄️ Database Tables (summary)

| Table | Stores |
|---|---|
| `users` | Auth credentials + basic profile |
| `user_answers` | Structured answers from chatbot (income, goals, habits) |
| `chat_messages` | Full conversation history per user |
| `transactions` | Individual expense entries |
| `budgets` | Monthly budget limits per category |

---

## 🔌 API Route Summary

| Method | Route | Description |
|---|---|---|
| POST | `/api/auth/register` | Create new account |
| POST | `/api/auth/login` | Login, receive JWT |
| GET | `/api/user/profile` | Get current user profile |
| PUT | `/api/user/profile` | Update profile |
| POST | `/api/chat/message` | Send message, get AI response |
| GET | `/api/chat/history` | Fetch past chat messages |
| GET | `/api/transactions` | List all transactions |
| POST | `/api/transactions` | Add new expense |
| PUT | `/api/transactions/:id` | Edit expense |
| DELETE | `/api/transactions/:id` | Delete expense |
| GET | `/api/budgets` | Get all budgets |
| POST | `/api/budgets` | Set category budget |
| PUT | `/api/budgets/:id` | Update budget limit |
