# 📿 SmartaPuja — AI-Powered Hindu Puja Guide

> _"Aadipujyo Ganadhipa"_ — Lord Ganesha is worshipped first.

---

## 1. Background & Problem Statement

Most Hindus who do not have deep knowledge of **Smarta** and **Nitya Puja Kriya** struggle to find the right resources to read and chant mantras correctly. Although several websites (e.g., [stotranidhi.com](https://stotranidhi.com)) and printed books exist, they suffer from the following problems:

- **Fragmented resources**: Mantras and procedures are scattered across multiple books, websites, and PDFs with no single unified source.
- **Incorrect sequencing**: Users often do not know the correct order of pujas (e.g., Ganapati puja must precede all other pujas).
- **No swara guidance**: Most digital resources provide plain text without **Vedic swara (accent/intonation) markings**, which are critical for correct Vedic mantra chanting.
- **Language barriers**: Content is often available only in Sanskrit/Telugu script or only in English transliteration — rarely both, side by side.
- **No personalization**: Existing resources don't allow a user to compose a custom puja sequence for a specific day and get a consolidated, ordered guide.

This application aims to solve all the above by providing an **AI-powered, personalized, and correctly-sequenced puja guide** rooted in the **Telugu Smarta Vaidika** tradition as established by **Jagadguru Adi Shankaracharya**.

---

## 2. Target Audience

| Attribute        | Detail                                                                                         |
| ---------------- | ---------------------------------------------------------------------------------------------- |
| **Age Group**    | 30–60 years                                                                                    |
| **Demographics** | Telugu-speaking Hindu families, primarily Smarta Brahmins and devout practitioners              |
| **Tech Comfort** | Moderate — comfortable with smartphones and basic web apps; prefer simplicity over complexity   |
| **Use Context**  | Morning/evening puja at home; festival-specific pujas; daily Nitya Karma                       |
| **Geography**    | India (primarily Andhra Pradesh & Telangana), and Telugu diaspora worldwide (USA, UK, AU, etc.) |
| **Devices**      | Primarily mobile phones (Android/iOS via PWA); secondary: tablets and desktops                  |

---

## 3. Core Idea

Build a **Progressive Web Application (PWA)** with a clean, distraction-free UI that allows users to:

1. **Select** one or more pujas they wish to perform for the day.
2. **Receive** an AI-generated, correctly-sequenced guide containing:
   - Step-by-step ritual instructions following the **Shodashopachara (16-step)** puja format for deity-specific pujas.
   - Complete mantra text with **swara markings** (Udātta, Anudātta, Svarita) for Vedic mantras only.
   - Transliteration and/or translation in the selected language (English or Telugu).
3. **Read** the generated content in a paginated, book-like reading experience optimized for use during actual puja (hands-free friendly, large text, auto-scroll options).

### AI Intelligence — Sequencing Rules

The AI backend must understand and enforce the **traditional Smarta Vaidika puja sequence**, including but not limited to:

| Rule                                         | Example                                                                                                  |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Ganapati Puja always first**               | If user selects Vinayaka Puja + Venkateswara Puja → Vinayaka Puja comes first                            |
| **Sankalpa before any puja**                 | Achamana → Pranayama → Sankalpa must precede the main puja sequence                                      |
| **Ishta Devata puja in the middle**          | Main deity pujas are placed after Ganapati and preliminary rituals                                       |
| **Navagraha / supplementary pujas after**    | Navagraha puja, Sapta Saneeswara puja come after main deity pujas                                       |
| **Sahasranama parayanams after main puja**   | Vishnu Sahasranamam, Lalitha Sahasranamam follow their respective deity pujas                            |
| **Namaskarams / Govinda Namalu at the end**  | Govinda Namalu, Mantra Pushpam, and concluding namaskarams are placed last                               |
| **Festival-specific overrides**              | On Vinayaka Chavithi, the Vinayaka puja has extended rituals; on Kartika Pournami, deepa puja is central |
| **Panchayatana awareness**                   | Respect the Panchayatana order (Shiva, Vishnu, Devi, Surya, Ganesha) when multiple deities are selected  |
| **Sandhyavandanam is standalone**            | When selected, Sandhyavandanam is placed at the very beginning (before even Ganapati puja) as it is a Nitya Karma |

### AI Intelligence — Estimated Time

For each generated puja sequence, the AI must provide:

- **Total estimated time** for the complete sequence.
- **Per-section estimated time** (e.g., "Ganapati Shodashopachara Puja: ~20 min", "Vishnu Sahasranamam: ~30 min").
- Estimates should be based on average chanting speed for a moderately-paced devotee.

---

## 4. Curated Puja Catalog (MVP — 10 Items)

The MVP will support the following **10 pujas/stotras**. Deity-specific pujas follow the **Shodashopachara (16-step) format**. Stotras and Parayanams follow their traditional recitation structure.

### 4.1 Catalog with Structure

| #  | Puja / Stotra                    | Type                    | Format                                      | Swara Needed | Est. Time |
| -- | -------------------------------- | ----------------------- | ------------------------------------------- | ------------ | --------- |
| 1  | **Sri Ganapati Puja**            | Shodashopachara Puja    | 16-step puja + Ganapati Atharvashirsha      | Yes (mantras)| ~20 min   |
| 2  | **Sri Venkateswara Puja**        | Shodashopachara Puja    | 16-step puja + Venkateswara Stotram         | Yes (mantras)| ~25 min   |
| 3  | **Sri Satyanarayana Swamy Puja** | Shodashopachara Puja    | 16-step puja + Satyanarayana Vratham Katha  | Yes (mantras)| ~45 min   |
| 4  | **Sri Lakshmi Puja**             | Shodashopachara Puja    | 16-step puja + Sri Suktam + Lakshmi Stotram | Yes (mantras)| ~25 min   |
| 5  | **Sri Shiva Puja**               | Shodashopachara Puja    | 16-step puja + Rudram Chamakam (optional)   | Yes (mantras)| ~25 min   |
| 6  | **Vishnu Sahasranamam**          | Stotra / Parayanam      | Dhyana Shloka → 1000 Names → Phala Shruti   | No           | ~30 min   |
| 7  | **Lalitha Sahasranamam**         | Stotra / Parayanam      | Dhyana Shloka → 1000 Names → Phala Shruti   | No           | ~35 min   |
| 8  | **Hanuman Chalisa**              | Stotra                  | Doha → 40 Chaupais → Doha                   | No           | ~10 min   |
| 9  | **Govinda Namalu**               | Namasmarana / Stotra    | 108 Names of Lord Venkateswara              | No           | ~15 min   |
| 10 | **Sandhyavandanam**              | Nitya Karma (Daily)     | Achamana → Pranayama → Marjana → Arghya → Gayatri Japa → Upasthana → Abhivadana | Yes (mantras)| ~20 min   |

### 4.2 Shodashopachara (16-Step) Puja Structure

Each deity-specific puja (items 1–5) follows this standard 16-step structure, with deity-specific mantras at each step:

| Step | Name (Sanskrit)  | Name (Telugu)       | Action                                              |
| ---- | ---------------- | ------------------- | --------------------------------------------------- |
| 1    | Āvāhana          | ఆవాహనం              | Invocation — inviting the deity into the idol/image  |
| 2    | Āsana            | ఆసనం                | Offering a seat to the deity                        |
| 3    | Pādya            | పాద్యం               | Offering water to wash the deity's feet             |
| 4    | Arghya           | అర్ఘ్యం              | Offering water for ceremonial greeting              |
| 5    | Āchamanīya       | ఆచమనీయం             | Offering water for sipping/rinsing                  |
| 6    | Snāna            | స్నానం               | Ceremonial bathing of the deity                     |
| 7    | Vastra           | వస్త్రం              | Offering clothes                                    |
| 8    | Upavīta          | ఉపవీతం              | Offering sacred thread                              |
| 9    | Gandha           | గంధం                | Offering sandalwood paste                           |
| 10   | Pushpa           | పుష్పం               | Offering flowers                                    |
| 11   | Dhūpa            | ధూపం                | Offering incense                                    |
| 12   | Dīpa             | దీపం                | Offering lamp                                       |
| 13   | Naivedya         | నైవేద్యం             | Offering food                                       |
| 14   | Tāmbūla          | తాంబూలం             | Offering betel leaves and nuts                      |
| 15   | Nīrājana         | నీరాజనం             | Waving of the camphor/lamp (Arati)                  |
| 16   | Mantrapushpa     | మంత్రపుష్పం          | Offering flowers with Vedic mantras + Pradakshina + Namaskaram |

**Pre-puja rituals** (automatically prepended by AI for every session):
- Achamana (ఆచమనం)
- Pranayama (ప్రాణాయామం)
- Sankalpa (సంకల్పం)
- Ganapati Prarthana (గణపతి ప్రార్థన) — if Ganapati is not already the selected puja

**Post-puja rituals** (automatically appended by AI for every session):
- Kshamapana (క్షమాప్రార్థన) — seeking forgiveness for errors
- Mantra Pushpam (if not already included)
- Final Namaskaram

### 4.3 Sequencing Priority (When Multiple Items Selected)

When a user selects multiple items, the AI must order them as follows:

```
1. Sandhyavandanam (if selected) — always first, standalone Nitya Karma
2. Pre-puja rituals (Achamana, Pranayama, Sankalpa)
3. Sri Ganapati Puja (if selected) — "Aadipujyo Ganadhipa"
4. Sri Shiva Puja (if selected) — Panchayatana: Shiva first among main deities
5. Sri Venkateswara Puja (if selected)
6. Sri Lakshmi Puja (if selected)
7. Sri Satyanarayana Swamy Puja (if selected)
8. Vishnu Sahasranamam (if selected) — Parayanam after main pujas
9. Lalitha Sahasranamam (if selected) — Parayanam after main pujas
10. Hanuman Chalisa (if selected) — Supplementary stotra
11. Govinda Namalu (if selected) — always last among content items
12. Post-puja rituals (Kshamapana, Final Namaskaram)
```

---

## 5. Swara Notation — Specification

### 5.1 Scope

- **Swara markings apply ONLY to Vedic mantras** (mantras from the Vedas: Rigveda, Yajurveda, Samaveda, Atharvaveda).
- **Swara markings do NOT apply to stotras, shlokas, chalisa, or namasmarana** (e.g., Vishnu Sahasranamam, Hanuman Chalisa, Govinda Namalu are plain text).

### 5.2 Vedic Mantras Requiring Swara in the MVP Catalog

| Puja Context              | Vedic Mantras with Swara                                           |
| ------------------------- | ------------------------------------------------------------------ |
| Ganapati Puja             | Ganapati Atharvashirsha (Upanishad)                                |
| Venkateswara Puja         | Purusha Suktam, Narayana Suktam                                   |
***
This file was split into two focused documents.

Open the product-focused functional requirements here:
- [functional-requirements.md](functional-requirements.md)

Open the technical design and architecture details here:
- [tech-design.md](tech-design.md)

***
│              [Text View] [▶️ Play] [Karaoke Highlight]          │
└──────────────────┬──────────────────────────────────────────────┘
                   │  HTTPS (REST API)
                   ▼
┌─────────────────────────────────────────────────────────────────┐
│                API GATEWAY (AWS API Gateway)                     │
└──────────────────┬──────────────────────────────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────────────────────────────┐
│                BACKEND (NestJS on AWS Lambda)                    │
│                                                                 │
│  ┌──────────────┐    ┌─────────────────────────┐                │
│  │ Puja Rules   │    │  LangGraph Agent         │                │
│  │ Engine       │───▶│  (Sequencing + Content   │                │
│  │ (Ordering,   │    │   Generation Workflow)   │                │
│  │  Shodashopa- │    └──────────┬──────────────┘                │
│  │  chara       │               │                               │
│  │  Validation) │               ▼                               │
│  └──────────────┘  ┌────────────────────────┐                   │
│                    │  LLM (GPT-4o/Claude)   │                   │
│                    └────────────────────────┘                   │
│                               │                                 │
│                    ┌────────────────────────┐                   │
│                    │  Playwright Scraper    │                   │
│                    │  (stotranidhi.com etc) │                   │
│                    └────────────────────────┘                   │
│                                                                 │
│  ┌──────────────────────────────────────────────────────┐       │
│  │          V2: TTS ROUTING ENGINE                      │       │
│  │                                                      │       │
│  │  Input: Section text + swara annotations             │       │
│  │                                                      │       │
│  │  ┌─────────────────┐    ┌──────────────────────┐     │       │
│  │  │ Vedic Mantras?  │YES │ Swara→Pitch Mapper   │     │       │
│  │  │ (has swara      │───▶│ + Self-hosted TTS    │     │       │
│  │  │  annotations)   │    │ (Guru Murthy voice   │     │       │
│  │  └────────┬────────┘    │  + F0 conditioning)  │     │       │
│  │           │NO           └──────────┬───────────┘     │       │
│  │           ▼                        │                 │       │
│  │  ┌─────────────────┐              │                 │       │
│  │  │ ElevenLabs API  │              │                 │       │
│  │  │ (Guru Murthy    │              │                 │       │
│  │  │  cloned voice)  │              │                 │       │
│  │  └────────┬────────┘              │                 │       │
│  │           │                        │                 │       │
│  │           └────────┬───────────────┘                 │       │
│  │                    ▼                                 │       │
│  │           ┌─────────────────┐                        │       │
│  │           │ Audio + Word    │                        │       │
│  │           │ Timestamps      │                        │       │
│  │           └────────┬────────┘                        │       │
│  └────────────────────┼─────────────────────────────────┘       │
└───────────────────────┼─────────────────────────────────────────┘
                        │
           ┌────────────┼────────────┐
           ▼            ▼            ▼
   ┌──────────────┐ ┌────────┐ ┌──────────────┐
   │   DynamoDB   │ │ Redis  │ │  S3 + CDN    │
   │  (Storage)   │ │(Cache) │ │(Audio Cache) │
   └──────────────┘ └────────┘ └──────────────┘
```

---

## 10. Content Validation Strategy

Since no automated content review workflow is required, the following manual validation approach will be used:

| Aspect                    | Approach                                                                         |
| ------------------------- | -------------------------------------------------------------------------------- |
| **Primary SME**           | Product Owner (you) — cross-checks AI output against authoritative sources       |
| **Reference Sources**     | stotranidhi.com, TTD publications, traditional Smarta puja books                 |
| **Validation Frequency**  | Every new puja type generated is validated before marking as "production-ready"   |
| **Caching Validated Content** | Once a puja output is validated, it is cached in Redis/DynamoDB to avoid regeneration and potential drift |
| **Escalation Path**       | If complex Vedic accuracy questions arise, consult offline experts (priests/scholars) |
| **Swara Validation**      | Cross-reference Vedic mantra swaras with published TTD Veda Patasala texts       |
| **Audio Validation (V2)** | SME listens to TTS-generated audio samples and validates pronunciation, cadence, and swara accuracy before enabling play buttons for each puja |
| **Error Reporting**       | Simple "Report Error" link on each page (stores feedback in DynamoDB for review — lightweight, no workflow) |

---

## 11. Non-Functional Requirements

| Requirement          | Target                                                                    |
| -------------------- | ------------------------------------------------------------------------- |
| **Performance**      | Page load < 3s on 3G; AI generation response < 10s for typical request    |
| **Availability**     | 99.5% uptime (serverless architecture helps)                              |
| **Scalability**      | Handle 1,000 concurrent users at launch; auto-scale via Lambda            |
| **Offline**          | Last generated puja guide fully accessible offline via service worker     |
| **Accessibility**    | WCAG 2.1 AA compliant; screen reader support; adjustable font sizes       |
| **Security**         | HTTPS only; no PII stored in MVP; API rate limiting                       |
| **SEO**              | SSR ensures mantra content is indexable (for organic discovery)            |
| **Content Accuracy** | All mantras validated by SME against authoritative Smarta Vaidika sources  |
| **Localization**     | Full UI and content in English and Telugu; extensible to other languages   |
| **Authentication**   | None in MVP — no user accounts, no login required                         |
| **Audio Latency (V2)** | First-time TTS generation < 5s per section; cached playback instant     |
| **Audio Quality (V2)** | 44.1 kHz / 128 kbps MP3 minimum; natural-sounding Guru Murthy voice    |

---

## 12. MVP Scope Summary

| In Scope ✅                                                    | Out of Scope ❌                                      |
| -------------------------------------------------------------- | ---------------------------------------------------- |
| 10-item puja catalog (Shodashopachara + Stotras)               | Audio playback / TTS                                 |
| Puja multi-select UI with categorized list                     | Voice cloning                                        |
| AI-generated sequenced puja guide (Shodashopachara format)     | Video-based AI guidance                              |
| English and Telugu language support                             | Chat-based interaction                               |
| Swara notation for Vedic mantras only                          | User accounts / authentication                       |
| Paginated reading view with TOC                                | Feedback workflow (only simple error report link)     |
| Estimated time per puja and total                              | Calendar / Panchanga integration                     |
| PWA (installable + offline last guide)                         | Comprehensive catalog (50+ pujas)                    |
| Mobile-responsive design with dark mode                        | Native mobile apps (iOS/Android)                     |
| Keep-screen-awake during reading                               | Katha / story section                                |
| Pre-puja & post-puja rituals auto-included                     | Karaoke-style text highlighting                      |

---

## 13. V2 Scope Summary

| In Scope ✅                                                    | Out of Scope ❌                                      |
| -------------------------------------------------------------- | ---------------------------------------------------- |
| AI voice cloning of Guru Murthy's voice                        | Video-based AI guidance                              |
| Text-to-Speech for all stotras (ElevenLabs cloned voice)       | Chat-based interaction                               |
| Pitch-conditioned TTS for Vedic mantras (self-hosted)          | User accounts / authentication                       |
| Per-section play button with Play/Pause/Speed/Repeat           | Feedback workflow                                    |
| "Play All" sequential playback                                 | Calendar / Panchanga integration                     |
| Karaoke-style word highlighting synced to audio                | Catalog expansion beyond 10 pujas                    |
| Audio caching in S3/CDN + offline via service worker           | Community features                                   |
| Puja Katha stories with TTS narration                          | Native mobile apps                                   |
| Background audio playback (Media Session API)                  |                                                      |

---

## 14. Success Metrics (MVP)

| Metric                          | Target                                      |
| ------------------------------- | ------------------------------------------- |
| PWA installs                    | 500+ in first 3 months                      |
| Daily active users              | 100+ within 3 months of launch              |
| Average session duration        | > 10 minutes (indicating actual puja use)   |
| Content accuracy feedback       | < 5% error reports on generated content     |
| AI generation success rate      | > 95% (no failures/timeouts)                |
| Lighthouse PWA score            | > 90                                        |
| Swara rendering accuracy        | 100% on Chrome/Safari mobile (primary)      |

### V2 Success Metrics (Additional)

| Metric                              | Target                                          |
| ----------------------------------- | ----------------------------------------------- |
| Audio play rate                     | > 40% of sessions use play at least once        |
| Voice naturalness rating (SME)      | > 4/5 on subjective quality scale               |
| Vedic swara pitch accuracy          | > 85% F0 contour match vs reference recordings  |
| TTS generation latency (first play) | < 5 seconds for a single section                |
| Audio cache hit rate                | > 80% (most plays served from S3/CDN cache)     |

---

## 15. Risks & Mitigations

| Risk                                                  | Impact | Mitigation                                                                            |
| ----------------------------------------------------- | ------ | ------------------------------------------------------------------------------------- |
| LLM generates incorrect mantra text or sequence       | High   | SME validation + cache validated outputs; RAG over verified sources                   |
| Swara notation rendering inconsistent across devices   | Medium | Extensive cross-browser testing; fallback to inline text notation with legend          |
| stotranidhi.com blocks scraping                       | Medium | Build own curated database; use scraping only as supplementary source                 |
| High LLM API costs at scale                           | Medium | Cache all 10 puja combinations after validation; use LLM only for novel combinations |
| Target audience unfamiliar with PWA install            | Medium | Clear onboarding flow with install prompts; share via WhatsApp links                  |
| Content sensitivity (religious accuracy)               | High   | SME review of every puja before production release; escalation to offline experts      |
| Telugu Unicode rendering issues on older devices       | Low    | Test on common Indian Android devices; provide English fallback                       |
| Voice clone doesn't sound natural enough (V2)          | High   | Use 2-hour high-quality source; ElevenLabs Professional tier; iterative SME review    |
| Vedic swara pitch TTS not accurate enough (V2)         | High   | Phased approach — launch V2 with standard TTS fallback; improve pitch model iteratively; display disclaimer |
| ElevenLabs API cost at scale (V2)                      | Medium | Cache all generated audio in S3; TTS called only once per unique text section         |
| Self-hosted GPU costs for Vedic TTS (V2)               | Medium | Use spot instances; batch-generate audio during off-peak; serve from S3 cache         |
| Guru Murthy's consent for voice cloning (V2)           | High   | Obtain written consent before any cloning work; credit him prominently in the app     |

---

## 16. Glossary

| Term                    | Definition                                                                                        |
| ----------------------- | ------------------------------------------------------------------------------------------------- |
| **Smarta**              | A tradition within Hinduism following Adi Shankaracharya, emphasizing worship of five deities      |
| **Vaidika**             | Pertaining to the Vedas; Vedic rituals and mantras                                                |
| **Shodashopachara**     | The 16-step formal worship procedure (ṣoḍaśa = 16, upachāra = offering/service)                   |
| **Nitya Puja**          | Daily worship rituals performed at home                                                           |
| **Nitya Karma**         | Mandatory daily rituals (e.g., Sandhyavandanam) that must be performed regardless                  |
| **Swara**               | Vedic accent/intonation markings (Udātta, Anudātta, Svarita) essential for correct mantra chanting |
| **Sankalpa**            | Formal declaration of intent before beginning a puja                                              |
| **Panchayatana**        | Worship of five deities (Shiva, Vishnu, Devi, Surya, Ganesha) as established by Adi Shankaracharya |
| **Govinda Namalu**      | A series of 108 names of Lord Venkateswara, typically recited at the conclusion                    |
| **Mantra Pushpam**      | A Vedic hymn from the Taittiriya Aranyaka, recited at the end of worship                          |
| **Katha**               | A devotional story associated with a specific vratham/puja                                        |
| **Parayanam**           | Systematic recitation/chanting of a sacred text (e.g., Sahasranamam)                              |
| **Sandhyavandanam**     | Daily twilight prayer ritual mandatory for dvijas (twice-born), centered around Gayatri Japa        |
| **Voice Cloning**       | AI technique to create a synthetic voice model that mimics a specific person's voice from audio samples |
| **F0 Contour**          | Fundamental frequency trajectory over time — represents pitch patterns in speech/chanting          |
| **TTS**                 | Text-to-Speech — converting written text into spoken audio using AI synthesis                      |
| **PWA**                 | Progressive Web Application — a web app with native app-like capabilities                         |
| **LangGraph**           | A framework for building stateful, multi-step AI agent workflows using LangChain                  |
| **LangSmith**           | An observability platform for monitoring and debugging LLM-powered applications                    |

---

## Appendix A: V2 Voice Cloning — Asset & Readiness Inventory

| Item                                       | Status        | Notes                                                          |
| ------------------------------------------ | ------------- | -------------------------------------------------------------- |
| Guru Murthy audio (Satyanarayana Vratham)  | ✅ Available   | ~2 hours, sufficient for Professional Voice Clone training     |
| Guru Murthy written consent for cloning    | ❌ Needed      | **Must obtain before any V2 work begins**                      |
| ElevenLabs Professional account            | ❌ To set up   | Requires paid plan for Professional Voice Cloning              |
| Self-hosted TTS model selection            | ❌ To evaluate | Evaluate Coqui TTS, Fish Speech, VITS, FastPitch for Vedic use |
| Audio pre-processing pipeline              | ❌ To build    | FFmpeg + Whisper transcription + segmentation scripts          |
| Swara-to-F0 pitch mapping rules            | ❌ To define   | Requires SME input on exact Hz ranges for each swara level     |
| GPU infrastructure for self-hosted TTS     | ❌ To provision | AWS EC2 g5.xlarge or SageMaker endpoint                       |
| Supplemental recordings from Guru Murthy   | ⚠️ Optional    | Additional 15–30 min recordings for other puja styles if needed |

> **Key Prerequisite**: Obtain **written consent from Guru Murthy** for voice cloning before initiating any V2 audio development. This is both an ethical and potentially legal requirement. Credit should be given prominently in the app (e.g., "Voice: Sri Guru Murthy Garu, Annavaram Devasthanam").

---

## Appendix B: V2 TTS Cost Estimation

| Component                 | Estimated Cost                                                    |
| ------------------------- | ----------------------------------------------------------------- |
| ElevenLabs Professional   | ~$99–$330/month (depending on character usage tier)               |
| ElevenLabs per-character  | ~$0.30 per 1,000 characters (after plan quota)                   |
| S3 audio storage          | ~$0.023/GB/month (negligible for cached MP3 files)               |
| CloudFront bandwidth      | ~$0.085/GB (first 10 TB/month)                                   |
| EC2 GPU (g5.xlarge)       | ~$1.006/hour on-demand; ~$0.40/hour spot                         |
| **Cost optimization**     | Cache all TTS output in S3 → ElevenLabs API called only once per unique text section. For 10 pujas × ~50 sections each × avg 200 chars = ~100,000 chars total one-time cost ≈ **$30 one-time**, then served from cache indefinitely. |

> With aggressive caching, the recurring TTS cost is near-zero after initial generation of all puja audio. GPU costs for the self-hosted Vedic TTS model can be minimized using batch generation during off-peak hours and spot instances.

---