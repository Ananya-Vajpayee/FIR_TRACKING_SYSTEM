# 🚀 Start Guide - FIR Tracking System

## Installation Order (Copy-Paste in VS Code Terminal)
### Step 1: Install Backend Dependencies
```bash
cd backend
npm install
```

### Step 2: Start MongoDB
Open a new terminal and run:
```bash
mongod
```
Keep this terminal running!

### Step 3: Start Backend Server
In another terminal:
```bash
cd backend
npm start
```
Backend will run on http://localhost:5000

### Step 4: Install Frontend Dependencies
Open a new terminal:
```bash
cd frontend
npm install
```

### Step 5: Start Frontend
```bash
npm start
```
Frontend will open automatically at http://localhost:3000

## 🎯 Testing the Application

### Create Admin Account
1. Go to http://localhost:3000/register
2. Fill in:
   - Name: Admin User
   - Email: admin@test.com
   - Phone: 1234567890
   - Password: admin123
   - Account Type: **Admin**
3. Click "Create Account"

### Create Client Account
1. Logout or open incognito window
2. Go to http://localhost:3000/register
3. Fill in:
   - Name: John Doe
   - Email: client@test.com
   - Phone: 9876543210
   - Password: client123
   - Account Type: **Client**
4. Click "Create Account"

### Test Client Flow
1. Login as client (client@test.com / client123)
2. Click "File New FIR"
3. Fill in:
   - Title: "Laptop Theft Report"
   - Category: Theft
   - Description: "My laptop was stolen from my car"
4. Submit FIR
5. View the FIR in your dashboard

### Test Admin Flow
1. Login as admin (admin@test.com / admin123)
2. See the new FIR in the admin dashboard
3. Click "Edit" icon on the FIR
4. Update:
   - Inspector Name: "Officer Smith"
   - Badge Number: "BADGE12345"
   - Status: "Under Investigation"
   - Priority: "High"
   - Mark documents as signed
5. Click "Save"

### Test Real-Time Updates
1. Keep both client and admin sessions open in different browsers
2. Update FIR from admin panel
3. Watch client dashboard update in real-time! 🎉

## 📁 VS Code Folder Structure

Open the project in VS Code. You'll see:

```
fir-tracking-system/
├── 📂 backend/
│   ├── 📂 config/
│   │   └── db.js (database connection)
│   ├── 📂 models/
│   │   ├── User.js (user schema)
│   │   └── FIR.js (FIR schema)
│   ├── 📂 middleware/
│   │   └── auth.js (JWT authentication)
│   ├── 📂 routes/
│   │   ├── auth.js (login/register routes)
│   │   └── firs.js (FIR CRUD routes)
│   ├── .env (environment variables)
│   ├── server.js (main server file - START HERE)
│   └── package.json
│
└── 📂 frontend/
    ├── 📂 src/
    │   ├── 📂 components/ (all React components)
    │   ├── 📂 context/ (AuthContext)
    │   ├── 📂 services/ (API and Socket)
    │   ├── App.js (main app with routing)
    │   ├── index.js (entry point)
    │   └── index.css (global styles)
    └── package.json
```

## ⚡ Development Tips

### Hot Reload
- Frontend auto-reloads on file changes
- Backend requires restart (use `nodemon` for auto-restart)

### Install nodemon (optional):
```bash
cd backend
npm install -D nodemon
# Then use: npm run dev
```

### Debug Tips
- Check browser console for frontend errors (F12)
- Check terminal for backend errors
- Use React DevTools for component inspection

## 🎨 Customization Guide

### Change Colors
Edit `frontend/src/index.css`:
```css
:root {
  --primary-orange: #your-color;
  --secondary-orange: #your-color;
}
```

### Modify FIR Categories
Edit `backend/models/FIR.js`:
```javascript
category: {
  enum: ['Your', 'Custom', 'Categories'],
}
```

### Add New Status
Edit both:
- `backend/models/FIR.js`
- `frontend/src/components/FIRDetail.js`

## 🐛 Common Issues

### Issue: MongoDB not starting
**Solution**: Install MongoDB from https://www.mongodb.com/try/download/community

### Issue: Port 5000 already in use
**Solution**: Change PORT in `backend/.env` to 5001

### Issue: Cannot connect to MongoDB
**Solution**: Check if mongod is running in terminal

### Issue: Real-time updates not working
**Solution**: 
1. Check if backend is running
2. Open browser console
3. Look for Socket connection messages

## 🎓 Learning Path

### For Beginners:
1. Start by reading `backend/server.js`
2. Understand routes in `backend/routes/`
3. Check models in `backend/models/`
4. Look at `frontend/src/App.js` for routing
5. Explore components one by one

### Key Files to Understand:
1. **server.js**: Backend entry, Socket setup
2. **auth.js** (middleware): JWT authentication
3. **AuthContext.js**: User state management
4. **socket.js**: Real-time communication
5. **FIRDetail.js**: Most complex component

## 📚 Tech Stack Explained

- **React**: Frontend UI library
- **Express**: Backend web framework
- **MongoDB**: NoSQL database
- **Mongoose**: MongoDB object modeling
- **Socket.IO**: Real-time bidirectional communication
- **JWT**: Secure authentication tokens
- **Framer Motion**: Animation library
- **Axios**: HTTP client
- **React Router**: Navigation
- **React Hot Toast**: Notifications

## 🎉 You're All Set!

