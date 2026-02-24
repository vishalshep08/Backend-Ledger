# 🏦 Backend Ledger – Banking Transaction System

A production-style **Bank Transaction & Ledger Management System** built using **Node.js, Express, and MongoDB**. This project simulates real-world banking architecture with secure transactions, double-entry ledger handling, MongoDB ACID transactions, and idempotency validation.

---

## 🚀 Features

### 🔐 Authentication
- User Registration
- Login with JWT
- Secure password hashing using bcrypt
- Token blacklist for logout security

### 💳 Account Management
- Create user account
- Get account balance
- View all accounts
- Account status handling

### 💸 Transaction System
- Initial system funding
- Peer-to-peer money transfers
- Double-entry ledger model
- Idempotency key validation (prevents duplicate transactions)
- MongoDB session-based ACID transactions
- Automatic rollback on failure

### 📧 Email Notifications
- Registration confirmation emails
- Transaction confirmation emails using Nodemailer

---

## 🧠 Architecture Highlights
- ACID compliant transactions using MongoDB sessions
- Double-entry ledger implementation
- Idempotent API design
- Clean folder structure (MVC pattern)
- Error handling & rollback mechanism
- Production-style backend structuring

---

## 🛠️ Tech Stack
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT (jsonwebtoken)
- bcrypt
- Nodemailer

---

## 📂 Project Structure

```
backend-ledger/
│
├── src/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── services/
│   └── app.js
│
├── .gitignore
├── .env                  ← (not committed, add manually)
├── package.json
├── package-lock.json
├── server.js
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/vishalshep08/Backend-Ledger.git
cd Backend-Ledger
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Create `.env` File

Create a `.env` file in the root directory:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/backend-ledger
JWT_SECRET=your_jwt_secret
EMAIL_USER=your_email
EMAIL_PASS=your_email_password
```

### 4️⃣ Start the Server

```bash
npm run dev
```

Server will run on: `http://localhost:3000`

---

## 📌 API Endpoints

### 🔐 Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register user |
| POST | `/api/auth/login` | Login user |
| POST | `/api/auth/logout` | Logout user |

---

### 💳 Accounts

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/accounts` | Create account |
| GET | `/api/accounts` | Get all accounts |
| GET | `/api/accounts/balance/:id` | Get account balance |

---

### 💸 Transactions

#### 1️⃣ Initial Funds (System Credit)

```http
POST /api/transactions/system/initial-funds
```

```json
{
  "toAccount": "accountId",
  "amount": 50000,
  "idempotencyKey": "unique-key"
}
```

---

#### 2️⃣ Transfer Money

```http
POST /api/transactions
```

```json
{
  "fromAccount": "accountId1",
  "toAccount": "accountId2",
  "amount": 1000,
  "idempotencyKey": "unique-key"
}
```

---

## 🔄 Idempotency Handling

If the same request is sent again with the same `idempotencyKey`, the system:
- Prevents duplicate transactions
- Returns already processed transaction
- Ensures financial safety and consistency

---

## 🗄️ Database Collections
- `users`
- `accounts`
- `transactions`
- `ledgers`
- `tokenblacklists`

---

## 🎯 What This Project Demonstrates
- Real-world fintech backend architecture
- MongoDB transaction handling (ACID compliance)
- Idempotent API development
- Secure authentication & authorization
- Double-entry ledger implementation
- Clean and scalable backend design

---

## 📌 Future Improvements
- Swagger API documentation
- Rate limiting
- Role-based access control
- Docker deployment
- Unit & integration testing

---

- GitHub: [https://github.com/vishalshep08](https://github.com/vishalshep08)
- LinkedIn: [https://linkedin.com/vishal-shep](https://linkedin.com/vishal-shep)

---

⭐ If you found this project useful, consider giving it a star!
