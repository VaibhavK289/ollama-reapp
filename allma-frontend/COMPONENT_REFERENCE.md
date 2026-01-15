# 🎨 Component Reference Guide

Quick reference for all UI components, utilities, and design patterns in Allma RAG.

---

## 🧩 Components

### ChatMessage
**Purpose**: Display user and AI messages with markdown support

**Props**:
- `message` - Message object with role, content, timestamp
- `index` - Index for stagger animation

**Features**:
- Markdown rendering
- Syntax highlighting
- Copy to clipboard
- Timestamps
- Stagger animations
- RAG context indicator

**Usage**:
```jsx
<ChatMessage 
  message={{
    role: 'user',
    content: 'Hello!',
    timestamp: Date.now()
  }}
  index={0}
/>
```

---

### InputArea
**Purpose**: Chat input with file upload and send functionality

**Props**:
- `onSendMessage` - Callback when message sent
- `isLoading` - Loading state
- `onFileUpload` - Callback for file uploads

**Features**:
- Auto-resizing textarea
- File attachment
- Voice input button
- Keyboard shortcuts
- Loading state
- Status indicator

**Usage**:
```jsx
<InputArea
  onSendMessage={(text, file) => handleSend(text, file)}
  isLoading={false}
  onFileUpload={(file) => handleUpload(file)}
/>
```

---

### Sidebar
**Purpose**: Navigation with conversations and settings

**Props**:
- `conversations` - Array of conversation objects
- `activeConversationId` - Current conversation ID
- `onSelectConversation` - Selection callback
- `onNewConversation` - New chat callback
- `onDeleteConversation` - Delete callback
- `darkMode` - Dark mode state
- `toggleDarkMode` - Toggle callback
- `onOpenSettings` - Settings callback

**Features**:
- Collapsible (80px ↔ 320px)
- Conversation list
- Delete confirmation
- Dark mode toggle
- Settings access

**Usage**:
```jsx
<Sidebar
  conversations={conversations}
  activeConversationId="1"
  onSelectConversation={(id) => setActive(id)}
  onNewConversation={() => createNew()}
  onDeleteConversation={(id) => deleteConv(id)}
  darkMode={true}
  toggleDarkMode={() => toggle()}
  onOpenSettings={() => setSettingsOpen(true)}
/>
```

---

### EmptyState
**Purpose**: Welcome screen when no messages

**Props**:
- `onNewChat` - New chat callback

**Features**:
- Feature showcase
- CTA button
- Quick tips
- Animated cards

**Usage**:
```jsx
<EmptyState onNewChat={() => createConversation()} />
```

---

### LoadingIndicator
**Purpose**: Show AI thinking state

**Props**:
- `message` - Loading message (default: "AI is thinking...")

**Features**:
- Animated dots
- Skeleton screens
- Shimmer effect
- Pulsing avatar

**Usage**:
```jsx
<LoadingIndicator message="Generating response..." />
```

---

### SettingsModal
**Purpose**: Configuration panel

**Props**:
- `isOpen` - Modal visibility
- `onClose` - Close callback
- `settings` - Settings object
- `onSave` - Save callback

**Features**:
- Model selection
- RAG configuration
- Appearance settings
- API configuration
- Glassmorphic overlay

**Usage**:
```jsx
<SettingsModal
  isOpen={isSettingsOpen}
  onClose={() => setSettingsOpen(false)}
  settings={settings}
  onSave={(newSettings) => saveSettings(newSettings)}
/>
```

---

### Toast
**Purpose**: Notification messages

**Props**:
- `message` - Notification text
- `type` - 'success' | 'error' | 'warning' | 'info'
- `onClose` - Close callback
- `duration` - Auto-dismiss time (ms)

**Features**:
- 4 variants
- Auto-dismiss
- Close button
- Icon indicators

**Usage**:
```jsx
<Toast
  message="File uploaded successfully"
  type="success"
  onClose={() => removeToast(id)}
  duration={5000}
/>
```

---

## 🎨 Design Utilities

### Colors

**Primary Scale**:
```css
bg-primary-50   /* Lightest */
bg-primary-100
bg-primary-200
bg-primary-300
bg-primary-400
bg-primary-500  /* Base */
bg-primary-600
bg-primary-700
bg-primary-800
bg-primary-900
bg-primary-950  /* Darkest */
```

**Accent Colors**:
```css
bg-accent-cyan
bg-accent-teal
bg-accent-emerald
bg-accent-pink
bg-accent-rose
```

**Neutral Scale**:
```css
bg-neutral-50   /* White in light, dark in dark */
...
bg-neutral-950  /* Dark in light, white in dark */
```

---

### Typography

**Font Sizes**:
```css
text-xs     /* 0.75rem / 12px */
text-sm     /* 0.875rem / 14px */
text-base   /* 1rem / 16px */
text-lg     /* 1.125rem / 18px */
text-xl     /* 1.25rem / 20px */
text-2xl    /* 1.5rem / 24px */
text-3xl    /* 1.875rem / 30px */
text-4xl    /* 2.25rem / 36px */
text-5xl    /* 3rem / 48px */
```

**Font Weights**:
```css
font-light      /* 300 */
font-normal     /* 400 */
font-medium     /* 500 */
font-semibold   /* 600 */
font-bold       /* 700 */
font-extrabold  /* 800 */
font-black      /* 900 */
```

**Font Families**:
```css
font-sans       /* Inter */
font-display    /* Cal Sans */
font-mono       /* JetBrains Mono */
```

---

### Buttons

**Primary Button**:
```jsx
<button className="btn-primary">
  Click Me
</button>
```
- Gradient background
- Shadow with glow
- Scale on hover
- Active state

**Secondary Button**:
```jsx
<button className="btn-secondary">
  Cancel
</button>
```
- Neutral background
- Subtle hover
- Scale on hover

**Ghost Button**:
```jsx
<button className="btn-ghost">
  More
</button>
```
- Transparent
- Hover background
- Minimal style

---

### Cards

**Standard Card**:
```jsx
<div className="card">
  Content
</div>
```
- White/dark background
- Rounded corners (3xl)
- Soft shadow

**Interactive Card**:
```jsx
<div className="card-interactive">
  Clickable Content
</div>
```
- Hover scale effect
- Shadow transition
- Cursor pointer

**Glass Card**:
```jsx
<div className="glass">
  Glassmorphism
</div>
```
- Semi-transparent
- Backdrop blur
- Border glow

**Strong Glass**:
```jsx
<div className="glass-strong">
  More opaque
</div>
```
- More opaque
- Stronger blur

---

### Inputs

**Modern Input**:
```jsx
<input 
  type="text" 
  className="input-modern"
  placeholder="Enter text"
/>
```
- Neutral background
- Focus border
- Ring on focus
- Rounded corners

**Textarea**:
```jsx
<textarea 
  className="input-modern"
  rows={3}
/>
```

**Select**:
```jsx
<select className="input-modern">
  <option>Option 1</option>
</select>
```

---

### Animations

**Fade In**:
```jsx
<div className="animate-fade-in">
  Fades in
</div>
```

**Fade Up**:
```jsx
<div className="animate-fade-up">
  Fades in and moves up
</div>
```

**Slide In**:
```jsx
<div className="animate-slide-in-right">
  Slides in from right
</div>
```

**Scale In**:
```jsx
<div className="animate-scale-in">
  Scales in
</div>
```

**Float**:
```jsx
<div className="animate-float">
  Continuous floating
</div>
```

**Shimmer**:
```jsx
<div className="shimmer">
  Loading shimmer
</div>
```

**Gradient**:
```jsx
<div className="gradient-bg">
  Animated gradient
</div>
```

**Pulse**:
```jsx
<div className="animate-pulse-slow">
  Slow pulse
</div>
```

**Glow**:
```jsx
<div className="animate-glow">
  Pulsing glow
</div>
```

---

### Shadows

```css
shadow-soft     /* Subtle elevation */
shadow-medium   /* Moderate depth */
shadow-large    /* Prominent elevation */
shadow-glow     /* Colored glow */
shadow-glow-lg  /* Larger glow */
```

---

### Special Effects

**Gradient Text**:
```jsx
<h1 className="gradient-text">
  Beautiful Gradient
</h1>
```

**Hide Scrollbar**:
```jsx
<div className="hide-scrollbar overflow-y-auto">
  Scrollable content
</div>
```

---

## 🎯 Layout Patterns

### Responsive Grid
```jsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

### Flex Center
```jsx
<div className="flex items-center justify-center h-screen">
  <div>Centered Content</div>
</div>
```

### Stack
```jsx
<div className="space-y-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

### Inline Stack
```jsx
<div className="flex items-center gap-3">
  <Icon />
  <span>Text</span>
</div>
```

---

## 📱 Responsive Utilities

**Breakpoints**:
- `sm:` - 640px and up
- `md:` - 768px and up
- `lg:` - 1024px and up
- `xl:` - 1280px and up
- `2xl:` - 1536px and up

**Example**:
```jsx
<div className="text-sm md:text-base lg:text-lg">
  Responsive text
</div>
```

**Hide on Mobile**:
```jsx
<div className="hidden lg:block">
  Desktop only
</div>
```

**Show on Mobile**:
```jsx
<div className="lg:hidden">
  Mobile only
</div>
```

---

## 🌙 Dark Mode

**Usage**:
```jsx
<div className="bg-white dark:bg-neutral-900 text-neutral-900 dark:text-neutral-100">
  Switches in dark mode
</div>
```

**Common Patterns**:
```css
/* Background */
bg-white dark:bg-neutral-900

/* Text */
text-neutral-900 dark:text-neutral-100
text-neutral-600 dark:text-neutral-400

/* Borders */
border-neutral-200 dark:border-neutral-700

/* Hover */
hover:bg-neutral-100 dark:hover:bg-neutral-800
```

---

## ⌨️ Keyboard Shortcuts

**Implemented**:
- `Enter` - Send message
- `Shift + Enter` - New line
- `Tab` - Navigate UI
- `Esc` - Close modals

**Coming Soon**:
- `Cmd/Ctrl + K` - New conversation
- `Cmd/Ctrl + ,` - Settings
- `Cmd/Ctrl + /` - Search

---

## 🎨 Icon Usage

**Lucide React Icons**:
```jsx
import { MessageSquare, Send, Settings } from 'lucide-react';

<MessageSquare className="w-5 h-5 text-primary-600" />
```

**Common Sizes**:
- `w-4 h-4` - Small (16px)
- `w-5 h-5` - Medium (20px)
- `w-6 h-6` - Large (24px)
- `w-8 h-8` - XL (32px)

---

## 🔧 Custom Hooks

### useMediaQuery
```jsx
const isMobile = useMediaQuery('(max-width: 640px)');
```

### useResponsive
```jsx
const { isMobile, isTablet, isDesktop } = useResponsive();
```

### useDarkMode
```jsx
const { darkMode, toggleDarkMode } = useDarkMode();
```

### useConversations
```jsx
const {
  conversations,
  activeConversation,
  addMessage,
  createConversation,
  deleteConversation
} = useConversations();
```

---

## 📝 Quick Tips

1. **Use design tokens** - Always use Tailwind classes, not arbitrary values
2. **Consistent spacing** - Stick to 8px grid (space-2, space-4, etc.)
3. **Responsive first** - Test mobile, tablet, desktop
4. **Accessibility** - Include ARIA labels, keyboard nav
5. **Performance** - Use CSS animations, avoid layout shifts
6. **Dark mode** - Always include dark: variants
7. **Animations** - Keep purposeful, not distracting
8. **Loading states** - Always show feedback
9. **Error handling** - Graceful degradation
10. **Documentation** - Comment complex logic

---

**Need help? Check the [Design System](DESIGN_SYSTEM.md) or [Quick Start](QUICKSTART.md) guide!** 🚀
