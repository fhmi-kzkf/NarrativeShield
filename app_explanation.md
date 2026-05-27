# NarrativeAegis™ — Technical Documentation & Application Guide

## 1. Executive Summary & Vision
NarrativeAegis™ is an enterprise-grade **AI Search Visibility (AISO) & Narrative Intelligence** platform. 

In the current digital landscape, user search behavior is undergoing a massive shift. Search engines are evolving from providing lists of hyperlinks to directly answering queries via generative summaries (like Google AI Overviews and Perplexity). This introduces a critical blind spot for brands: **companies have zero visibility and control over what AI models tell users about their reputation.** 

NarrativeAegis solves this by automating geo-targeted search auditing, analyzing sentiment, detecting untrustworthy/outdated sources cited by AI ("poison sources"), and generating step-by-step corrective playbooks.

---

## 2. System Architecture & Tech Stack

```
                                  +------------------------------------+
                                  |         Next.js Frontend           |
                                  |     (React Context & LocalState)   |
                                  +-----------------+------------------+
                                                    |
                                          (POST /api/audit payload)
                                                    v
                                  +------------------------------------+
                                  |        Next.js API Route           |
                                  |          (/api/audit)              |
                                  +--------+------------------+--------+
                                           |                  |
                       (Fetch Google SERPs)|                  |(Analyze Texts & Playbook)
                                           v                  v
                   +-------------------------------+  +-------------------------------+
                   |      Bright Data SERP API     |  |       Google Gemini API       |
                   |   (Geotargeting via gl/hl)    |  |       (gemini-2.5-flash)      |
                   +-------------------------------+  +-------------------------------+
```

* **Frontend Framework**: Next.js 15 (React 19) App Router
* **Visual Engine**: HSL Theme System + Glassmorphism (Vanilla CSS) + GSAP Animations
* **State & Persistence**: React Context API (`AuditProvider`) synced with `localStorage`
* **Scraping Infrastructure**: **Bright Data SERP API** + Bright Data Administrative Zone API
* **Large Language Model (LLM)**: **Google Gemini API** (Model: `gemini-2.5-flash`)

---

## 3. Detailed Component Breakdown

### A. Web Scraping & AI Overview Parsing (`src/lib/brightdata.ts`)
The integration with Bright Data is split into two phases:
1. **Dynamic Zone Retrieval**: The system queries the Bright Data Administrative API (`/zone/get_active_zones`) to automatically retrieve the active SERP zone name matching the user's account. This prevents hardcoding errors.
2. **Synchronous Google SERP Querying**: Dispatches POST requests to `https://api.brightdata.com/request` with `brd_json=1` and country (`gl`) / language (`hl`) parameters.
3. **Complex AI Overview Parsing**: The parser handles various Google SGE formats returned in JSON:
   - Maps standard text snippets.
   - Parses lists recursively, extracting textual summaries without rendering raw JS objects.
   - Extracts all cited references (source titles and URLs) for the poison source tracker.

### B. Cognitive Engine (`src/lib/gemini.ts`)
* **Bulk Parallel Analysis**: Dispatches parallel prompts to `gemini-2.5-flash` using `Promise.all` to analyze the collected AI Overview text. The model rates the sentiment from `-1.0` (critical danger) to `+1.0` (highly positive), extracts core factual claims, and identifies competitor mentions.
* **Format Resilience**: Gemini's JSON string outputs are cleaned of Markdown wrappers (e.g. ` ```json ` fences) using a custom regex utility to prevent parse crashes.
* **Playbook Generation**: Takes all aggregated sentiments, competitor data, and poison sources, compiling them into a professional step-by-step markdown correction guide.

### C. AVS (AI Visibility Score) Pillars (`src/lib/avs.ts`)
AVS evaluates the brand's reputation in AI-powered search engines out of 100 points:
* **Presence Rate (35%)**: Probability that a user's search queries trigger an AI Overview.
* **Sentiment Score (30%)**: Scaled rating based on the average emotional tone computed by Gemini.
* **Share of Voice (25%)**: Ratio of mentions of your brand compared to competitors in AI content.
* **Geographic Parity (10%)**: Measures how consistent the sentiment score is across global markets. High deviations drop this score, flagging regional brand vulnerabilities.

### D. Zero-Database Local History (`src/context/AuditContext.tsx`)
Rather than forcing a complex database setup, NarrativeAegis uses a client-side database wrapper:
* On initialization, it reads historical audits from `localStorage` (`narrative_aegis_history`).
* A React context wraps the root layout (`RootLayout`), exposing states like `auditData`, `pastAudits`, `isLoading`, and `runAudit`.
* Running a new audit hits `/api/audit`, returns the result payload, appends/replaces it in local history, sets the active audit state, and triggers a global UI re-render.

---

## 4. Why NarrativeAegis is Sticky (The SaaS Value Proposition)

A common question for brand intelligence tools is: *Why would a customer keep paying for this after using it once?* 
The answer lies in the **dynamic, volatile nature of Generative Search (AISO)**:
1. **Continuous Algorithm & Data Shifts**: Google's AI models are constantly re-trained and updated. A brand with a perfect 90 AVS today can drop to 30 tomorrow if Google shifts its training sources.
2. **Early Poison Warning System**: New Reddit threads, forum complaints, and competitor PR are published daily. If the AI model starts citing a new negative source, NarrativeAegis's alerts notify PR managers immediately.
3. **Competitor AISO Battle**: Direct competitors will continuously optimize their own search visibility. NarrativeAegis helps brands keep their *Share of Voice* high.
4. **Playbook Campaign Tracking**: Brand campaigns take weeks to alter AI training models. Brands use NarrativeAegis continuously to verify if their PR actions successfully shifted the AI overview.

---

## 5. Local Setup & Verification

### Setup `.env.local`
Save the credentials inside `narrative-shield-app/.env.local`:
```env
GOOGLE_GEMINI_API_KEY=your_gemini_key_here
BRIGHT_DATA_API_KEY=your_brightdata_key_here
```

### Installation & Run
```bash
# Navigate to Next.js app directory
cd narrative-shield-app

# Install packages
npm install

# Run dev server
npm run dev

# Check production compile
npm run build
```
