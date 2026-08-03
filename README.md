## Adarsh Shankar

Director and GM at [Iyara Labs](https://iyaralabs.com), an AI-native digital agency working
out of Dubai and San Francisco. Before that, email and AI consulting. MS in Marketing
Analytics from Purdue.

Most of what I build sits between a business process and a model: agent harnesses, event-
driven workers, and the unglamorous infrastructure that decides whether either one is
actually reliable.

### Things worth a look

**[skill-routing-eval](https://github.com/Adarsh350/skill-routing-eval)** — An A/B harness
for measuring whether the context you inject into every agent session changes what the
agent does. Runs both arms, because a score from the ON arm alone can't distinguish "the
map worked" from "the model didn't need it". On my own setup: 15/15 with the injection,
9/15 without. The more useful finding was the variance — three consecutive runs of an
unchanged map scored 13, 15 and 11, which is why it samples repeatedly and collapses by
majority instead of trusting a single pass.

**[claude-code-hooks](https://github.com/Adarsh350/claude-code-hooks)** — Three
zero-dependency hooks: one blocks credential-shaped strings from reaching source files,
one refuses to end a session that changed config without executing it, one suggests
compacting at a clean boundary. The interesting part is which way each fails. The secrets
guard fails open and never fires on `.env`, because a guard that blocks the correct answer
gets disabled within a day. The verification gate fails closed, because a silently skipped
gate is a broken config you find tomorrow.

**[windows-arm64-dev-fixes](https://github.com/Adarsh350/windows-arm64-dev-fixes)** — Eight
JavaScript toolchain failures on Windows 11 ARM64, each with the verbatim symptom, the
actual cause, and the fix. Most share one root cause — a package ships no `win32-arm64`
build — surfacing far from that fact as a `spawn EFTYPE`, a zero-byte binary, or an
`npm install` that exits 0 and installs nothing. All hit and resolved on a real machine.

**[graphify-github-obsidian](https://github.com/Adarsh350/graphify-github-obsidian)** —
Builds knowledge graphs from every repo in a GitHub account and syncs them into Obsidian,
unattended.

**[mailchimp-bounce-monitor-worker](https://github.com/Adarsh350/mailchimp-bounce-monitor-worker)**
— Cloudflare Worker handling Mailchimp unsubscribe, bounce, abuse and soft-bounce webhooks.
Deliverability degrades quietly, so the work is in the retry and idempotency paths rather
than the happy one.

### Working on

Agent evaluation, mostly. It is easy to make an agent setup feel better and hard to show
that it is, and the gap between those two is where most of the effort in this space is
currently going to waste.

### Elsewhere

Chess takes the rest of the time — 2264 rapid on Lichess, Arena International Master.
[deepgamecoaching.com](https://deepgamecoaching.com) is the coaching practice; its repo is
here too.
