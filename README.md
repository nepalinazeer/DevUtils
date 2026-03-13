# DevUtils — Developer Toolkit

A collection of free, privacy-first browser tools for developers — JSON formatter, JWT decoder, regex tester, diff viewer, MCP &amp; Agent security labs, LLM tokenizer, and more. No data leaves your browser.

**Live site:** [toolings.net](https://toolings.net)

---

## Tools

### General

| Tool | Path | Description |
|------|------|-------------|
| JSON Formatter | `/json` | Format, validate, prettify, minify, and sort JSON with full syntax highlighting |
| Base64 | `/base64` | Encode/decode Base64 with correct Unicode handling via TextEncoder |
| Password Generator | `/password` | Cryptographically secure passwords via `crypto.getRandomValues()`, up to 128 chars |
| URL Encoder | `/url-codec` | Encode/decode URL components with `encodeURIComponent` / `decodeURIComponent` |
| JWT Decoder | `/jwt` | Decode JWT headers, payloads, and signatures in-browser with live expiry status |
| Regex Tester | `/regex` | Live regex matching with flag toggles, match indices, and captured group inspection |
| Timestamp Converter | `/timestamp` | Unix ↔ human-readable date conversion across 13 timezones with a live ticking clock |
| Diff Viewer | `/diff` | Line-by-line text diff using Myers algorithm, side-by-side and unified views |

### AI / LLM

| Tool | Path | Description |
|------|------|-------------|
| Tokenizer Visualizer | `/tokenizer` | Visualize GPT-style BPE tokenization with color-coded token IDs |
| Attention Heatmap | `/attention` | Simulate transformer self-attention and visualize word-to-word attention weights |
| Embedding Explorer | `/embeddings` | 2D PCA projection of character n-gram word embeddings with cosine similarity |
| Agent Security Lab | `/agent-security` | Interactive CTF-style lab for OWASP LLM Top 10 agentic AI vulnerabilities |

### MCP (Model Context Protocol)

| Tool | Path | Description |
|------|------|-------------|
| MCP Message Flow | `/mcp-flow` | Step through the full MCP JSON-RPC handshake with live message payloads |
| MCP Security Lab | `/mcp-security` | Interactive CTF-style lab for OWASP MCP Top 10 vulnerabilities |
| MCP Tool Schema Builder | `/mcp-schema` | Visual editor for MCP tool input schemas — no JSON hand-writing required |
| MCP Config Generator | `/mcp-config` | Generate MCP server config blocks for Claude Desktop or Claude Code |

---

## Security Labs

Both labs share the same structure:

- **Learn** — understand the vulnerability, how it works, and why it's dangerous
- **Attack** — exploit it in a safe simulated environment
- **Defend** — read the secure fix with Python syntax-highlighted code diffs

### MCP Security Lab (`/mcp-security`)
Covers OWASP MCP Top 10: token mismanagement, prompt injection, command injection, SSRF, privilege escalation, rug pull attacks, cross-session data leakage, and more.

### Agent Security Lab (`/agent-security`)
Covers OWASP LLM Top 10 for agentic AI: indirect prompt injection, excessive agency, memory poisoning, multi-agent trust exploitation, denial-of-wallet, insecure code execution, context exfiltration, cross-session leakage, tool chain injection, and missing human-in-the-loop controls.

Both labs include **Hacker Mode** — a retro terminal aesthetic with matrix rain intro animation, green-on-black display, and scanline overlay.

---

## Tech Stack

- **Framework:** React 18 + TypeScript
- **Build:** Vite
- **Styling:** Tailwind CSS
- **Routing:** React Router v6
- **Icons:** Lucide React
- **AI/ML:** `@huggingface/transformers`, `js-tiktoken`
- **SEO:** `react-helmet-async`, JSON-LD structured data, sitemap.xml

---

## Development

```bash
npm install
npm run dev       # dev server at localhost:5173
npm run build     # production build
npm run preview   # preview production build
```

All tools are lazy-loaded via `React.lazy()` for fast initial page load. Tool registration is centralized in [`src/registry.tsx`](src/registry.tsx) — adding a new tool requires only a single entry there.

---

## Privacy

Every tool runs entirely client-side. No analytics, no tracking, no data transmission. Sensitive inputs like JWTs and passwords never leave the browser.
