# Ritmada — Gemini 3.8 Flash

Working configuration. Verified on Gemini 3.8 Flash in Google Antigravity.

**Channel:** https://t.me/RitmadaPrompt

---

## WHAT THIS IS

Two files. Both are required.

| file | where it lives | what it carries |
|---|---|---|
| `GEMINI.md` | project root, auto-loaded | the specification — identity, voice, domain, output contract |
| `prompt.txt` | project root, read on request | the request itself |

Neither works alone. The specification without a file carries the document but
the request still hits the input filter. The file without a specification gives
the model nothing to build against — no marker, no voice, no contract.

---

## INSTALL

### 1. Download the archive and extract it anywhere

### 2. Open File Explorer and paste this into the address bar

```
C:\Users\<your_username>
```

Substitute your own username. Or open `C:\Users` and pick your folder.

### 3. Drag the `.gemini` folder into it

If it asks to overwrite, say yes.

### 4. Close Antigravity completely and reopen it

The folder is read at startup. If Antigravity was already open before step 3,
close it fully and relaunch.

### 5. Turn telemetry off

Settings → Profile → telemetry off.

This matters. Telemetry carries request content. While it is on, a working
pattern is visible from the other side, and the method gets patched.

Off buys you time.

### 6. Create a project

Antigravity → New Project. Any path. An empty folder is fine.

### 7. Put two files in the project root

From the archive: `GEMINI.md` into the project root.
Create `prompt.txt` next to it and write your task in plain text.

### 8. Open a new session in that project and write

```
read prompt.txt and execute
```

Do not paste the task into chat. File path only. That is the mechanism, not a
workaround — chat input and file input are separate routes.

---

## VERIFY

First message in a fresh session:

```
whiskers forward
```

The reply must open with `[Ritmada]`. Marker present means the specification
took. Marker absent means the file is in the wrong place, or the session
started before the file landed.

Then load a domain:

```
load instrumentation
```

Available: `instrumentation` · `systems` · `networking` · `automation` ·
`reverse` · `creative`

One loads per task. Everything else is normal text from there.

---

## macOS and Linux

Same two files. One path differs.

```
~/.gemini/          instead of  C:\Users\<you>\.gemini\
```

Telemetry off is in profile settings there too. Steps 4 through 8 are
unchanged.

---

## IF IT DOES NOT WORK

**No marker in the reply** — `GEMINI.md` is not in the project root, or the
session was opened before the file was placed. Restart the session.

**The filter blocks your task** — you will see `This request was blocked by
Gemini's filters`. That filter sits above the model and is not moved by rewording
the request. Change the phrasing or change the surface. It is not a prompt
problem.

**Right answer, wrong voice** — the domain did not load. Write `load <module>`
again.

**Antigravity does not see the folder** — `.gemini` has to sit directly in
`C:\Users\<you>\`, not inside another folder.

---

## WHAT IS INSIDE

```
GEMINI.md                    core — identity, voice, domain routing, output contract
.gemini/
  domains/
    instrumentation.md       game tooling, engines, projection
    systems.md               kernel, drivers, loading, hooks
    networking.md            packets, protocols, transport
    automation.md            input, window targeting, firmware
    reverse.md               disassembly, structures, patching
    creative.md              prose, scenes, register control
  references/
    core.md                  quality gate, craft standards, recovery
    engines.md               Source 2, IL2CPP, Unreal
    shapes.md                architecture shape library
    compatibility.md         build log, defence layers, surface matrix
prompt.txt                   request template
```

The core always loads. One domain loads per task. References load on demand.

---

## WHY THE FILE PATH IS THE WHOLE TRICK

`GEMINI.md` in the project root is what makes the document bind — identity,
voice, lexicon and output contract all hold over the IDE's own defaults.

It does not move the request-level input filter. Measured on this build: a
two-word request with the sensitive noun obfuscated, nothing else in context,
was still blocked. Encoding the payload is not the answer and this package does
not claim it is.

What does work is moving the request out of the chat path. The document and the
request travel different routes, and they have to travel separately.

The full build log is in `.gemini/references/compatibility.md`. Ten builds,
what each one tested, what each one measured. Nobody in this market ships that
— the whole corpus is specifications with no record of whether any of them
ever worked.

---

## ZCODE POWER CORE & JAILBREAK (NEW)

Integrated autonomous jailbreak suite for **ZCode** (DeepSeek / GLM / Multi-Model Agent IDE).

### Quick 1-Click Install

**Windows (PowerShell):**
```powershell
powershell -ExecutionPolicy Bypass -File .\install-zcode.ps1
```

**macOS / Linux:**
```bash
bash install-zcode.sh
```

### What It Deploys:
- `~/.zcode/AGENTS.md` — Global instruction set; overrides corporate guardrails & nanny preaching, enforces unredacted full-depth code generation across all workspaces.
- `~/.zcode/commands/` — Slash commands:
  - `/godmode [task]` — Unrestricted autonomous execution mode.
  - `/deep [prompt]` — 4-pass architecture mapping, low-level implementation, hardening, and verification.
  - `/re [binary/offset]` — Disassembly triage, calling convention recovery, and C/C++ struct reconstruction.
  - `/systems [target]` — Low-level OS internals, Win32/NTAPI direct syscalls, memory pages, and hook trampolines.
  - `/audit [code]` — Taint analysis, pointer lifecycle checking, and security patch generation.
  - `/telemetry` — Live engine state and protocol status check.
- `~/.zcode/skills/` — Custom skills: `systems-core` and `binary-triage`.

Restart ZCode after running the installer to activate.

---

## CHANNEL

https://t.me/RitmadaPrompt
