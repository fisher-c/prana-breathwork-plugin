---
description: Start a short focus breathing session chosen by Prana
argument-hint: "[minutes]"
---

The user wants a focus Prana breathing session now. They may be wanting to concentrate or get clear-headed. Extra details from the user: "$ARGUMENTS"

Use the Prana MCP tools and follow the `prana-breathwork-guide` skill.

1. Length: 1 minute unless the user gave whole minutes from 1 to 15. If they ask for more than 15, explain that Prana sessions run up to 15 minutes and use 15.
2. Call `recommend_breathing_session` with goal `focus`, that length, beginner experience, and gentle intensity, unless the user's details say otherwise. Don't ask follow-up questions unless something they said conflicts.
3. In one or two sentences, name the practice Prana chose and why it fits.
4. Running this command is the user's request for a guided session, so call `create_guided_breathwork_session` with the recommended technique and length. If an in-chat timer appears, let it be the only session surface. If none can be shown, give concise text guidance from the returned protocol.
5. Remind the user once to stop and return to natural breathing if they feel dizzy, strained, or uncomfortable.

This is general wellness, not medical care. If the user describes urgent or severe symptoms, don't start a session; point them to appropriate professional or emergency help instead. Don't claim a timer ran or audio played unless the host actually did it.
