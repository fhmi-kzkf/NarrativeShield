# 🎬 Video Pitch Script: NarrativeAegis™
**Target Duration:** ~3 - 5 Minutes  
**Theme:** Hackathon Pitch & Live Demo (Bright Data × Gemini AI)  
**Language:** English  

---

## 📌 Scene 1: Introduction / Hook (0:00 - 0:45)
* **Visual:** Presenter on camera, or a screen recording showing a Google search page with an incorrect or negative "AI Overview" block about a brand. Transition with a dramatic digital glitch effect.
* **Audio/Voice Over:**
  > "Have you ever wondered... what AI says about your brand or company when someone searches for it online? 
  > 
  > Today, over 40% of Google searches trigger an **AI Overview**. Users no longer click links; they read summaries generated directly by AI. The problem is: **you are blind to what AI is telling them.**
  > 
  > What if the AI is citing outdated data? What if it's summarizing biased forum posts? Or worse... what if it's recommending your direct competitors?
  > 
  > Welcome to **NarrativeAegis™** — your brand's digital defense shield in the age of Generative AI."

---

## 📌 Scene 2: Solution & Value Proposition (0:45 - 1:30)
* **Visual:** Transition to a smooth high-definition screencast of the NarrativeAegis Landing Page, showing the premium glassmorphic UI and interactive animated background grids. The presenter scrolls down gently.
* **Audio/Voice Over:**
  > "NarrativeAegis is an integrated *AI Search Visibility & Narrative Intelligence* platform. We monitor, analyze, and protect your brand's reputation in AI search results in real time.
  > 
  > Powered by **Bright Data's** advanced web scraping infrastructure and **Gemini AI's** cognitive intelligence, NarrativeAegis maps global search sentiments, languages, and contexts instantly."

---

## 📌 Scene 3: Global Dashboard & AVS Demo (1:30 - 2:30)
* **Visual:** Transition to the **Global Dashboard** page. The cursor highlights the **Global AVS** card and the **Tracked Brands** list.
* **Audio/Voice Over:**
  > "Let's dive into our main dashboard. Here, we introduce our proprietary metric: **AVS**, or the **AI Visibility Score**. 
  > 
  > AVS measures your AI reputation health on a scale of 0 to 100, calculated across 4 pillars: *Presence Rate* (how often your brand triggers AI), *Sentiment Score* (whether the AI tone is positive or negative), *Share of Voice* compared to competitors, and *Geographic Parity* (sentiment consistency across regions).
  > 
  > For example, let's open the live audit report for our tracked brand, **Gojek**."

---

## 📌 Scene 4: Highlight Feature — Narrative Map & Poison Sources (2:30 - 3:45)
* **Visual:** Clicking Gojek. Show the interactive **AVS Gauge** and transition to the **Narrative Map** tab (the colorful interactive sentiment grid). The cursor clicks an orange/red cell, opening the details panel showing the cited sources and the original AI text snippet.
* **Audio/Voice Over:**
  > "This is where the magic happens. The **AI Narrative Map** correlates *Search Intent* (Informational, Comparative, Evaluative, Transactional) with your audience's geography. 
  > 
  > Look at this red cell. Users in Germany searching for comparative products are seeing negative sentiment. When we click it, the system immediately pulls the exact AI Overview text and highlights its citations.
  > 
  > We call these **Poison Sources**. NarrativeAegis automatically detects outdated, competitor-biased, or inaccurate web pages that feed the AI, ranking them by impact and repair ease."

---

## 📌 Scene 5: Highlight Feature — Corrective Action Playbook (3:45 - 4:15)
* **Visual:** Switch to the **Playbook** tab. Show step-by-step action items displayed as an animated professional report.
* **Audio/Voice Over:**
  > "We don't just detect the problems; we solve them. The **Action Playbook** generates customized corrective strategies powered by Gemini. 
  > 
  > Whether it's publishing a target security paper, requesting an article revision on a biased blog, or launching a positive review campaign on G2. Every action includes a timeline showing how long it will take for the AI engine to update its narrative."

---

## 📌 Scene 6: Behind the Tech & Wrap-up (4:15 - 5:00)
* **Visual:** Back to the presenter, or showing the system architecture data flow diagram. Bright Data and Gemini logos are displayed side by side with a glow effect.
* **Audio/Voice Over:**
  > "Behind the scenes, NarrativeAegis queries the **Bright Data SERP API** in parallel to bypass geo-restrictions and retrieve raw Google search pages. This data is then analyzed by **Gemini 2.5 Flash** for instant bulk sentiment classification.
  > 
  > In an era where AI is the new search gateway, NarrativeAegis ensures your brand story is told honestly, accurately, and positively.
  > 
  > Shield your narrative. Use **NarrativeAegis** today. Thank you."

---

# 📖 Complete Explanation of NarrativeAegis™

### 1. The Core Problem
In the pre-AI era, traditional Search Engine Optimization (SEO) focused entirely on keyword rankings (ranking on page 1 of Google). However, with the rise of **Google AI Overviews (SGE)**, **Perplexity**, and **Bing Copilot**, search behaviors have shifted:
* Users receive synthesized summaries at the top of search results without needing to click any links.
* These summaries are automatically generated by AI scraping various web sources.
* **The Problem**: Brands are blind to what AI is saying. AI engines often pull outdated articles, competitor-authored reviews, or noisy forum threads (like Reddit or Quora), damaging brand reputation instantly PR/marketing departments knowing.

### 2. How the Platform Works
NarrativeAegis is built as a responsive SaaS dashboard that performs on-demand audits and periodic tracking:
1. **User Setup**: Users input their Brand name (e.g., *Gojek*), competitors (e.g., *Grab*), and select target geographic markets.
2. **Web Scraping via Bright Data SERP API**:
   The system generates targeted query variations mapping the user search intents. Queries are dispatched to Bright Data SERP API with country (`gl`) and language (`hl`) parameters. Bright Data returns raw structured Google search results, extracting the AI Overview content block.
3. **Cognitive Analysis with Gemini 2.5 Flash**:
   The parsed AI Overview text is sent to Gemini AI. Gemini evaluates the sentiment (ranging from -1.0 to +1.0), pulls factual claims, flags competitor mentions, and identifies potential reputation risks.
4. **AVS Index Calculation**:
   The four pillars of the AVS score are calculated and combined to give a single executive health rating from 0 to 100.
5. **Corrective Playbook & Poison Sources Mapping**:
   The system ranks cited websites that negatively impact the brand and recommends counter-campaigns (e.g., PR releases, article corrections) to shift the AI model's training citations.

### 3. Key Technical Highlights
* **High Performance**: Uses parallel processing (`Promise.all`) for both web scraping and Gemini evaluations, ensuring an audit completes in under 20 seconds.
* **Aesthetic Glassmorphic UI**: Uses custom HSL color systems, glass backdrop filters, and micro-animations (via GSAP) to deliver a modern, premium user experience.
* **Dynamic Local Storage**: Audits are synchronized locally using React Context API and LocalStorage, giving users persistent search history without backend database overhead.
