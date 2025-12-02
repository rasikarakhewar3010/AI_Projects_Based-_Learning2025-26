# AI_Projects_Based-_Learning2025-26

## 🧩 Code Breaker
**A Logic Game Powered by Prolog, Node.js, and React Native**

![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-1B1F23?style=for-the-badge&logo=expo&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Prolog](https://img.shields.io/badge/Prolog-SWI-blue?style=for-the-badge)

---

### 📖 Overview

**Code Breaker** is an interactive mobile logic game that challenges players to guess a secret 4-digit code. What makes this project unique is its **hybrid architecture**:
- **Logic Engine**: The core game logic (generating codes, evaluating guesses) is written in **Prolog**, a logic programming language.
- **Backend**: A **Node.js (Express)** server acts as the bridge, executing Prolog queries via child processes.
- **Frontend**: A sleek **React Native (Expo)** mobile application provides the user interface.

This project demonstrates the integration of symbolic AI (Prolog) with modern web and mobile technologies.

---

### 📱 Game Preview

<p align="center">
  <img src="https://github.com/user-attachments/assets/c0aea772-4b61-46cd-976d-1e1315cdd3bf" alt="Home Screen" width="200"/>
  <img src="https://github.com/user-attachments/assets/e13a81b8-da47-4353-9c00-844b0d4fb3d7" alt="Code Input Screen" width="200"/>
  <img src="https://github.com/user-attachments/assets/9c9a0e8e-9f3d-421d-b4bd-8994fec45094" alt="Winning Screen" width="200"/>
  <img src="https://github.com/user-attachments/assets/6e94e3ff-c857-4c3a-8c5e-e8d6e7037537" alt="Losing Screen" width="200"/>
</p>

---

### ✨ Key Features

- **🧠 Prolog-Powered Logic**: Utilizes Prolog's pattern matching and constraint solving for game mechanics.
- **⚡ Cross-Platform Mobile App**: Built with React Native and Expo for iOS and Android.
- **� RESTful API**: Node.js backend exposes endpoints to start games and submit guesses.
- **🎨 Clean UI/UX**: Vanilla CSS4 styling for a polished, responsive look.
- **🔄 Unlimited Gameplay**: Play as many rounds as you like with instant feedback.

---

### 🛠️ Tech Stack

| Component | Technology | Description |
|-----------|------------|-------------|
| **Frontend** | React Native (Expo) | Mobile UI and user interaction. |
| **Backend** | Node.js, Express | API server handling HTTP requests. |
| **Logic** | SWI-Prolog | Core game rules and code generation. |
| **Styling** | Vanilla CSS (in JS) | Custom styling for the mobile app. |

---

### ⚙️ Architecture

```mermaid
graph LR
    A[Mobile App (React Native)] -- HTTP POST --> B[Node.js Server]
    B -- Spawns Process --> C[SWI-Prolog]
    C -- JSON Output --> B
    B -- JSON Response --> A
```

---

### 🚀 Installation & Setup

#### Prerequisites
1.  **Node.js**: Install from [nodejs.org](https://nodejs.org/).
2.  **SWI-Prolog**: Install from [swi-prolog.org](https://www.swi-prolog.org/).
    *   *Important*: Ensure `swipl` is in your system PATH or update the path in `backend/server.js`.
3.  **Expo Go**: Install the Expo Go app on your phone (iOS/Android) to test.

#### 1. Backend Setup
Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
```

**Configuration**:
Open `backend/server.js` and verify the `prologExecutable` path:
```javascript
// Update this if your path is different
const prologExecutable = `"C:\\Program Files\\swipl\\bin\\swipl.exe"`;
```

Start the server:
```bash
npm start
# Server runs on http://localhost:3000
```

#### 2. Frontend Setup
Open a new terminal, navigate to the frontend directory, and install dependencies:

```bash
cd frontend
npm install
```

Start the Expo development server:
```bash
npx expo start
```
Scan the QR code with your Expo Go app to play!

---

### � API Reference

The backend exposes the following endpoints:

#### `POST /api/new_game`
Starts a new game session.
- **Response**:
  ```json
  {
    "success": true,
    "gameState": { ... }
  }
  ```

#### `POST /api/guess`
Submits a guess to be checked against the secret code.
- **Body**: `{ "guess": "1234" }`
- **Response**:
  ```json
  {
    "success": true,
    "gameState": {
      "guesses": [ ... ],
      "gameWon": false,
      "message": "..."
    }
  }
  ```

---

### � Folder Structure

```
AI_Projects_Based-_Learning2025-26/
├── backend/
│   ├── codebreaker.pl      # Prolog game logic
│   ├── server.js           # Node.js Express server
│   └── package.json        # Backend dependencies
├── frontend/
│   ├── app/                # Expo Router pages
│   ├── components/         # React Native components
│   └── package.json        # Frontend dependencies
└── README.md               # Project documentation
```

---

### 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

---

### 📄 License

This project is licensed under the **ISC License**.
