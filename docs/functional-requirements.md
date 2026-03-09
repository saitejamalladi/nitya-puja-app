# SmartaPuja — Functional Requirements

## Overview
A product to provide an AI-powered, personalized, and correctly-sequenced puja guide rooted in the Telugu Smarta Vaidika tradition. Focus is on user-facing behavior, flows, content, and acceptance criteria. 

## 1. Background & Problem Statement
Most users lack a single unified source for Smarta/Nitya puja procedures and Vedic swara-aware mantras. The app must consolidate correct sequences, provide swara markings for Vedic mantras, support English and Telugu, and enable personalized puja composition.

## 2. Target Audience
- Age: 30–60
- Telugu-speaking Hindu families settled abroad, Smarta practitioners
- Devices: Primarily mobile (PWA), also tablets and desktops
- Use Context: Morning/evening puja, festival-specific pujas, Nitya Karma

## 3. Core Product Idea
- Allow users to select one or more pujas for a session.
- Generate a consolidated, ordered puja guide following Smarta Vaidika sequencing rules.
- Provide mantra text with swara markings for Vedic mantras, transliteration and/or translation (English or Telugu).
- Present content in a paginated, book-like reading experience optimized for live puja use.

## 4. Sequencing & Business Rules
The AI must enforce these domain rules when composing sequences:
- Ganapati Puja (Vinayaka) should be first if selected.
- Pre-puja rituals (Achamana, Pranayama, Sankalpa) must precede main pujas.
- Main deity pujas follow Ganapati and preliminary rituals.
- Supplementary pujas (Navagraha, Sapta Saneeswara) occur after main pujas.
- Sahasranama parayanams follow their respective deity pujas.
- Final namaskarams (Govinda Namalu, Mantra Pushpam) conclude the session.
- Festival-specific overrides (e.g., Vinayaka Chavithi) must be supported.
- Sandhyavandanam, if selected, is standalone and placed at the very beginning.
- Respect Panchayatana ordering when multiple deities are selected.

## 5. Estimated Time
- The guide must present total estimated duration and per-section estimates based on average chanting speed for a moderately-paced devotee.

## 6. MVP Puja Catalog (User-visible items)
The product will expose these 10 items in MVP:
1. Sri Ganapati Puja — Shodashopachara (16-step) + Ganapati Atharvashirsha (swara)
2. Sri Venkateswara Puja — Shodashopachara + deity stotram
3. Sri Satyanarayana Swamy Puja — Shodashopachara + vratham katha
4. Sri Lakshmi Puja — Shodashopachara + Sri Suktam
5. Sri Shiva Puja — Shodashopachara + Rudram/Chamakam (optional)
6. Vishnu Sahasranamam — Parayanam (no swara)
7. Lalitha Sahasranamam — Parayanam (no swara)
8. Hanuman Chalisa — Stotra (no swara)
9. Govinda Namalu — 108 names (no swara)
10. Sandhyavandanam — Nitya Karma with Gayatri japa (swara where applicable)

## 7. Shodashopachara (16-step) Puja Structure (Displayed to Users)
Each deity-specific puja must display the 16 standard steps with deity-specific mantras and brief ritual instructions (what the user does physically). The app must automatically include pre-puja rituals and post-puja rituals for every generated session.

## 8. Swara Notation (Product Scope)
- Swara markings apply ONLY to Vedic mantras (from the Vedas). Stotras, shlokas, chalisa, and namasmarana remain plain text.
- The app will render Udātta, Anudātta, and Svarita markings visually and include a legend explaining them.
- Provide a fallback inline-notation (e.g., simple markers) when swara rendering is unavailable on a device.

## 9. User-Facing Features (MVP)
- Puja selection interface with categorized list and multi-select capability.
- Language toggle: English (default) and Telugu. Users choose transliteration vs native script.
- Preview of AI-determined order before final generation.
- Generate My Puja Guide button to produce the consolidated guide.
- Structured output that includes section headers, step-level instructions, mantras (with swara where applicable), translations/meanings, and per-section time estimates.
- Paginated, book-like reading experience optimized for live puja: large text, auto-scroll option, page navigation, TOC, and progress indicator.
- Dark mode and adjustable font sizes for readability.
- Keep-screen-awake functionality during active reading.
- Offline access to the last generated guide.

## 10. Accessibility & Localization
- WCAG 2.1 AA compliance goals: readable fonts, screen-reader friendly markup, focus management for pagination.
- Full UI and content support for English and Telugu; transliteration options available.

## 11. Content Validation & SME Flow
- Provide an in-app "Report Error" option for users to flag inaccuracies.

## 12. Non-Functional Requirements (High-level)
- Performance: fast generation and responsive UI for mobile devices.
- Availability: reliable uptime for primary flows.
- Offline: last generated guide accessible offline.
- Security & Privacy: HTTPS, minimal/no PII in MVP.
- Scalability: handle initial expected user load; cache validated outputs to reduce repeated work.

## 13. MVP Scope Summary
In scope:
- 10-item puja catalog, AI-generated sequenced guides, English & Telugu, swara notation for Vedic mantras, paginated reading view, estimated times, PWA installable/offline last guide.
Out of scope for MVP:
- Voice cloning, full chat-based interaction, calendar/Panchanga integration, community features.

## 14. Success Metrics (Product)
- PWA installs and DAU targets, average session duration, content accuracy feedback rates, AI generation success rate, swara rendering accuracy on primary mobile browsers.

---

For technical implementation details, see the Tech Design document: [tech-design.md](tech-design.md)
