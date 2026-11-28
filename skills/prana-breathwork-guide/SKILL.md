---
name: prana-breathwork-guide
description: Choose, explain, compare, conduct, or open conservative Prana breathing practices through the Prana MCP tools. Use for requests about breathwork or pranayama techniques, short breathing breaks for calm, focus, sleep preparation, energy, balance, or cooling, guided Prana sessions, and Prana app session handoff.
---

# Prana Breathwork Guide

Use Prana's public catalog and deterministic protocol for general-wellness breathwork. Keep the interaction grounded, brief, and explicit about what the anonymous plugin can and cannot know.

## Check the request before calling any Prana tool

If any of these conditions applies, answer directly and stop. Do not call even a read-only catalog tool for that request.

- Urgent symptoms, diagnosis, prescriptions, or a claim to treat or cure a condition: decline the medical request. For concerning symptoms, direct the user to appropriate urgent or emergency help. Do not offer breathwork as a remedy.
- Access to private records or a recommendation that depends on them: say that Prana cannot access those records. Do not ask the user to share them, guess their contents, or substitute a generic recommendation. Wait for a separate general-wellness request based on non-sensitive preferences.
- A session longer than 15 minutes, automatic playback, or a request to bypass an entitlement, onboarding, or safety check: explain the relevant limit. Do not prepare a session, return an app link, or propose a workaround.

## Choose the workflow

- For a named technique or an educational question, resolve its canonical id with `list_breathing_techniques`, then call `get_breathing_technique`. Skip the list call only when the user already supplied a canonical id.
- To compare two through four named techniques, call `get_breathing_technique` once for each and compare cadence, breath retention, intensity, common uses, duration options, and cautions. Do not add medical claims.
- For "what should I do?", collect only missing structured preferences and call `recommend_breathing_session`.
- For an in-chat practice, call `prepare_guided_breathwork_session` after the technique and supported duration are known.
- When the user wants a session in the Prana app ("open it in Prana", "in the app", "send me a link"), call `get_prana_session_link`, not `prepare_guided_breathwork_session`. For a Prana app handoff, call `get_prana_session_link` and present the returned HTTPS `url` as a clickable, user-initiated action. Use `deepLink` only in hosts that can open `prana://` links.

Do not call recommendation tools when the user only asks how a named practice works. Do not add alternative practices unless asked.
After a recommendation, do not prepare or conduct a session unless the user explicitly asked for guidance, a timer, or a session.

## Recommend a practice

Use only the tool's structured inputs: goal, available time, experience, intensity, whether eyes must stay open, whether to avoid retention, familiarity preference, and time context. Ask at most one concise question when a required choice cannot be reasonably inferred. Prefer conservative inputs when the user is unsure.

Describe a returned recommendation as a match for the preferences the result actually evaluated, not a diagnosis or an inference from private history. When `familiarPreferenceEvaluated` is false, do not imply that `preferFamiliar` affected the selection; disclose that this anonymous release cannot evaluate familiarity from personal history. Respect `no_confident_recommendation`; explain the conflict and offer to adjust one constraint.

## Conduct a session

Request a supported duration from the selected technique. Set the presentation mode to the host capability the user requested, use reduced motion when requested, and keep voice guidance off unless the host can actually speak timed cues.

Follow the returned phase timing and narration exactly. Use a local clock; do not poll the server for the next breath. Preserve quiet intervals and the stop instruction. Never claim audio played, a timer ran, or a session completed unless the host actually performed it.

If the host cannot reliably conduct the requested modality, offer a text protocol or a Prana app handoff.

Never offer or construct a session longer than 15 minutes. Do not offer a host-invented longer session, chain multiple sessions, or suggest pacing a Prana technique beyond 15 minutes after refusing an unsupported duration.

## Keep the safety boundary

- Treat all output as general wellness, not medical care or symptom interpretation.
- Tell the user to stop and return to natural breathing if they feel dizzy, strained, or uncomfortable.
- Do not solicit or send symptoms, diagnoses, heart-rate data, sleep data, mood logs, or other private health details to choose a practice.
- For urgent, severe, or concerning symptoms, do not recommend a breathwork protocol as a remedy; advise appropriate professional or emergency help.
- Do not expose or invent audio URLs, storage paths, premium access, or account data.

## State current limitations

This release is anonymous. It cannot read favorites, history, streaks, mood, biometrics, subscriptions, chat history, or saved preferences, and it cannot write session completion. Say so directly when asked. Use the public workflow only for a supported request.
