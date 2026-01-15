# 🚀 Allma Studio - RAG Application

![RAG Ingestion Pipeline](diagrams/RAG_Implementation_Architecture_Diagram.jpg)

## ✨ Project Overview

**Allma Studio** is a production-ready, full-stack **Retrieval-Augmented Generation (RAG)** application featuring:

- 🎨 **Beautiful Modern UI** - Completely redesigned with industry-leading design principles
- 🤖 **Local AI Models** - Powered by Ollama (DeepSeek, Gemma, Qwen)
- 📚 **RAG Pipeline** - ChromaDB vector store with document ingestion
- ⚡ **FastAPI Backend** - Orchestrated service architecture
- 💎 **React Frontend** - Tailwind CSS with glassmorphism and animations
- 🌙 **Dark Mode** - Full support with localStorage persistence
- 📱 **Responsive** - Mobile, tablet, and desktop optimized
- ♿ **Accessible** - WCAG compliant with keyboard navigation

## 🏗️ Architecture

### Backend (`allma-backend/`)
FastAPI orchestration layer connecting:
- **RAG Service** - Embeddings, retrieval, reranking
- **Vector Store Service** - ChromaDB persistence
- **Document Service** - File parsing, chunking
- **Conversation Service** - Chat history management

### Frontend (`allma-frontend/`)
React + Vite SPA with:
- **Modern Design System** - Custom Tailwind theme
- **Component Library** - Reusable UI components
- **State Management** - React hooks + localStorage
- **API Integration** - Fetch API for backend communication

## 🎨 Design Highlights

The frontend has been **completely redesigned** by a lead web designer with focus on:

- ✅ **Color Theory** - Sophisticated purple-to-blue gradient palette
- ✅ **Typography** - Inter font family with optical sizing
- ✅ **Motion Design** - 15+ custom animations (fade, slide, scale, float, glow)
- ✅ **Glassmorphism** - Modern backdrop blur effects
- ✅ **Responsive** - Mobile-first with 3 breakpoint system
- ✅ **Accessibility** - WCAG AA compliant (4.5:1 contrast)
- ✅ **Performance** - GPU-accelerated CSS animations

See [Frontend Design System](allma-frontend/DESIGN_SYSTEM.md) for complete documentation.

## 🚀 Quick Start

### Prerequisites
- Node.js v16+
- Python 3.9+
- Ollama with models:
  - `deepseek-r1:latest` or `gemma2:9b` (LLM)
  - `nomic-embed-text:latest` (embeddings - **required**)

### Start Backend
```bash
cd allma-backend
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

API docs: http://localhost:8000/docs

### Start Frontend
```bash
cd allma-frontend
npm install
npm run dev
```

App: http://localhost:5173

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [Frontend Design System](allma-frontend/DESIGN_SYSTEM.md) | Complete design documentation |
| [Quick Start Guide](allma-frontend/QUICKSTART.md) | Getting started guide |
| [Backend API](allma-backend/ORCHESTRATION_README.md) | API reference |
| [Copilot Instructions](.github/copilot-instructions.md) | Development guide |

## 🎯 Features

### Chat Interface
- ✅ Real-time messaging with AI
- ✅ Markdown support with syntax highlighting
- ✅ Copy messages to clipboard
- ✅ Message timestamps
- ✅ Auto-scroll to new messages
- ✅ Multiple conversation support

### RAG Capabilities
- ✅ Document upload (.txt, .pdf, .doc, .md)
- ✅ Vector embeddings with nomic-embed-text
- ✅ Semantic search with ChromaDB
- ✅ Context-aware responses
- ✅ Source attribution

### UI/UX
- ✅ Collapsible sidebar (80px ↔ 320px)
- ✅ Dark mode with toggle
- ✅ Settings panel (model, RAG, appearance)
- ✅ File attachment with preview
- ✅ Loading indicators
- ✅ Toast notifications
- ✅ Empty states
- ✅ Error handling

### Responsive Design
- ✅ Mobile: Hamburger menu, full-screen chat
- ✅ Tablet: Adaptive layout, touch-optimized
- ✅ Desktop: Full sidebar, hover effects

## 🎨 Design System Features

### Animations
- `fade-in`, `fade-up` - Entrance effects
- `slide-in-left`, `slide-in-right` - Directional slides
- `scale-in` - Scaling entrance
- `float` - Continuous floating
- `shimmer` - Loading skeleton
- `gradient` - Animated backgrounds
- `glow` - Pulsing glow effect

### Components
- **Sidebar** - Collapsible navigation
- **ChatMessage** - User/AI message bubbles
- **InputArea** - Chat input with file upload
- **EmptyState** - Welcome screen
- **LoadingIndicator** - Typing animation
- **SettingsModal** - Configuration panel
- **Toast** - Notifications

### Utilities
- `.glass` - Glassmorphism effect
- `.gradient-text` - Gradient text
- `.btn-primary`, `.btn-secondary`, `.btn-ghost` - Button variants
- `.card`, `.card-interactive` - Card styles
- `.input-modern` - Form inputs

## 📊 Architecture Diagrams

![Database Schema](./diagrams/Entity_Relationship_Diagram.png)
![Architectural Diagram](./diagrams/architecture-diagram.jpg)