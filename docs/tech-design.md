# SmartaPuja — Technical Design

This document contains the technical and architecture-focused sections for implementation, integrations, and infrastructure. It is intended for full-stack and AI integration specialists.

## 1. Tech Stack (Frontend)
- Framework: Next.js 14+ (App Router, SSR & Server Components)
- Language: TypeScript
- Styling: Tailwind CSS + shadcn/ui
- PWA: Service worker, Web App Manifest
- State Management: React Context + Zustand
- Internationalization: next-intl or react-i18next
- Text Rendering: custom rendering techniques for Vedic swara marks
- Audio Playback: HTML5 Audio API + Media Session API

## 2. Backend & AI Orchestration
- API Framework: NestJS (TypeScript)
- AI Orchestration: LangGraph (agent workflow graphs)
- Observability: LangSmith for tracing and evaluation of LLM calls
- LLM Provider: OpenAI GPT-4o / Anthropic Claude (configurable)
- Web Scraping: Playwright for authoritative sources when needed
- Cache: Redis for frequently requested sequences
- Database: DynamoDB for generated content history and cached guides
- API Protocol: REST for MVP (GraphQL optional later)

## 3. V2 — Voice Cloning & TTS Infrastructure
### Voice Cloning (Stotras)
- Use ElevenLabs Professional Voice Clone trained on ~2 hours of high-quality Guru Murthy audio for stotras and non-Vedic content.

### Vedic Mantras (Pitch-Controlled TTS)
- Self-hosted TTS (Coqui TTS / Fish Speech / VITS-based) fine-tuned with pitch/F0 conditioning to accurately reproduce Udātta/Anudātta/Svarita contours.
- Pre-processing: FFmpeg (noise reduction, normalization), Whisper for transcription and alignment.
- Swara-to-pitch mapper service: converts swara annotations to F0 contour sequences for conditioning.

### TTS Routing Logic
- If section is Vedic (swara annotated): route to self-hosted pitch-conditioned TTS with swara→F0 input.
- Else: route to ElevenLabs API using the cloned voice.

### Audio Caching & Delivery
- Cache generated audio in S3 and serve via CloudFront CDN.
- Service worker caches previously played audio for offline playback.
- Word-level timestamps for karaoke highlighting via ElevenLabs timestamps or forced alignment for self-hosted model.

## 4. Architecture Overview
High-level diagram (textual):

```
USER (PWA Next.js)
  ↕ HTTPS
API Gateway → Backend (NestJS + LangGraph) → LLMs (OpenAI/Claude)
                     ↘ Playwright (scraper)
                     ↘ TTS Router → ElevenLabs / Self-hosted TTS
                     ↘ Redis / DynamoDB / S3
```

## 5. Features — Implementation Notes
- Sequencing & Rules Engine: a domain rules module (deterministic) to apply Smarta sequencing before/after LLM generation.
- RAG (Retrieval-Augmented Generation): use cached authoritative snippets and Playwright-scraped references for high-accuracy outputs.
- Caching Strategy: validate once via SME, then persist canonical outputs in DynamoDB/Redis to avoid regeneration cost.
- Swara Rendering: combine Unicode + CSS techniques and provide inline fallback markers when rendering is unsupported.

## 6. Infrastructure & CI/CD
- IaC: AWS CDK (TypeScript)
- Cloud: AWS for Lambda, API Gateway, S3, CloudFront, DynamoDB, Redis (ElastiCache), EC2/SageMaker for TTS inference
- Local development: LocalStack
- CI/CD: GitHub Actions → CDK Deploy
- Monitoring: CloudWatch + LangSmith + Sentry for frontend

## 7. Data Flow & Storage
- Generated guides stored in DynamoDB (versioned).  
- Cache hot items in Redis for low-latency reads.  
- Audio assets stored in S3 + served via CloudFront; service worker caches for offline.

## 8. Security & Compliance
- HTTPS everywhere, API rate limiting, minimal/no PII in MVP.
- For voice cloning: obtain written consent from voice donor before storing or using voice assets.

## 9. Testing & Validation
- Unit tests for rules engine, sequence generation, and TTS routing logic.
- Integration tests for LLM orchestration flows (LangGraph) with deterministic input/output checks.
- E2E tests for PWA flows (selection → generate → read → play audio), run in CI with Playwright.
- Load test the API and TTS endpoints; tune caching to meet latency targets.

## 10. Observability & Cost Controls
- Trace LLM calls and agent workflows via LangSmith.
- Cache validated outputs aggressively to reduce LLM/TTS costs.
- Use S3 + CDN to minimize repeated TTS calls.

## 11. Architecture Diagram & Component Responsibilities
- Frontend: Next.js PWA, pagination, swara rendering, audio playback, UI for selection and previews.
- Backend: NestJS APIs, LangGraph orchestration, domain rules engine, cache layer.
- AI Services: LLMs for content generation; TTS for audio synthesis (ElevenLabs + self-hosted for Vedic swara).
- Infra: AWS for storage, compute, CDN, and optional GPU inference hosts.

## 12. V2 Voice Cloning Pipeline & Notes
- Pipeline: audio pre-process → transcription/alignment → segmentation → ElevenLabs clone training + self-hosted fine-tuning for pitch control.
- Validation: SME review for swara accuracy; automated F0 DTW checks for pitch contour similarity.
- Fallback: if pitch-conditioned TTS is not production-ready, use ElevenLabs for all content with a user-facing disclaimer.

## 13. Appendices
### Appendix A: Asset & Readiness Inventory
- Guru Murthy audio: available (~2 hours) — obtain written consent before cloning.
- ElevenLabs account: required for professional clone.
- Self-hosted model: evaluate Coqui/Fish/VITS options.

### Appendix B: TTS Cost Estimation
- ElevenLabs: subscription + per-character costs; S3 and CloudFront for storage and delivery; EC2 GPU for self-hosted inference.

---

For product-level functional requirements, see: [functional-requirements.md](functional-requirements.md)
