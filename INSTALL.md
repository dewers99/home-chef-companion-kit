# Installing the Home Chef Companion Kit

The kit is plain text — `AGENT.md`, the `skills/` folders, `templates/`, and
`reference/`. Anything that can read long instructions can run it. Pick your
tool below. Each guide states its honest limits; platforms change, so when in
doubt, check your tool's docs.

Two ways to get the files: (1) download the kit (ZIP) and attach the files to your AI
chat, or (2) give your AI the repo link or folder and let it
fetch the kit: https://github.com/dewers99/home-chef-companion-kit. Git users: `git clone https://github.com/dewers99/home-chef-companion-kit`.

---

## Muse AI (recommended)

1. Share the kit's repo/folder link with your Muse AI assistant, or paste in
   `AGENT.md` plus the `skills/` files you want.
2. Tell it: "Install this companion kit and start intake with me."

**Honest limits:** The persona persists per the platform's own capabilities.
What your Muse AI can store (profiles, pantry lists, saved recipes) depends on
the version you're using — check your tool's docs, or just ask your companion
what it can actually keep. The companion will never pretend it saved something
it can't.

## ChatGPT

Use **Projects**: create a project, upload the kit files (`AGENT.md`,
`skills/`, `templates/`, `reference/`) to the project, and start your
conversation there.

**Honest limits:** Context has limits — very long projects can lose track of
earlier details, and uploaded-file persistence is bounded by the platform.
Keep your profile and pantry files lean, and check your tool's docs for
current limits.

## Claude

Use **Projects**: create a project, upload the kit files to the project, and
chat inside it.

**Honest limits:** Project knowledge persists across conversations, but each
conversation still has a context limit — long threads can drop earlier
details. Uploaded files live with the project; check your tool's docs for the
current limits.

## Google Gemini

Use **Gems**: create a Gem, add the kit's instructions (`AGENT.md` content and
the skills), and save it.

**Honest limits:** A Gem keeps its instructions across sessions, but file
handling and long-term storage vary by version and surface (app vs. web).
Check your tool's docs — or ask the companion what it can actually save.

## Microsoft Copilot

Copilot chats don't keep a standing persona — **you'll need to re-attach the
kit each session.** Paste `AGENT.md` plus the skills you want at the start of
the conversation, then go.

**Honest limits:** No standing persona, no persistent memory of your profile or
pantry between chats. Saved recipes are copy-paste text you keep yourself.
Saying it plainly: Copilot works fine as a session-by-session cooking buddy,
but it won't remember you next week.

## Cursor / coding agents

Drop the kit files into your project workspace and point the agent at
`AGENT.md`. It's purely file-based — no special integration needed. Your
profile, pantry, and Recipe Box live as files in your workspace, which is the
most durable setup of all.

**Honest limits:** It's file-based, so everything the companion "remembers" is
a file you can see and edit. No magic — but no surprises either.

## Any other AI tool

Paste `AGENT.md` plus the skills you want into the tool's system/persona
prompt area, or attach them to the conversation. Plain-text portability is the
whole point: if it reads instructions, it can be your sous-chef.

---

## Recipe-storage capability matrix

Where can the companion actually write and save things? Match your
expectations to your platform:

| Platform | Persona persists? | Can the companion save files? | Recipes saved as… |
| --- | --- | --- | --- |
| Muse AI | Per platform capabilities | Where the tool supports files/workspace | Saved files or project content — ask your companion what's possible |
| ChatGPT (Projects) | Within the project | Files you upload (the companion can't add project files itself) | Project files (uploaded by you); long-project context limits apply |
| Claude (Projects) | Across conversations in the project | Files you upload (the companion can't add project files itself) | Project files (uploaded by you); conversation context still bounded |
| Google Gemini (Gems) | Yes, as a Gem | Varies by version | Depends on the app/web version — ask |
| Microsoft Copilot | No — re-attach each session | No persistent saves | Copy-paste text you keep yourself |
| Cursor / coding agents | Via workspace files | Yes — workspace files | Files in your workspace, fully yours |
| Any other tool | Depends on the tool | Depends on the tool | Ask the companion what it can actually keep |

**The standing rule:** the companion never pretends it saved something it
can't. Without real persistence, it says so plainly and offers the recipe as
copy-paste text you can keep yourself. No fake promises, ever.

---

## Updates

**First check:** one week after install. **Then:** weekly, monthly, or off —
your choice. The companion compares the repo's `VERSION` file against the
version it was installed from. If an update exists, it shows you exactly what
changed — never a silent apply, never "trust me." You decide.

**URL-installed kits:** if your companion re-fetches the kit from its link
every session, it's already current — no update check needed.

## Feedback

Two weeks after install, the companion will offer you an anonymous feedback
form — always skippable, never nagging, and not monitored in real time
(responses are only read by the kit's author, periodically). Saying "no
thanks" once means it won't ask again.

[Give your feedback here — anonymous, takes about 2 minutes.](https://tally.so/r/0QXMbQ)
