# 🚀 Allma RAG - Quick Start Guide

## ✨ What's New

Your Allma RAG application has been **completely redesigned** with:

- ✅ **Modern, Beautiful UI** - Professional design with glassmorphism and gradients
- ✅ **Smooth Animations** - Purposeful motion design throughout
- ✅ **Dark Mode** - Fully implemented with local storage persistence
- ✅ **Responsive Design** - Perfect on mobile, tablet, and desktop
- ✅ **Advanced Typography** - Inter font with optimal readability
- ✅ **Accessible** - WCAG compliant with keyboard navigation
- ✅ **Settings Panel** - Customize models, RAG, and appearance
- ✅ **File Upload** - Drag and drop document support
- ✅ **Code Highlighting** - Beautiful syntax highlighting for code blocks
- ✅ **Conversation Management** - Multiple chat sessions with persistence

## 📋 Prerequisites

1. **Node.js** (v16 or higher)
2. **Backend Server** running at `http://localhost:8000`
3. **Ollama** with required models:
   - `deepseek-r1:latest` or `gemma2:9b` or `qwen2.5-coder:7b`
   - `nomic-embed-text:latest` (required for RAG)

## 🏃 Running the Application

### Step 1: Install Dependencies

```bash
cd allma-frontend
npm install
```

### Step 2: Start Development Server

```bash
npm run dev
```

The application will start at: **http://localhost:5173**

### Step 3: Start Backend (in separate terminal)

```bash
cd allma-backend
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

## 🎨 Features Overview

### 1. **Chat Interface**
- Send messages and get AI responses
- Markdown support with code highlighting
- Copy messages to clipboard
- Message timestamps
- Auto-scroll to new messages

### 2. **Sidebar**
- Create new conversations
- Browse conversation history
- Delete old conversations
- Access settings
- Toggle dark mode
- Collapsible on desktop

### 3. **Settings**
- Choose AI model
- Configure RAG settings
- Adjust appearance
- Set backend URL
- Customize experience

### 4. **File Upload**
- Click paperclip icon to attach files
- Supported formats: .txt, .pdf, .doc, .docx, .md
- Automatic RAG ingestion
- Visual file preview

### 5. **Responsive Design**
- **Mobile**: Hamburger menu, full-screen chat
- **Tablet**: Adaptive layout, touch-optimized
- **Desktop**: Full sidebar, hover effects

## ⚡ Keyboard Shortcuts

- `Enter` - Send message
- `Shift + Enter` - New line in message
- `Cmd/Ctrl + K` - New conversation (coming soon)
- `Cmd/Ctrl + ,` - Open settings (coming soon)

## 🎨 Customization

### Change Color Theme

Edit `tailwind.config.js`:

```js
colors: {
  primary: {
    500: '#8b5cf6', // Change this to your brand color
    // ...
  }
}
```

### Adjust Animations

Edit `index.css`:

```css
/* Speed up/slow down animations */
animation: fadeIn 0.3s ease-in-out; /* Change duration */
```

### Modify Layout

Edit component files in `src/components/`:
- `Sidebar.jsx` - Left sidebar
- `ChatMessage.jsx` - Message bubbles
- `InputArea.jsx` - Chat input
- `EmptyState.jsx` - Welcome screen

## 🔧 Configuration

### Backend URL

Default: `http://localhost:8000`

To change, open Settings → API Configuration → Backend URL

Or edit localStorage:
```js
localStorage.setItem('settings', JSON.stringify({
  ...settings,
  apiUrl: 'https://your-backend.com'
}));
```

### AI Model

Default: `deepseek-r1:latest`

To change, open Settings → Model Settings → Language Model

Available models:
- DeepSeek R1 (5.2GB)
- Gemma 2 9B (5.4GB)
- Qwen 2.5 Coder (4.7GB)

### RAG Settings

- **Enable RAG**: Toggle retrieval-augmented generation
- **Top K**: Number of documents to retrieve (1-10)

## 📱 Mobile Experience

On mobile devices (< 640px):
1. Tap hamburger menu (top-left) to open sidebar
2. Select or create conversations
3. Tap outside sidebar to close
4. Full-screen chat interface
5. Touch-optimized buttons (44x44px minimum)

## 🌙 Dark Mode

Dark mode is **enabled by default** and persists across sessions.

To toggle:
- Click moon/sun icon in sidebar
- Or use Settings → Appearance

## 📊 Performance Tips

1. **Clear old conversations**: Delete unused chats to improve load time
2. **Optimize images**: Use WebP format for file uploads
3. **Reduce animations**: Use browser's "Reduce motion" setting
4. **Close unused tabs**: Free up memory
5. **Update browser**: Use latest Chrome, Firefox, or Safari

## 🐛 Troubleshooting

### Backend Not Connected
- Check if backend is running at `http://localhost:8000`
- Visit `http://localhost:8000/docs` to verify
- Check Settings → API Configuration

### RAG Not Working
- Ensure `nomic-embed-text:latest` is installed in Ollama
- Run: `ollama pull nomic-embed-text`
- Check Settings → RAG Configuration → Enable RAG

### Animations Laggy
- Close other browser tabs
- Disable animations in system preferences
- Update graphics drivers
- Try a different browser

### Sidebar Not Opening (Mobile)
- Clear browser cache
- Reload page
- Check console for errors (F12)

### Messages Not Sending
- Check internet connection
- Verify backend is running
- Check browser console for errors
- Try refreshing the page

## 📚 File Structure

```
allma-frontend/
├── src/
│   ├── components/
│   │   ├── ChatMessage.jsx       # Message bubble component
│   │   ├── EmptyState.jsx        # Welcome screen
│   │   ├── InputArea.jsx         # Chat input with file upload
│   │   ├── LoadingIndicator.jsx  # Loading animation
│   │   ├── SettingsModal.jsx     # Settings panel
│   │   └── Sidebar.jsx           # Navigation sidebar
│   ├── hooks/
│   │   └── useApp.js             # Custom React hooks
│   ├── App.jsx                   # Main application
│   ├── App.css                   # Component styles
│   ├── index.css                 # Global styles
│   └── main.jsx                  # Entry point
├── public/                       # Static assets
├── tailwind.config.js            # Tailwind configuration
├── vite.config.js                # Vite configuration
├── package.json                  # Dependencies
├── DESIGN_SYSTEM.md              # Design documentation
└── README.md                     # This file
```

## 🎯 Next Steps

1. **Customize Colors**: Edit `tailwind.config.js` to match your brand
2. **Add Features**: Extend components with new functionality
3. **Improve RAG**: Upload more documents for better responses
4. **Deploy**: Build for production with `npm run build`
5. **Share**: Show off your beautiful AI chat interface!

## 🔨 Build for Production

```bash
npm run build
```

Output will be in `dist/` folder, ready to deploy to:
- Vercel
- Netlify
- GitHub Pages
- Your own server

## 📖 Documentation

- [Design System](DESIGN_SYSTEM.md) - Complete design documentation
- [Backend API](../allma-backend/ORCHESTRATION_README.md) - API reference
- [Copilot Instructions](../.github/copilot-instructions.md) - Development guide

## 💡 Tips for Best Experience

1. Use on a large screen for full desktop experience
2. Enable dark mode for reduced eye strain
3. Upload relevant documents to improve RAG responses
4. Create separate conversations for different topics
5. Use keyboard shortcuts for faster interaction

## 🎉 Enjoy Your New Design!

Your Allma RAG application is now **production-ready** with a beautiful, modern interface that rivals the best AI chat applications in the world. The design follows industry-leading principles and provides an exceptional user experience across all devices.

**Happy Chatting! 🚀**

---

*Need help? Check the [Design System documentation](DESIGN_SYSTEM.md) or create an issue on GitHub.*
