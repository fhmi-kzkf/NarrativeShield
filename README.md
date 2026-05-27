# NarrativeAegis™ — AI Search Visibility & Narrative Intelligence

NarrativeAegis is a powerful brand intelligence platform designed to monitor, audit, and protect your brand's reputation across modern AI Search Engines (like Google AI Overviews, Perplexity, and others). It helps brand managers, marketers, and PR professionals understand what AI tells users about their brand, identify source bias or "poison sources," and execute data-backed playbook strategies to influence the AI narrative.

Built for the **Web Data UNLOCKED Hackathon 2026**.

---

## 🌟 Key Features

1. **AI Narrative Audit Engine**
   - Automatically generates targeted search queries (Informational, Comparative, Transactional, Evaluative) for your brand and competitors.
   - Executes live searches across multiple geographies (US, Germany, Japan, Indonesia, etc.) and languages using the **Bright Data SERP API**.
   - Extracts real-time AI Overview (AIO) text content, citations, and organic search listings.

2. **AI Visibility Score (AVS)**
   - A proprietary comprehensive index (0-100) assessing your brand's AI search presence.
   - Broken down into:
     - **Presence Rate (35%)**: How often your brand is featured in AI Overviews.
     - **Sentiment (30%)**: The emotional tone of AI statements about your brand.
     - **Share of Voice (25%)**: Ratio of your brand's presence compared to direct competitors.
     - **Geographic Parity (10%)**: Consistency of AVS across scanned regional markets.

3. **Poison Source Detector**
   - Traces and lists external source URLs cited by AI Overviews that negatively affect your brand.
   - Classifies sources by bias type (e.g., outdated content, competitor-authored reviews, forum noise, factual errors).
   - Ranks sources using an Impact vs. Fixability framework, guiding you on where to focus corrective actions first.

4. **Corrective Action Playbook**
   - Leverages **Gemini 2.5 Flash** to analyze collected SERP data and generate step-by-step strategies.
   - Recommends explicit PR, SEO, and content campaigns (e.g., publishing target papers, requesting domain revisions, starting review campaigns) with expected timelines.

5. **Premium Interactive Dashboard**
   - Visualized using modern glassmorphic UI, rich color-coded charts (AVS gauge, sentiment matrix, competitor benchmark), and micro-animations.
   - Powered by dynamic local storage history so you can track multiple brands and audit history.

---

## 🛠️ Tech Stack

- **Framework**: Next.js 15 (React 19) App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS & Custom CSS variables
- **Animations**: GSAP (GreenSock Animation Platform) + Custom Scroll & Entrance animations
- **Scraping Infrastructure**: Bright Data SERP API & Zone Administration API
- **AI Engine**: Google Gemini API (Model: `gemini-2.5-flash`)

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v18.x or later)
- NPM or Yarn
- Bright Data Account (with a configured SERP API Zone)
- Google Gemini API Key

### 1. Clone & Navigate

```bash
cd NarrativeAegis/narrative-shield-app
```

### 2. Environment Setup

Create a `.env.local` file inside the `narrative-shield-app` directory:

```env
# Google Gemini API Key
GOOGLE_GEMINI_API_KEY="YOUR API KEY HERE"

# Bright Data API Key
BRIGHT_DATA_API_KEY="YOUR API KEY HERE"
```

*Note: The application will automatically detect your active SERP zone from your Bright Data account using the Administrative API. If none is found, it defaults to the zone name `narrative_aegis_serp`.*

### 3. Install Dependencies

```bash
npm install
```

### 4. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📁 Project Structure

```text
narrative-shield-app/
├── public/                 # Static assets
├── src/
│   ├── app/                # Next.js App Router (pages and API routes)
│   │   ├── api/audit/      # Audit scraping & analysis endpoint
│   │   ├── audit/new/      # Start a new audit form
│   │   ├── audit/nexafin/  # Audit results detail dashboard
│   │   ├── dashboard/      # Global dashboard page
│   │   └── playbook/       # Global playbook page
│   ├── components/         # Reusable React components (AVSGauge, NarrativeMap, etc.)
│   ├── context/            # React Context for Audit history & execution state
│   ├── hooks/              # Custom React hooks (animations, countup, etc.)
│   └── lib/                # Core logic & integrations (Bright Data, Gemini, AVS)
└── .env.local              # Local environment credentials (ignored by Git)
```

---

## 📝 License

This project was built for hackathon evaluation and demonstration purposes. Distributed under the MIT License.
