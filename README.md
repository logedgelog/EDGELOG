# EdgeLog Trading Journal

A sophisticated, single-file HTML trading journal for futures traders using ICT methodology. Track trades, analyze performance, and optimize your trading edge with Firebase backend and GitHub Pages hosting.

## 🎯 Features

### Core Trading Features
- **ICT Trade Tracking** – Log trades with setup names, entry/exit, stop loss, targets
- **Multi-Instrument Support** – MNQ, NQ, MES, ES with per-instrument P&L calculations
- **Advanced Analytics** – R-Multiple distribution, MAE/MFE tracking, monthly calendar heatmap
- **Trade Grading** – Confluence-based trade quality scoring (MSS, OB, FVG grading)
- **Psychology Tab** – Discipline score, emotion tracking, behavioral pattern analysis
- **PDF Reports** – Export monthly/weekly reports and performance summaries

### Authentication & Security
- **Google OAuth** – Seamless sign-in with Google accounts
- **Email/Password Auth** – Traditional email signup and login
- **Mobile Support** – Full iOS Safari and Android browser compatibility
- **Firebase Firestore** – Cloud-based data with automatic sync

### Admin Features
- **User Management** – View all users, monitor login activity
- **Dashboard Viewer** – Admin can view any user's complete trading dashboard
- **Session Tracking** – Detailed login history with device/timezone metadata
- **Performance Monitoring** – Track user trading metrics and activity

### UI/UX
- **7 Themes** – Dark/light variants with localStorage persistence
- **Logo Branding** – Custom logo in header and PDF exports
- **Responsive Design** – Works on desktop, tablet, and mobile
- **Keyboard Shortcuts** – Quick navigation (N=New Trade, D=Dashboard, Esc=Close, etc.)

## 🚀 Quick Start

### Prerequisites
- GitHub account
- Firebase project with Firestore and Authentication enabled
- Modern web browser

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/edgelog.git
   cd edgelog
   ```

2. **Configure Firebase**
   Update `firebase-config.js` with your Firebase credentials:
   ```javascript
   const FIREBASE_CONFIG = {
     apiKey: "YOUR_API_KEY",
     authDomain: "your-project.firebaseapp.com",
     projectId: "your-project",
     storageBucket: "your-project.appspot.com",
     messagingSenderId: "YOUR_SENDER_ID",
     appId: "YOUR_APP_ID"
   };
   const ADMIN_EMAIL = "your-admin@email.com";
   ```

3. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)
   - Save

4. **Access Your App**
   - Your site will be available at: `https://yourusername.github.io/edgelog`
   - Share the link with users

### First Run

1. Navigate to `https://yourusername.github.io/edgelog/login.html`
2. Sign in with Google or create email/password account
3. Click "EdgeLog" link to access your trading journal
4. Start logging trades!

## 📁 File Structure

```
edgelog/
├── index.html                Landing/home page
├── login.html               Authentication page (Google + Email/Password)
├── EdgeLog_v61.html         Main trading journal application
├── admin.html               Admin dashboard (users, activity, metrics)
├── firebase-config.js       Firebase credentials (UPDATE THIS!)
└── README.md                This file
```

## 🔐 Authentication

### Google OAuth
- One-click sign-in
- Works on all devices
- No password to remember

### Email/Password
- Traditional signup/login
- Firebase handles security (bcrypt hashing)
- Minimum 6 characters

### Admin Access
- Sign in as configured ADMIN_EMAIL
- Access admin.html for user management
- View any user's complete trading dashboard

## 📊 Data Structure (Firestore)

All user data stored in Firestore (cloud-based, not local):

```
users/{uid}
├── displayName: string
├── email: string
├── photoURL: string
├── createdAt: timestamp
├── lastLogin: timestamp
├── loginCount: number
├── trades: [array of trade objects]
└── loginHistory (subcollection)
```

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **N** | New trade |
| **D** | Dashboard |
| **T** | Trades |
| **A** | Analytics |
| **M** | Mind/Psychology |
| **?** | Keyboard shortcuts help |
| **Esc** | Close any modal |

## 🔐 Security Notes

✅ **Passwords** – Firebase Auth handles hashing, never plaintext
✅ **HTTPS** – GitHub Pages provides automatic HTTPS
✅ **Authentication** – OAuth 2.0 for Google, bcrypt for passwords
✅ **Data** – All data encrypted in Firestore

## 🔧 Customization

### Change Admin Email
Edit `firebase-config.js`:
```javascript
const ADMIN_EMAIL = "your-admin-email@example.com";
```

### Add Your Logo
Replace the base64 data URI in `EdgeLog_v61.html` with your own PNG logo.

## 📱 Mobile Support

- **iOS Safari** – Full support
- **Android Chrome** – Full support
- **Android Firefox** – Full support
- **iPad** – Full support with responsive layout

## 🚀 Deploy Changes

```bash
# Make changes locally
git add .
git commit -m "feat: describe your change"
git push origin main

# GitHub Pages auto-updates within seconds
```

## 📞 Support

For issues:
1. Check browser console (F12) for errors
2. Verify Firebase config is correct
3. Ensure Firestore permissions are set
4. Check network tab for failed requests

## 📝 Changelog

**v62.1** (June 17, 2026)
- Admin dashboard viewer (see any user's trades)
- Email/Password authentication
- Mobile login improvements
- Logo integration
- Quick Trade Escape shortcut

---

Built with ❤️ for traders by traders. Hosted on GitHub Pages. Powered by Firebase.
