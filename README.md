 # **Yourchats – MERN Realtime Chat Application**

A full-stack real-time chat application built using the **MERN stack**, **Socket.io**, **Cloudinary**, and **JWT Authentication**.
Supports **1-to-1 messaging**, **image sharing**, **online users status**, and **persistent sessions** using cookies.

---
Live link :  https://yourchats.vercel.app/

## **🚀 Features**

### **Authentication**

* Login, Signup, Logout
* JWT-based authentication (stored in HTTP-only cookies)
* Protected routes for messages and user data

### **Realtime Messaging**

* Socket.io integration
* Realtime message send & receive
* Online users tracking
* New message event broadcasts

### **Media Upload**

* Cloudinary integration for image uploads in messages
* Profile picture upload

### **User Interface**

* Clean and responsive UI
* Sidebar showing user list and online users
* Chat UI with message bubbles and timestamps

### **Database**

* MongoDB for storing:

  * Users
  * Messages
  * Profile pictures

---

## **🛠 Tech Stack**

### **Frontend**

* React
* Zustand (global state management)
* Axios
* Socket.io-client
* Vite

### **Backend**

* Node.js
* Express.js
* MongoDB + Mongoose
* Socket.io
* Cloudinary SDK
* JWT authentication
* Cookie-parser

---

## **📂 Project Structure**

```
backend/
│── controllers/
│── lib/
│── middleware/
│── models/
│── routes/
│── server.js

frontend/
│── src/
│   ├── components/
│   ├── pages/
│   ├── store/
│   ├── lib/
│   └── App.jsx
│── vite.config.js
```

---

## **🔧 Environment Variables**

Create a `.env` file inside backend:

```
PORT=5001
MONGODB_URL=your_mongodb_connection_string
JWT_SECRET=your_secret_key

CLOUDINARY_CLOUD_NAME=xxxx
CLOUDINARY_API_KEY=xxxx
CLOUDINARY_API_SECRET=xxxx
```

---

## **⚙️ Installation & Setup**

### **1. Clone the repository**

```
git clone https://github.com/your-username/messer-chat-app.git
cd messer-chat-app
```

---

### **2. Backend Setup**

```
cd backend
npm install
npm start
```

---

### **3. Frontend Setup**

```
cd frontend
npm install
npm run dev
```

---

## **🌐 Deployment**

### **Frontend Deployment – Vercel**

* Deploy Vite React app
* Add environment variables
* Update backend base URL in Axios

### **Backend Deployment – Render / Railway**

* Create a web service
* Set environment variables
* Use Node start command:

  ```
  node server.js
  ```

### **Socket.io Note**

Vercel DOES NOT support backend WebSockets.
Use **Render**, **Railway**, **DigitalOcean**, or **AWS** for Socket.io server.

---

## **💬 API Endpoints**

### **Authentication Routes**

| Method | Endpoint           | Description          |
| ------ | ------------------ | -------------------- |
| POST   | `/api/auth/signup` | Create new user      |
| POST   | `/api/auth/login`  | Login user           |
| POST   | `/api/auth/logout` | Logout user          |
| GET    | `/api/auth/check`  | Check logged-in user |

---

### **Message Routes**

| Method | Endpoint                 | Description                |
| ------ | ------------------------ | -------------------------- |
| GET    | `/api/messages/users`    | List all users except self |
| GET    | `/api/messages/:id`      | Get chat history           |
| POST   | `/api/messages/send/:id` | Send message               |

---

## **💡 Realtime Events (Socket.io)**

### **Client → Server**

* Connect with:

  ```
  io(BASE_URL, { query: { userId } })
  ```

### **Server → Clients**

* `getOnlineUsers` → list of online users
* `newMessage` → new incoming message

---

 
## **🤝 Contributing**

Pull requests are welcome.
For major changes, open an issue first to discuss what you want to change.

---
 
