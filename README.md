# AI Hotel Booking Assistant

An AI-powered front desk for hotels — guests chat with an assistant that answers questions about rooms, rates, amenities, and services in real time, across one property or an entire chain.

Built with **n8n** automation and an **AI Agent** model, embedded into any hotel website as a lightweight chat widget.

---

## What it does

A hotel website is usually a brochure: photos, a phone number, maybe a contact form. This replaces that with a front desk that never sleeps.

- A guest opens the chat on the website
- Asks a question in plain language — *"What rooms are free this weekend?"*, *"Do you have a family room under $150?"*, *"Is breakfast included?"*
- An AI agent reads the question, checks the hotel's room and rate data, and replies in seconds
- The conversation remembers context, so guests can ask follow-up questions naturally without repeating themselves

No forms. No hold music. No waiting on a reply.

---

## Why it matters

| Without automation | With this assistant |
|---|---|
| Guest emails or calls and waits for a reply | Guest gets an answer instantly, any time of day |
| Staff repeat the same questions about rates, rooms, and amenities all day | The assistant handles repetitive questions; staff focus on guests who need a human |
| Each property needs its own contact point | One assistant can answer for a single hotel or an entire multi-property chain |
| No record of what guests are actually asking | Every conversation is tracked by session, surfacing patterns in guest demand over time |

---

## How it works

```
 Guest types a question
          │
          ▼
   Website chat widget
          │  (sends message + session ID)
          ▼
     n8n Webhook
          │
          ▼
      AI Agent ────────► reads hotel data (rooms, rates, amenities, services)
          │
          ▼
   Simple Memory ───────► recalls this guest's earlier messages in the same chat
          │
          ▼
   Reply sent back to the chat widget
```

**In plain terms:**

1. The website sends the guest's message to an n8n workflow, tagged with a session ID unique to that conversation.
2. The AI agent reads the message and pulls in relevant hotel data before answering.
3. A memory layer keeps track of the conversation so far, so the assistant doesn't lose context mid-chat.
4. The reply is sent straight back into the chat widget on the website.

Every part of this is modular. The hotel data source can be swapped for a live booking system, the AI model can be upgraded, and additional automations — confirmation emails, payment links, staff alerts — can be added to the same workflow without touching the website.

---

## Core features

- **Natural-language Q&A** — guests ask questions however they'd naturally phrase them, no rigid menus or keywords required
- **Session-based memory** — each conversation is tracked independently, so the assistant keeps context without mixing up different guests
- **Multi-property aware** — works for a single hotel or filters answers by property across a chain
- **Always available** — runs 24/7 with no staffing required to keep it online
- **Lightweight integration** — added to any website as a small embeddable chat widget, no rebuild of the existing site needed

---

## Tech stack

| Layer | Tool |
|---|---|
| Automation | [n8n](https://n8n.io) — visual workflow automation |
| AI reasoning | LLM-powered AI Agent node |
| Conversation memory | Session-based chat memory (per-guest history) |
| Hotel data | Structured data — rooms, rates, amenities, services |
| Frontend | Embeddable HTML/JS chat widget |

---

## Status

This is a working assistant, demonstrated on a sample hotel website with real chat functionality. Connecting it to a live property management or booking system is the natural next step for production use.
