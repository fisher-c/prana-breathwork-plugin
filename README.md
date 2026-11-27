# Prana: Breathwork Meditation

Breathwork and pranayama for calm, focus, sleep, and energy, inside Claude.

Prana brings its public breathwork catalog and guided-session protocol into Claude. Ask about a technique, compare a few, get a conservative recommendation for how you want to feel, or follow a short guided session right in the conversation. When you want to keep practicing, open the matching session in the Prana app.

## What you can ask

- "Start a one-minute Box Breathing session"
- "I'm stressed before a meeting. Choose a one-minute breathing practice to help me calm down"
- "I want to wind down for sleep. What breathing practice should I try?"
- "Compare Box Breathing and Equal Breathing"

## Shortcut commands

In Claude Code, start a session with one command:

| Command | What it does |
| --- | --- |
| `/prana:breathe` | Starts a one-minute Box Breathing session |
| `/prana:breathe 4-7-8` | Starts the technique you name, for 1 minute. Common names work: `box`, `4-7-8`, `ujjayi`, `humming bee` |
| `/prana:breathe 4-7-8 5` | The technique you name, for the number of minutes you give (1 to 15) |
| `/prana:calm` | Picks and starts a gentle practice for stress |
| `/prana:focus` | Picks and starts a practice for focus |
| `/prana:sleep` | Picks and starts a wind-down practice for sleep |

Add a number of minutes to `calm`, `focus`, or `sleep`, for example `/prana:sleep 3`. For intermediate and advanced techniques, Claude shares the cautions and asks you to confirm before starting.

## What's included

- **Prana MCP server**, a remote Streamable HTTP server at `https://pranabreathworks.com/api/mcp`. It needs no sign-in.
- **Prana Breathwork Guide skill**, which helps Claude pick the right tool for each request and keep guidance brief.
- **Four shortcut commands** for Claude Code, listed above.

The server provides six read-only tools:

| Tool | What it does |
| --- | --- |
| `list_breathing_techniques` | Lists the published Prana techniques |
| `get_breathing_technique` | Explains one technique: steps, timing, and cautions |
| `compare_breathing_techniques` | Compares two to four techniques side by side |
| `recommend_breathing_session` | Suggests a conservative session from your stated preferences |
| `create_guided_breathwork_session` | Builds a short guided session with an in-chat timer where supported |
| `get_prana_session_link` | Returns a link to open the matching session in the Prana app |

## Breathing techniques

Prana includes 13 techniques. You can ask for any of them by name, and guided sessions run from 1 to 15 minutes in whole minutes.

### Beginner

| Technique | Also known as | Good for | Breath holds |
| --- | --- | --- | --- |
| Full Yogic Breathing | Dirgha | Relaxing, stress relief, balance, sleep | No |
| Equal Breathing | Sama Vritti | Stress relief, focus, balance | No |
| Alternate Nostril Breathing | Nadi Shodhana | Balance, focus, stress relief | No |
| Ocean Breath | Ujjayi | Focus, stress relief, relaxing | No |
| Humming Bee Breath | Bhramari | Stress relief, sleep, relaxing | No |
| Cooling Breath | — | Cooling, relaxing, stress relief | No |
| Calming Breath | 4-6 breathing | Relaxing, stress relief, balance | No |
| Box Breathing | Square breathing | Stress relief, focus, balance | Yes |
| Sleep Reset | 4-7-8 breathing | Sleep, relaxing, stress relief | Yes |

### Intermediate and advanced

These are stronger practices, and each has its own cautions, such as pregnancy, heart conditions, high blood pressure, or anxiety. Claude shares them when you ask about a technique or start a session.

| Technique | Also known as | Level | Good for | Breath holds |
| --- | --- | --- | --- | --- |
| Skull-Shining Breath | Kapalabhati | Intermediate | Energizing, cleansing | No |
| Bellows Breath | Bhastrika | Advanced | Energizing, cleansing | No |
| Right Nostril Breathing | Surya Bhedana | Advanced | Energizing, focus | No |
| Breath Retention | Kumbhaka | Advanced | Focus, balance | Yes |

## Privacy and safety

- No account or sign-in needed. The plugin works without a Prana account, and you don't need the Prana app to use it in Claude.
- Anonymous and read-only. The plugin doesn't access your Prana account, practice history, mood, biometrics, subscriptions, or health data, and it doesn't write anything.
- General wellness only. Prana doesn't diagnose, treat, or prescribe. Stop any practice if you feel dizzy, short of breath, or uncomfortable, and talk to a clinician about medical conditions.
- Sessions are short and start only when you ask for them.

Privacy policy: https://pranabreathworks.com/privacy
Terms: https://pranabreathworks.com/terms

## Support

- Website: https://pranabreathworks.com/ai
- Support: https://pranabreathworks.com/support
- Email: prana@pranabreathworks.com
