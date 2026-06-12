# 🗂️ FinGuide AI — Complete Project Structure

```
finguide-ai/
│
├── main.py
├── requirements.txt
├── .env
├── docker-compose.yml
├── README.md
├── .gitignore
│
├── client/                                         # ── FRONTEND (React + Tailwind) ──
│   ├── package.json
│   ├── tailwind.config.js
│   ├── vite.config.js
│   ├── .env.local
│   │
│   ├── public/
│   │   ├── logo.svg
│   │   └── favicon.ico
│   │
│   └── src/
│       ├── main.jsx
│       ├── App.jsx
│       │
│       ├── pages/
│       │   ├── Landing.jsx
│       │   ├── Login.jsx
│       │   ├── Register.jsx
│       │   ├── ForgotPassword.jsx
│       │   ├── Chat.jsx
│       │   ├── Dashboard.jsx
│       │   ├── Tracker.jsx
│       │   ├── Budget.jsx
│       │   ├── Goals.jsx
│       │   ├── Timeline.jsx
│       │   ├── Profile.jsx
│       │   └── admin/
│       │       ├── AdminDashboard.jsx
│       │       ├── AdminUsers.jsx
│       │       ├── AdminChats.jsx
│       │       └── AdminKnowledge.jsx
│       │
│       ├── components/
│       │   ├── auth/
│       │   │   ├── LoginForm.jsx
│       │   │   ├── RegisterForm.jsx
│       │   │   └── ForgotPasswordForm.jsx
│       │   │
│       │   ├── chat/
│       │   │   ├── ChatWindow.jsx
│       │   │   ├── ChatBubble.jsx
│       │   │   ├── ChatInput.jsx
│       │   │   ├── TypingIndicator.jsx
│       │   │   └── OnboardingFlow.jsx
│       │   │
│       │   ├── dashboard/
│       │   │   ├── StatCard.jsx
│       │   │   ├── HealthScoreCard.jsx
│       │   │   ├── SpendingTrendChart.jsx
│       │   │   ├── SavingsGrowthChart.jsx
│       │   │   ├── ExpensePieChart.jsx
│       │   │   ├── BudgetUsageChart.jsx
│       │   │   ├── GoalProgressChart.jsx
│       │   │   └── InsightsPanel.jsx
│       │   │
│       │   ├── tracker/
│       │   │   ├── ExpenseList.jsx
│       │   │   ├── ExpenseCard.jsx
│       │   │   ├── DailyView.jsx
│       │   │   ├── WeeklyView.jsx
│       │   │   └── MonthlyView.jsx
│       │   │
│       │   ├── budget/
│       │   │   ├── BudgetCard.jsx
│       │   │   ├── BudgetSetForm.jsx
│       │   │   ├── CategoryProgressBar.jsx
│       │   │   └── OverspendAlert.jsx
│       │   │
│       │   ├── goals/
│       │   │   ├── GoalCard.jsx
│       │   │   ├── AddGoalForm.jsx
│       │   │   └── GoalProgressBar.jsx
│       │   │
│       │   ├── timeline/
│       │   │   ├── TimelineList.jsx
│       │   │   └── TimelineEvent.jsx
│       │   │
│       │   ├── profile/
│       │   │   ├── ProfileForm.jsx
│       │   │   └── ChangePasswordForm.jsx
│       │   │
│       │   └── ui/
│       │       ├── Button.jsx
│       │       ├── Input.jsx
│       │       ├── Modal.jsx
│       │       ├── Badge.jsx
│       │       ├── Spinner.jsx
│       │       ├── Navbar.jsx
│       │       ├── Sidebar.jsx
│       │       └── ProtectedRoute.jsx
│       │
│       ├── hooks/
│       │   ├── useAuth.js
│       │   ├── useChat.js
│       │   ├── useProfile.js
│       │   ├── useTransactions.js
│       │   ├── useBudget.js
│       │   ├── useGoals.js
│       │   └── useInsights.js
│       │
│       ├── context/
│       │   ├── AuthContext.jsx
│       │   └── ChatContext.jsx
│       │
│       ├── lib/
│       │   ├── api.js
│       │   ├── utils.js
│       │   └── constants.js
│       │
│       └── styles/
│           └── index.css
│
│
└── server/                                         # ── BACKEND (FastAPI + Python) ──
    ├── main.py
    ├── requirements.txt
    ├── .env
    │
    ├── core/
    │   ├── config.py
    │   ├── database.py
    │   ├── security.py
    │   └── dependencies.py
    │
    ├── routers/
    │   ├── auth.py
    │   ├── users.py
    │   ├── chat.py
    │   ├── transactions.py
    │   ├── budgets.py
    │   ├── goals.py
    │   ├── insights.py
    │   ├── timeline.py
    │   ├── health_score.py
    │   └── admin.py
    │
    ├── models/
    │   ├── __init__.py
    │   ├── user.py
    │   ├── profile.py
    │   ├── expense.py
    │   ├── budget.py
    │   ├── goal.py
    │   ├── health_score.py
    │   ├── insight.py
    │   ├── chat_message.py
    │   └── timeline.py
    │
    ├── schemas/
    │   ├── __init__.py
    │   ├── auth.py
    │   ├── user.py
    │   ├── chat.py
    │   ├── transaction.py
    │   ├── budget.py
    │   ├── goal.py
    │   ├── insight.py
    │   └── health_score.py
    │
    ├── services/
    │   ├── auth_service.py
    │   ├── chat_service.py
    │   ├── memory_service.py
    │   ├── insight_service.py
    │   ├── health_score_service.py
    │   ├── goal_service.py
    │   ├── timeline_service.py
    │   └── admin_service.py
    │
    ├── ai/
    │   ├── __init__.py
    │   ├── agent.py
    │   │
    │   ├── prompts/
    │   │   ├── system_prompt.py
    │   │   ├── onboarding_prompt.py
    │   │   ├── returning_prompt.py
    │   │   ├── insight_prompt.py
    │   │   └── extraction_prompt.py
    │   │
    │   ├── rag/
    │   │   ├── rag_pipeline.py
    │   │   ├── vector_store.py
    │   │   ├── embeddings.py
    │   │   └── ingest.py
    │   │
    │   ├── memory/
    │   │   ├── extractor.py
    │   │   └── updater.py
    │   │
    │   └── intent/
    │       ├── classifier.py
    │       └── router.py
    │
    ├── knowledge_base/
    │   ├── raw/
    │   │   ├── mutual_funds.pdf
    │   │   ├── credit_score.pdf
    │   │   ├── sip_basics.pdf
    │   │   ├── budgeting_101.pdf
    │   │   └── inflation_guide.pdf
    │   └── faiss_index/
    │       ├── index.faiss
    │       └── index.pkl
    │
    ├── migrations/
    │   ├── env.py
    │   ├── script.py.mako
    │   └── versions/
    │       ├── 001_create_users.py
    │       ├── 002_create_profiles.py
    │       ├── 003_create_expenses.py
    │       ├── 004_create_budgets.py
    │       ├── 005_create_goals.py
    │       ├── 006_create_health_score.py
    │       ├── 007_create_insights.py
    │       ├── 008_create_chat_history.py
    │       └── 009_create_timeline.py
    │
    └── tests/
        ├── test_auth.py
        ├── test_chat.py
        ├── test_memory_extractor.py
        ├── test_health_score.py
        └── test_goals.py
```

---

## 🖥️ Frontend File Descriptions  `.jsx / .js`

### `src/pages/`

| File | Purpose |
|---|---|
| `Landing.jsx` | Public home page — intro to FinGuide AI, login/register CTA |
| `Login.jsx` | Login page |
| `Register.jsx` | Registration page |
| `ForgotPassword.jsx` | Password reset request page |
| `Chat.jsx` | **Hero page** — AI chatbot, main feature of the app |
| `Dashboard.jsx` | Overview — score card, all charts, AI insights panel |
| `Tracker.jsx` | Daily / weekly / monthly spending tracker |
| `Budget.jsx` | Category budget setup and progress monitoring |
| `Goals.jsx` | Financial goals list with progress and predicted ETA |
| `Timeline.jsx` | Chronological financial event history |
| `Profile.jsx` | Editable user profile page |
| `admin/AdminDashboard.jsx` | Admin overview — platform usage stats |
| `admin/AdminUsers.jsx` | Admin — view and manage all users |
| `admin/AdminChats.jsx` | Admin — view chat statistics and logs |
| `admin/AdminKnowledge.jsx` | Admin — manage RAG knowledge base documents |

---

### `src/components/auth/`

| File | Purpose |
|---|---|
| `LoginForm.jsx` | Email + password form with validation |
| `RegisterForm.jsx` | Name, email, password, confirm password form |
| `ForgotPasswordForm.jsx` | Email input to trigger reset link |

---

### `src/components/chat/`

| File | Purpose |
|---|---|
| `ChatWindow.jsx` | Full chat UI container — manages message list and scroll |
| `ChatBubble.jsx` | Single message bubble — user (right) or AI (left) |
| `ChatInput.jsx` | Text input box with send button |
| `TypingIndicator.jsx` | Animated dots shown while AI is responding |
| `OnboardingFlow.jsx` | Guided first-login question sequence UI |

---

### `src/components/dashboard/`

| File | Purpose |
|---|---|
| `StatCard.jsx` | Single stat card — Income / Expenses / Savings / Score |
| `HealthScoreCard.jsx` | Big circular score display (e.g. 84 / 100) |
| `SpendingTrendChart.jsx` | Line chart — monthly spending over time |
| `SavingsGrowthChart.jsx` | Line/area chart — savings growth over time |
| `ExpensePieChart.jsx` | Pie chart — expense breakdown by category |
| `BudgetUsageChart.jsx` | Bar chart — budget vs actual per category |
| `GoalProgressChart.jsx` | Progress bars for all active goals |
| `InsightsPanel.jsx` | List of latest AI-generated personalized recommendations |

---

### `src/components/tracker/`

| File | Purpose |
|---|---|
| `ExpenseList.jsx` | Full list of expense entries with filter/sort |
| `ExpenseCard.jsx` | Single expense row — amount, category, date, note |
| `DailyView.jsx` | Expenses grouped by today |
| `WeeklyView.jsx` | Expenses grouped by current week |
| `MonthlyView.jsx` | Expenses grouped by current month with totals |

---

### `src/components/budget/`

| File | Purpose |
|---|---|
| `BudgetCard.jsx` | Single category card — e.g. Food ₹2400 / ₹3000 — 80% |
| `BudgetSetForm.jsx` | Form to set or update a category budget limit |
| `CategoryProgressBar.jsx` | Colored progress bar (green → yellow → red) |
| `OverspendAlert.jsx` | Warning banner when a category budget is exceeded |

---

### `src/components/goals/`

| File | Purpose |
|---|---|
| `GoalCard.jsx` | Goal name, target amount, saved amount, % done, ETA |
| `AddGoalForm.jsx` | Form to create a new financial goal |
| `GoalProgressBar.jsx` | Visual progress bar for a single goal |

---

### `src/components/timeline/`

| File | Purpose |
|---|---|
| `TimelineList.jsx` | Full vertical timeline of financial events |
| `TimelineEvent.jsx` | Single event entry — date, icon, description |

---

### `src/components/profile/`

| File | Purpose |
|---|---|
| `ProfileForm.jsx` | Editable fields — name, age, income, goals, risk level, language |
| `ChangePasswordForm.jsx` | Current password + new password + confirm form |

---

### `src/components/ui/`

| File | Purpose |
|---|---|
| `Button.jsx` | Reusable button — primary, secondary, danger variants |
| `Input.jsx` | Styled text input with label and error state |
| `Modal.jsx` | Generic modal overlay wrapper |
| `Badge.jsx` | Small label chip — category tags, status indicators |
| `Spinner.jsx` | Loading spinner for async states |
| `Navbar.jsx` | Top navigation bar with user avatar and logout |
| `Sidebar.jsx` | Side navigation — links to all pages |
| `ProtectedRoute.jsx` | HOC that redirects to `/login` if user is not authenticated |

---

### `src/hooks/`

| File | Purpose |
|---|---|
| `useAuth.js` | Auth state — user object, login, logout, register actions |
| `useChat.js` | Chat session — message history, send message, streaming response |
| `useProfile.js` | Fetch and update user profile |
| `useTransactions.js` | Fetch, add, edit, delete expense entries |
| `useBudget.js` | Fetch, set, update category budgets |
| `useGoals.js` | Fetch, create, update financial goals |
| `useInsights.js` | Fetch AI-generated recommendations |

---

### `src/context/`

| File | Purpose |
|---|---|
| `AuthContext.jsx` | Global auth state provider — wraps entire app |
| `ChatContext.jsx` | Global chat history state — persists across page navigation |

---

### `src/lib/`

| File | Purpose |
|---|---|
| `api.js` | Axios instance with base URL and JWT auth interceptor |
| `utils.js` | Currency formatter (₹), date helpers, percentage calculator |
| `constants.js` | Expense categories, score thresholds, budget color rules |

---

## 🐍 Backend File Descriptions  `.py`

### Root

| File | Purpose |
|---|---|
| `main.py` | FastAPI app — registers all routers, CORS config, startup events |
| `requirements.txt` | All Python package dependencies |
| `.env` | DB URL, JWT secret, API keys (never commit to git) |

---

### `core/`

| File | Purpose |
|---|---|
| `config.py` | Loads `.env` variables using Pydantic `BaseSettings` |
| `database.py` | SQLAlchemy engine, `SessionLocal`, `Base` — PostgreSQL connection |
| `security.py` | JWT token creation and verification, bcrypt password hashing |
| `dependencies.py` | `get_db()` session injector, `get_current_user()` auth guard |

---

### `routers/`

| File | Route Prefix | Purpose |
|---|---|---|
| `auth.py` | `/auth` | POST `/register`, POST `/login`, POST `/forgot-password` |
| `users.py` | `/users` | GET `/profile`, PUT `/profile` |
| `chat.py` | `/chat` | POST `/message`, GET `/history` |
| `transactions.py` | `/transactions` | GET, POST, PUT `/{id}`, DELETE `/{id}` |
| `budgets.py` | `/budgets` | GET, POST, PUT `/{id}` |
| `goals.py` | `/goals` | GET, POST, PUT `/{id}` |
| `insights.py` | `/insights` | GET — returns latest AI recommendations |
| `timeline.py` | `/timeline` | GET — returns all financial events |
| `health_score.py` | `/health-score` | GET — returns score + breakdown |
| `admin.py` | `/admin` | GET `/users`, GET `/analytics`, PUT `/knowledge` |

---

### `models/`  *(SQLAlchemy ORM)*

| File | Table | Key Columns |
|---|---|---|
| `user.py` | `users` | id, name, email, password_hash, role, created_at |
| `profile.py` | `profiles` | user_id, age, gender, education, occupation, income, allowance, risk_level, language |
| `expense.py` | `expenses` | id, user_id, amount, category, date, source, note |
| `budget.py` | `budgets` | id, user_id, category, limit_amount, month |
| `goal.py` | `goals` | id, user_id, goal_name, target_amount, current_amount, target_date, status |
| `health_score.py` | `financial_health` | user_id, score, savings_rate, budget_discipline, debt_level, goal_progress, last_updated |
| `insight.py` | `insights` | id, user_id, recommendation, type, created_at, is_read |
| `chat_message.py` | `chat_history` | id, user_id, role, message, timestamp |
| `timeline.py` | `financial_timeline` | id, user_id, event_type, description, amount, date |

---

### `schemas/`  *(Pydantic)*

| File | Classes |
|---|---|
| `auth.py` | `RegisterRequest`, `LoginRequest`, `TokenResponse` |
| `user.py` | `UserProfileResponse`, `UpdateProfileRequest` |
| `chat.py` | `ChatMessageRequest`, `ChatMessageResponse` |
| `transaction.py` | `CreateTransactionRequest`, `TransactionResponse` |
| `budget.py` | `SetBudgetRequest`, `BudgetResponse` |
| `goal.py` | `CreateGoalRequest`, `GoalResponse`, `GoalProgressResponse` |
| `insight.py` | `InsightResponse` |
| `health_score.py` | `HealthScoreResponse`, `ScoreBreakdown` |

---

### `services/`

| File | Purpose |
|---|---|
| `auth_service.py` | Registration, login validation, password reset logic |
| `chat_service.py` | Build message history, call AI agent, trigger memory extraction |
| `memory_service.py` | Coordinate extractor → DB write → dashboard refresh |
| `insight_service.py` | Generate personalized AI suggestions from stored user data |
| `health_score_service.py` | Calculate 0–100 score from savings rate, budget discipline, debt, goal progress |
| `goal_service.py` | Track goal progress, predict completion date from savings rate |
| `timeline_service.py` | Auto-log financial events (income, goal started, purchase made) |
| `admin_service.py` | Platform stats, user management, knowledge base updates |

---

### `ai/`

| File | Purpose |
|---|---|
| `agent.py` | Main orchestrator — receives message, detects intent, routes to correct handler |

#### `ai/prompts/`

| File | Purpose |
|---|---|
| `system_prompt.py` | Core AI persona — finance-only scope, tone, language rules |
| `onboarding_prompt.py` | First-login question sequence (income, goals, habits, debt) |
| `returning_prompt.py` | Return visit greeting — "Hey 👋 Any updates or doubts?" |
| `insight_prompt.py` | Prompt to generate personalized insights from financial data |
| `extraction_prompt.py` | Prompt to extract structured data from free-text messages |

#### `ai/rag/`

| File | Purpose |
|---|---|
| `rag_pipeline.py` | LangChain RAG chain — retriever + LLM |
| `vector_store.py` | Load and query FAISS index |
| `embeddings.py` | Embedding model setup |
| `ingest.py` | One-time script — loads PDFs → builds FAISS index |

#### `ai/memory/`

| File | Purpose |
|---|---|
| `extractor.py` | Parses "I spent ₹1000 on food" → `{category: food, amount: 1000}` |
| `updater.py` | Writes extracted data to correct DB table |

#### `ai/intent/`

| File | Purpose |
|---|---|
| `classifier.py` | Classifies message as `finance_question` / `financial_update` / `off_topic` |
| `router.py` | Routes intent to RAG, memory extractor, or rejection reply |

---

### `migrations/`  *(Alembic)*

| File | Purpose |
|---|---|
| `env.py` | Alembic environment — connects to SQLAlchemy models |
| `script.py.mako` | Migration file template |
| `versions/001_create_users.py` | Create `users` table |
| `versions/002_create_profiles.py` | Create `profiles` table |
| `versions/003_create_expenses.py` | Create `expenses` table |
| `versions/004_create_budgets.py` | Create `budgets` table |
| `versions/005_create_goals.py` | Create `goals` table |
| `versions/006_create_health_score.py` | Create `financial_health` table |
| `versions/007_create_insights.py` | Create `insights` table |
| `versions/008_create_chat_history.py` | Create `chat_history` table |
| `versions/009_create_timeline.py` | Create `financial_timeline` table |

---

### `tests/`

| File | What it tests |
|---|---|
| `test_auth.py` | Register, login, token validation |
| `test_chat.py` | Message routing, AI response, history storage |
| `test_memory_extractor.py` | NLP extraction accuracy ("I spent ₹500" → correct category + amount) |
| `test_health_score.py` | Score calculation across different financial profiles |
| `test_goals.py` | Goal progress tracking and ETA prediction |

---

## 📦 `requirements.txt`

```
fastapi
uvicorn
sqlalchemy
alembic
psycopg2-binary
pydantic[email]
pydantic-settings
python-jose[cryptography]
passlib[bcrypt]
python-dotenv
langchain
langchain-community
faiss-cpu
openai
google-generativeai
sentence-transformers
pypdf
pytest
httpx
```
