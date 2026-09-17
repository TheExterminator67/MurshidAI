Murshid · مرشد
A multi-agent AI advisor for Emirati entrepreneurs, prototyped for the Khalifa Fund for Enterprise Development (KFED).

🏆 4th Place — 42AD Summer Program Hackathon (Khalifa Fund challenge track, July 2026)

🔗 Live demo: murshid-ai-beta.vercel.app

What it is
Murshid is Arabic for "guide." Beneficiaries — small business owners like a home baker in Al Ain — talk to Murshid over WhatsApp the way they naturally speak: Emirati Arabic and English mixed mid-sentence, by text or voice note. Behind the conversation, four specialized AI agents cooperate to profile the entrepreneur, recommend funded KFED programs with real citations, watch for funding opportunities, and — crucially — hand the case to a human advisor the moment the AI is no longer confident it should answer alone.

The core pitch: an AI that knows its limits. Murshid doesn't pretend to be a lawyer or a banker. When a question crosses into territory like loan restructuring, it escalates to a human advisor — and arrives with a bilingual briefing document already prepared, saving roughly two hours of prep.

The four agents
Agent	Role
Listener · المنصت	Intake — transcribes bilingual voice notes (handling Arabic/English code-switching and Emirati dialect), classifies intent, and keeps the beneficiary's profile current (business type, location, stage, growth signals).
Planner · المخطط	Recommendation — builds stepped program pathways from the KFED document corpus. Every recommendation carries a real citation (e.g. "Ruwad Program Guide, p.3") so advisors can verify the source.
Scout · الكشّاف	Proactivity — watches funding windows, deadlines, and market signals, firing unprompted alerts when a beneficiary matches (e.g. "Micro-financing window opens Monday — matches 4/5 criteria.").
Safety Net · شبكة الأمان	Guardrails — scores the system's confidence on every turn. Below a 40% threshold, it triggers escalation: generating a bilingual Advisor Brief and handing the case to a human.
Each agent owns a consistent color throughout the interface, so an advisor can read the activity feed at a glance.

Two screens
Mission Control — the cinematic showcase screen (1920×1080, dark Gulf-night navy). Three zones: a WhatsApp-style beneficiary conversation with mixed Arabic (RTL) / English (LTR) messages and a playable voice note; a live agent activity timeline; and a case panel with a beneficiary profile, a numbered recommended funding pathway, and a signature confidence meter — a thin gold arc that drains through amber to ember-red as confidence drops, culminating in a full-screen escalation takeover with a bilingual Advisor Brief.

A keyboard-driven demo mode (→ / ← to step through a 6-beat story, A to auto-play, R to reset) walks through the whole arc: standby → voice note arrives → Planner issues a pathway → Scout alert → confidence drain → escalation.

Workspace — the advisor's day-to-day back office (light "Industry" design language), with seven sections: Overview (usage vs. monthly limits, task counts, trends), Agents (per-agent status and stats), Tasks (full task list with detail drill-down and actions), Categories (the five capability areas), Activity/History (a searchable audit trail), Usage & Limits (deep metering and projections), and Settings (escalation thresholds, notifications, language).

Design language
Palette: deep Gulf-night navy ground; Khalifa Fund gold reserved almost exclusively for the confidence arc and escalation moments; warm sand for text and citations; one dawn-coral accent for Scout alerts.
Typography: IBM Plex Sans Arabic — a matched bilingual family carrying both scripts — with a condensed geometric face for labels and the wordmark.
Motion: one orchestrated sequence (the escalation takeover) plus restrained micro-motion elsewhere (feed slide-ins, agent pulses). prefers-reduced-motion is respected throughout.
Current status
This is a hackathon prototype: everything currently runs on mock data — nothing is live. The mocks are deliberately isolated so a real backend can drop in without touching the UI:

Mission Control is driven by a single pollEvents() function that returns the messages, events, confidence, and profile state for the current story beat — swap its body for a real API call with the same return shape.
Workspace is driven by one mock module, workspace-data.js, exposing a fetchWorkspace() function (with simulated latency for loading states) — replace it with real endpoints.
The 60-second pitch
Murshid is a WhatsApp-native AI advisor for Khalifa Fund entrepreneurs. Four agents work every conversation: the Listener understands mixed Arabic-English voice notes, the Planner recommends real KFED programs with page-level citations, the Scout proactively flags funding windows, and the Safety Net watches confidence on every answer. When a question is beyond the AI — watch the gold arc drain — it doesn't guess: it escalates to a human advisor with a bilingual brief already written, saving two hours of prep. The whole system is auditable: every task, every unit of usage, every escalation is tracked in the advisor workspace.

License
Released under the MIT License.
