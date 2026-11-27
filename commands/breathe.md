---
description: Set up a guided Prana breathing session (Box Breathing for 1 minute by default)
argument-hint: "[technique] [minutes]"
---

The user wants a guided Prana breathing session now. Their request: "$ARGUMENTS"

Use the Prana MCP tools and follow the `prana-breathwork-guide` skill.

1. Work out the technique and length from the request:
   - No technique named: use Box Breathing (`box`).
   - A technique named in any common form, such as "4-7-8", "ujjayi", "bee breath", "square breathing": resolve it to its canonical id with `list_breathing_techniques`. If nothing matches, say so briefly and list the beginner techniques to choose from. Don't guess.
   - No length given: 1 minute. A length must be whole minutes from 1 to 15. If they ask for more than 15, explain that Prana sessions run up to 15 minutes and offer 15. Never chain sessions to go longer.
2. If the technique is intermediate or advanced, or uses breath holds the user may not expect, call `get_breathing_technique` first. Share its cautions in a sentence or two and ask the user to confirm before you continue.
3. Call `prepare_guided_breathwork_session` with that technique and length. If an in-chat timer appears, it starts only when the user presses start; let it be the only session surface: don't add a second timer or repeat the steps. If no timer can be shown, give concise text guidance from the returned protocol.
4. Remind the user once to stop and return to natural breathing if they feel dizzy, strained, or uncomfortable.

Don't claim a timer ran or audio played unless the host actually did it.
