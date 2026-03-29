## chm1-ai-assistant-portfolio


## 🎯 Overview

This is a modern, performant portfolio site built with **vanilla HTML/CSS/JavaScript** and enhanced with **Claude API integration**. It features a terminal-style chat interface that lets visitors ask about projects, stack, and experience in real-time.

**Live:** Interactive terminal experience powered by Claude API  
**Tech Composition:** 94.7% HTML | 5.3% Python  
**Status:** ✅ Live & Available

---

## 🛠 Tech Stack

### Frontend
- **HTML5** — Semantic structure, responsive design
- **CSS3** — Custom variables, animations, glassmorphism effects
- **Vanilla JavaScript** — Terminal UI, interactivity, scroll effects

### Backend
- **Python** — Serverless API handler
- **httpx** — HTTP client for Claude API calls
- **Vercel Functions** — Deployment & hosting

### AI Integration
- **Claude API (Haiku)** — Real-time conversational responses
- **Context:** System prompt with portfolio details for accurate answers

---

## 📋 Project Structure

```
.
├── index.html          # Main portfolio page (embedded styles + scripts)
├── api/chat.py         # Serverless function for Claude API calls
├── vercel.json         # Deployment configuration
├── requirements.txt    # Python dependencies
└── README.md          # This file
```

### Key Files

**`index.html`** (39KB)
- Single-page portfolio with 6 main sections
- Terminal overlay for interactive chat
- Mac-style window aesthetics (buttons, popups, effects)
- Real-time clock, parallax scrolling, scroll reveal animations
- Easter egg (click © 2025 in footer)

**`api/chat.py`** (2KB)
- POST handler for `/api/chat` endpoint
- Proxies requests to Claude API v1/messages
- Handles CORS, error handling, environment variables
- Uses **Claude Haiku 4.5** for speed & cost efficiency

---

## 🎨 Features

### Interactive Terminal
- Click the terminal window or "ask me anything" prompt to open
- Real-time typing animation for responses
- Conversation history maintained during session
- Minimize, maximize, close buttons (Mac-style)
- Status indicator (READY / THINKING...)

### Portfolio Sections

1. **Hero** — Full-screen intro with system status bar
2. **About** — Who you are + Technical Stack with skill bars
3. **Work** — 4 featured projects with tags and deployment status
4. **Process** — How you work: Scope → Iterate → Ship
5. **Contact** — Email, GitHub, LinkedIn links
6. **Footer** — Easter egg hidden in copyright year

### Responsive Design
- Mobile-optimized (breakpoint: 768px)
- Hides ghost windows on mobile
- Stacked layout for touch devices

---

## 🚀 Getting Started

### Prerequisites
- Python 3.x
- Anthropic API key (for Claude access)

### Local Development

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Set environment variable:**
   ```bash
   export ANTHROPIC_API_KEY="your-key-here"
   ```

3. **Run locally** (for testing the API):
   ```bash
   # Vercel CLI
   vercel dev
   ```
   Then navigate to `http://localhost:3000`

### Deployment (Vercel)

This repo is preconfigured for Vercel:

```bash
# Deploy
vercel

# Set API key in environment variables
vercel env add ANTHROPIC_API_KEY
```

The `vercel.json` file configures:
- Python runtime for `api/chat.py`
- URL rewrite: `/api/chat` → `/api/chat.py`

---

## 📝 Configuration

### Update Portfolio Content

Edit `index.html` to customize:

1. **Hero Section** (line 394)
   - Headline: `Full-Stack Developer who ships.`
   - Meta info: Role, Stack, Focus, Status

2. **About Section** (lines 410-431)
   - Bio text
   - Tech stack proficiency bars

3. **Work/Projects** (lines 439-474)
   - Project titles, descriptions, tags
   - Status (Deployed, Active, Production)
   - Years

4. **Contact Links** (lines 492-495)
   - Email, GitHub, LinkedIn URLs

### Update AI Assistant

Edit the `SYSTEM_PROMPT` (line 550 in `index.html`) to:
- Change personality/tone
- Update project descriptions
- Add new technologies or skills

---

## 🔌 API Integration

### Request Format
```json
{
  "system": "System prompt (context about you)",
  "messages": [
    { "role": "user", "content": "User question" },
    { "role": "assistant", "content": "Previous response" }
  ]
}
```

### Response Format
```json
{
  "content": [
    { "type": "text", "text": "Claude's response" }
  ]
}
```

### Error Handling
- Missing API key → 500 error with message
- Invalid JSON → 400 error
- API timeout (30s) → 500 error with details

---

## 🎭 Customization

### Colors & Theme
CSS variables (line 9-20):
```css
--bg: #0a0a0a              /* Dark background */
--yellow: #F5A800          /* Accent color */
--green: #00ff88           /* Terminal prompt */
--white: #f0f0f0           /* Text */
```

### Animations
- Hero fade-up: 0.6s–0.7s staggered
- Scroll reveal: 0.6s, triggered at 10% threshold
- Terminal type effect: 18ms per character

### Fonts
- **Syne** (sans-serif) — Large headings
- **Space Mono** (monospace) — Code, terminal, body text

---

## 📊 Performance

- **Single HTML file** → No build process needed
- **No external dependencies** (except fonts from Google)
- **Terminal API calls** → Lazy-loaded via fetch
- **CSS optimized** → Embedded, minimal (inline in <style>)
- **JS lightweight** → ~15KB unminified (inline <script>)

**Load time:** ~100–300ms (depending on connection)

---

## 🐛 Troubleshooting

### Terminal returns "ERROR"
- Check `ANTHROPIC_API_KEY` is set in Vercel environment
- Verify Claude API account has credits
- Check browser console for request errors

### Styling breaks on mobile
- Ensure viewport meta tag is present (line 5)
- Test with DevTools mobile emulation (375px–768px)

### Chat responses are slow
- Verify Vercel function cold start (first request slower)
- Check API rate limits on Claude dashboard

---

## 📄 License

Personal portfolio — feel free to use as inspiration for your own!

---

## 🔗 Links

- **Live Site:** [your-domain.com]
- **Repository:** github.com/chenghongm/chm1-portfolio
- **API:** `/api/chat` (POST, requires auth)
- **Docs:** Anthropic Claude API v1 docs

---

**Built by Chenghong Meng** — Direct. Systems-oriented. Ships production code.
```

This README covers:
- ✅ Project overview & purpose
- ✅ Tech stack breakdown
- ✅ File structure with descriptions
- ✅ All major features
- ✅ Setup & deployment instructions
- ✅ How to customize content & AI behavior
- ✅ API integration details
- ✅ Troubleshooting guide

Feel free to adjust sections to match your actual live URL, contact links, and any additional details!
