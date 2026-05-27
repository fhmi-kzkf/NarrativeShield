# 📋 PRODUCT REQUIREMENT DOCUMENT
## Narrative Aegis™ v4.0
### *AI Search Visibility & Narrative Intelligence for Enterprise Brands*

| Versi | Tanggal | Status |
|-------|---------|--------|
| 4.0 (Final — Vercel + Hybrid AI) | 26 Mei 2026 | Final |

---

## 1. The One-Line Pitch

> **"Brandwatch tells you what people say about you. Narrative Aegis tells you what AI tells people about you — and fixes it."**

---

## 2. Executive Summary

Sejak 2024, lebih dari 40% pencarian Google kini menampilkan **AI Overviews** yang menjawab pertanyaan pengguna *sebelum* mereka mengklik satu pun hasil pencarian. Bing Copilot, Perplexity, dan ChatGPT Search melakukan hal yang sama. Brand kehilangan kendali atas narasi mereka bukan lagi di media sosial — tapi di **lapisan AI yang menjadi filter tunggal antara merek dan pasar mereka**.

Narrative Aegis adalah sistem intelijen pertama yang:
1. **Mengaudit** apa yang dikatakan AI publik tentang brand Anda di berbagai pasar dan bahasa
2. **Mendeteksi** sumber data mana yang *meracuni* representasi AI Anda
3. **Menghasilkan** Corrective Action Playbook terstruktur — bukan sekadar laporan, tapi panduan tindakan spesifik

Dibangun di atas infrastruktur Bright Data karena mengakses AI Overviews secara konsisten, dalam skala global, lintas bahasa, adalah **mustahil tanpanya**.

---

## 3. Mengapa Ini Bukan "Brand Monitoring Biasa"

| Dimensi | Brandwatch / Mention / Meltwater | Narrative Aegis v4.0 |
|---------|----------------------------------|----------------------|
| Yang dipantau | Mention di sosmed, blog, forum | Apa yang *dikatakan AI* ke pengguna |
| Visibilitas untuk brand | Ada notifikasi mention | Zero visibility — tidak ada tool untuk ini |
| Tindakan yang bisa diambil | "Balas tweet negatif" | "Perbaiki halaman X agar AI berhenti mengutipnya" |
| Ketergantungan pada Bright Data | Bisa tanpa Bright Data | **Mustahil tanpa Bright Data** |

---

## 4. Problem Statement

### Masalah 1 — AI Menjadi Gatekeeper Persepsi Brand
Ketika calon pelanggan mengetik *"Is [Brand X] trustworthy?"*, Google AI Overviews kini menjawab langsung — tanpa pengguna harus membuka satu pun halaman. Brand tidak tahu jawaban apa yang diberikan AI ini.

### Masalah 2 — Sumber Racun Tidak Teridentifikasi
AI Overviews tidak transparan tentang sumber yang diprioritaskan. Brand tidak tahu apakah narasi negatif berasal dari review G2 lama, artikel kompetitor yang bias, Wikipedia yang belum diperbarui, atau forum Reddit dengan konteks yang salah.

### Masalah 3 — Variasi Geografis Tidak Terpantau
AI Overviews menampilkan konten berbeda per bahasa dan lokasi. Brand global mungkin punya representasi akurat di AS tapi buruk di Jerman atau Indonesia — tanpa pernah mengetahuinya.

---

## 5. Target Users & Personas

| Persona | Jabatan | Pain Point | Nilai dari Narrative Aegis |
|---------|---------|------------|----------------------------|
| **Rina** | Chief Brand Officer | "Saya tidak tahu apa yang dikatakan Google AI ketika CTO pelanggan saya mencari alternatif kami" | Dashboard: AI menyebut kami sebagai pilihan pertama atau terakhir? |
| **Dito** | Head of Digital Marketing | "Saya habiskan $2M/tahun untuk SEO tapi tidak tahu apakah upaya itu tercermin di AI Overviews" | Audit: apakah konten yang kami optimalkan dikutip AI? |
| **Maya** | VP Communications | "Saat ada krisis, saya tidak tahu apakah AI sudah memperbesar narasi salah" | Alert: AI Overviews berubah dalam 24 jam setelah insiden |

---

## 6. Core Features

### F1: AI Narrative Audit Engine
Sistem mengirimkan **50+ query variasi** per brand ke Bright Data SERP API, mencakup:
- Query intent berbeda: informational, comparative, evaluative, transactional
- Query dalam 5 bahasa dan 8 pasar geografi berbeda
- Query dari perspektif: calon pelanggan, investor, rekruter

Untuk setiap query, sistem mengekstrak:
- Apakah AI Overview muncul?
- Konten AI Overview: sentimen, klaim faktual, penyebutan kompetitor
- Sumber yang dikutip AI (URL basis jawabannya)
- Posisi brand vs kompetitor dalam narasi AI

**Output:** AI Narrative Map — matriks visual representasi brand lintas intent dan geografi.

**Mengapa perlu Bright Data:** Google AI Overviews tidak tersedia melalui API resmi manapun. Scraping langsung diblokir. Hanya Bright Data SERP API yang bisa mengakses ini secara konsisten dan dalam skala 50+ query multi-geografi.

### F2: Narrative Poison Source Detector
Setelah AI Narrative Map terbentuk, sistem menelusuri setiap URL yang dikutip AI Overviews sebagai sumber.

Untuk setiap sumber, sistem menganalisis:
- **Usia konten:** apakah artikel sudah outdated?
- **Bias sumber:** konten kompetitor, review bias, atau forum tanpa konteks?
- **Akurasi faktual:** apakah klaim masih akurat dibanding fakta terkini brand?
- **Kemampuan perbaikan:** bisa brand mempengaruhi sumber ini?

Untuk sumber JS-heavy (G2, Trustpilot, forum): menggunakan **Scraping Browser** untuk rendering penuh.

**Output:** Ranked list "Poison Sources" — sumber mana yang paling berdampak negatif dan paling mudah diperbaiki.

### F3: AI Visibility Score & Competitor Benchmarking
Sistem menghitung **AI Visibility Score (AVS)** — metrik baru yang mengukur seberapa baik brand direpresentasikan dalam AI-generated answers dibanding kompetitor.

Komponen AVS:
- *Presence rate:* % query di mana brand muncul di AI Overview
- *Sentiment score:* rata-rata sentimen konten AI tentang brand
- *Share of AI voice:* berapa kali brand disebut vs kompetitor
- *Geographic parity:* konsistensi representasi lintas pasar

```
AVS = (0.35 × Presence Rate) + (0.30 × Sentiment Score)
    + (0.25 × Share of AI Voice) + (0.10 × Geographic Parity)

Skala: 0–100
< 40 : Critical  — AI aktif merugikan brand
40–60: Neutral   — AI tidak membantu atau merugikan
60–80: Positive  — AI mendukung persepsi positif brand
> 80 : Leading   — Brand mendominasi narasi AI di kategori
```

### F4: Corrective Action Playbook
Berdasarkan temuan F1–F3, sistem menghasilkan playbook yang berisi:
- Untuk setiap poison source: rekomendasi spesifik (update halaman mana, publish konten apa)
- Prioritas berdasarkan: dampak pada AVS × kemudahan eksekusi
- Template konten: struktur artikel yang kemungkinan besar dikutip AI
- Timeline realistis: estimasi berapa minggu perubahan tercermin di AI Overview

### F5: Continuous Watch & Delta Alert
Sistem berjalan setiap 24 jam via Vercel Cron dan membandingkan AI Narrative Map hari ini vs kemarin. Alert dikirim ke Slack/email jika:
- AI Overview berubah sentimen secara signifikan
- Sumber baru (terutama negatif) mulai dikutip AI
- Kompetitor mulai disebutkan dalam query yang sebelumnya hanya menyebut brand kita

---

## 7. Technical Architecture

```
┌─────────────────────────────────────────────────────┐
│              BROWSER / USER                         │
│         Next.js App Router — Vercel CDN             │
│ └───────────────────┬─────────────────────────────────┘
                    │ fetch()
┌───────────────────▼─────────────────────────────────┐
│         VERCEL — Next.js API Routes                 │
│              (Serverless Functions)                 │
│                                                     │
│  /api/audit      /api/sources     /api/playbook     │
│       │                │               │            │
│       ▼                ▼               ▼            │
│  Bright Data      Bright Data     Gemini Flash      │
│  SERP API         Web Scraper     (bulk analysis)   │
│  (50+ queries)    API +                │            │
│                   Scraping Browser     ▼            │
│                                  Claude Sonnet      │
│                                  (final playbook)   │
│                                                     │
│  ─────────────────────────────────────────────────  │
│           Vercel KV (Redis)                         │
│    cache hasil audit · job queue · rate limit       │
└─────────────────────────────────────────────────────┘
                    │
┌───────────────────▼─────────────────────────────────┐
│           VERCEL CRON JOBS                          │
│     /api/audit dijalankan otomatis tiap 24 jam      │
└─────────────────────────────────────────────────────┘

Output: Slack webhook · PDF report · UI dashboard
```

---

## 8. Tech Stack

### Frontend & Backend
| Layer | Teknologi | Keterangan |
|-------|-----------|------------|
| Framework | Next.js 15+ (App Router) | Satu repo, SSR + API Routes |
| Styling | Tailwind CSS & Custom HSL | Utility-first, cepat dibangun |
| Deploy | Vercel | `git push` = live, free tier cukup |
| Cache / State | LocalStorage & React Context | Job queue, cache hasil audit |

### AI Models — Hybrid Strategy
| Task | Model | Alasan |
|------|-------|--------|
| Analisis 50+ SERP results (bulk) | Gemini 2.5 Flash | Cepat, paralel, murah — task repetitif |
| Klasifikasi poison sources (bulk) | Gemini 2.5 Flash | Volume tinggi, task sederhana |
| AI Visibility Score calculation | Gemini 2.5 Flash | Structured, formula-based |
| Final Executive Playbook | Gemini 2.5 Flash | Output yang dilihat juri — berkualitas tinggi |

### Data & Web Intelligence
| Bright Data Product | Peran | Mengapa Esensial |
|--------------------|-------|-----------------|
| **SERP API** | Ambil Google AI Overviews untuk 50+ query × 8 market | AI Overviews tidak ada di API publik manapun. Mustahil tanpa ini. |
| **Web Scraper API** | Ambil konten Reddit, LinkedIn yang dikutip AI | Pre-built scrapers untuk 660+ situs, output terstruktur langsung |
| **Scraping Browser** | Render JS penuh untuk halaman review dan forum dinamis | Halaman dinamis sangat JS-heavy, tidak bisa di-scrape biasa |

---

## 9. Folder Structure

```
narrative-shield-app/
├── src/
│   ├── app/
│   │   ├── page.tsx                  ← Landing page
│   │   ├── dashboard/page.tsx        ← Dashboard utama
│   │   ├── audit/nexafin/page.tsx    ← Halaman hasil audit (dynamic render)
│   │   └── api/
│   │       └── audit/route.ts        ← POST: trigger full audit
│   ├── lib/
│   │   ├── brightdata.ts             ← SERP API + Web Scraper helpers
│   │   ├── gemini.ts                 ← Gemini Flash bulk analysis
│   │   ├── avs.ts                    ← AI Visibility Score calculator
│   │   └── queries.ts                ← Query variation generator
│   ├── components/
│   │   ├── NarrativeMap.tsx          ← Heatmap intent × sentimen
│   │   ├── PoisonSources.tsx         ← Ranked source list
│   │   ├── AVSGauge.tsx              ← Score visualisasi
│   │   └── Playbook.tsx              ← Action cards
│   └── context/
│       └── AuditContext.tsx          ← History database local storage
```

---

## 10. Vercel Timeout — Solusi untuk Audit Panjang

Vercel Serverless Function default timeout: 10 detik (Hobby), 60 detik (Pro).
Audit 50+ query bisa melebihi batas ini. Solusi untuk hackathon:

**Opsi A — Vercel Pro (Recommended untuk demo):**
```typescript
// app/api/audit/route.ts
export const maxDuration = 300 // 5 menit, cukup untuk demo
```

Untuk hackathon, Opsi A lebih simpel dan cukup.

---

## 11. Metrics for Success

| Metrik | Target |
|--------|--------|
| Query coverage per audit | 50+ variasi |
| Market coverage | 5+ bahasa, 8+ negara |
| End-to-end latency (50 queries paralel) | < 60 detik |
| Poison source identification | >85% akurasi (manual spot-check) |
| AVS delta detection | Perubahan >10 poin terdeteksi dalam 24 jam |
| Action playbook | >3 rekomendasi spesifik per audit |

---

## 12. Demo Plan (15 Menit)

**Skenario:** Brand ride-hailing lokal fiktif "Gojek" ingin memantau representasinya. Tim PR mereka tidak tahu apa yang dikatakan AI ke ribuan calon pelanggan yang mencari mereka hari ini dibandingkan kompetitornya, "Grab".

| Menit | Aktivitas | Visual |
|-------|-----------|--------|
| 0–1 | Hook: ketik *"Gojek vs Grab"* di Google live — AI Overview muncul mengutip artikel lama yang sudah tidak relevan | Live browser |
| 1–3 | Input brand di UI, klik Audit | Progress: *"Querying 52 variations across 6 markets..."* |
| 3–6 | AI Narrative Map muncul: heatmap merah di kolom "comparative" dan "transactional" | Heatmap interaktif |
| 6–9 | Klik sel merah → verbatim AI Overview + sumber yang dikutip | Side-by-side: AI answer vs sumber aslinya |
| 9–11 | Competitor Benchmark: *"Di 34% query komparatif, AI menyebut kompetitor Grab sebagai alternatif lebih murah"* | Bar chart share of AI voice |
| 11–13 | Poison Sources list: artikel lama di posisi #1, forum Reddit di #2 | Ranked cards dengan impact score |
| 13–15 | Generate Playbook (Gemini): 5 tindakan spesifik dengan prioritas dan timeline | Action cards + AVS gauge |

**Penutup:** *"Semua ini mustahil tanpa Bright Data. Kami membuka web untuk era AI search visibility."*

---

## 13. Risks and Mitigations

| Risiko | Kemungkinan | Mitigasi |
|--------|-------------|----------|
| Google AI Overviews tidak muncul untuk semua query live | Tinggi | Sistem tetap catat "no AI Overview" sebagai data; gunakan fallback cache sebelum demo |
| Vercel timeout untuk 50+ queries | Sedang | Set `maxDuration: 300` di Pro tier; atau batasi query ke 12 variasi utama |
| Gemini Flash rate limit | Rendah | Implement retry dengan exponential backoff; batasi concurrency ke 10 parallel requests |
| Scraping Browser lambat untuk demo | Sedang | Tampilkan cached result jika API lambat merespon |

---

## 14. Why This Wins

**Originality:** Tidak ada alat yang secara eksplisit mengaudit AI-generated search answers dan memberikan corrective action. Ini adalah kategori baru: **AI Search Visibility Optimization (AISO)** — analog dengan SEO tapi untuk era AI search.

**Application of Technology:** Bright Data SERP API adalah satu-satunya cara mengakses Google AI Overviews secara konsisten dan dalam skala. Demo membuktikan ini dengan log real-time 50+ successful queries. Hybrid AI strategy (Gemini Flash) menunjukkan pemahaman mendalam tentang kecepatan vs kualitas.

**Business Value:** Setiap brand yang menghabiskan anggaran PR dan SEO kini memiliki blind spot baru. TAM-nya adalah seluruh pasar brand monitoring ($5.5B) yang sedang terdisrupsi oleh AI search.

**Presentation:** Hook dengan live Google search yang menampilkan AI Overview negatif adalah momen yang tidak bisa dibantah — konkret, langsung, dan relevan ke semua orang di ruangan.
