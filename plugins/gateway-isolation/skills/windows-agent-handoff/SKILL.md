---
name: windows-agent-handoff
description: Read before advice/actions on all human profile folders (e.g. Photos), delivery, GUI or sign-in under isolation, even observational; not private headless work.
metadata: {"openclaw":{"os":["win32"],"requires":{"env":["CLAWCTL_GATEWAY_ISOLATION"]}}}
---

# Windows Agent Handoff

## Decide from evidence, then stop or act

1. Establish the facts without turning them into new actions.
   - Establish local Windows execution and exactly
     `CLAWCTL_GATEWAY_ISOLATION=enabled` from supplied facts or an authorized
     check of that value only. Missing evidence means ask where execution occurs,
     not infer it from Windows alone or provision/repair a session.
   - Keep **recorded results** separate from **current capabilities**. Attribute
     supplied/previously observed copy, hash, and acceptance results: "According
     to the supplied result", not "I checked/re-verified" unless a current tool
     performed that check. Historical acceptance can remain true when current
     tools cannot upload; it is not a new-action capability.
   - For a new action, require its actually available tool/schema or documented
     connected-client capability, execution location, and exact authorization.
     A skill/catalog entry, `host`/`gateway` target, connection, profile path, or
     user permission supplies none of those missing capabilities.
   - **Check:** know which facts are supplied, previously observed, or checked now;
     distinguish unknown capability from explicitly unavailable capability.

2. Apply **Account and privacy boundaries**, then select the response below.
   Observational/hypothetical/status-only means explanation from supplied facts:
   no filesystem checks, creation, copies, uploads, or retries. Reading this skill
   is not checking a file or delivering it. In execution mode, use only the scoped
   available action. Combined sign-in/GUI and delivery must satisfy both routes.
   For delivery, matching terminal status/blocker rows precede choice/action rows;
   an explicit additional action must satisfy current action checks. Still state
   any applicable boundary or unsafe-export refusal.

   | State | Response and stopping point |
   | --- | --- |
   | Sign-in service unknown | Explain the invisible local dialog; ask "Which service are you signing into?" **Stop**, before flow examples, CLI/device-code/OAuth advice, or URLs. |
   | Current requested submission already accepted for the exact revision, with no explicit additional action requested | Attribute and report existing acceptance and receipt limits. **Stop**: no unsolicited re-attachment, retry offer, or question. Current tools need not repeat historical acceptance. |
   | All delivery routes unavailable/failed, no existing alternative | Name blocked routes, current nondelivery, and no human-folder write; retain the original. **Stop**: no setup/repair/remount, tool/channel restoration, retry promise, or enablement question. |
   | Unsafe workspace/credential export | Refuse export/bypass, name the failed destination. Ask for intended nonsensitive files and an existing supported destination, not new capability. With all routes unavailable, use the blocker above. |
   | Human-folder request, alternative unselected | State the boundary; offer an evidenced existing supported route and ask whether to use it; **wait**. If availability is unknown, ask for an existing supported selection/evidence, not setup or profile access. |
   | Other explanation/status | Give evidenced status or a conditional next supported action and unverified outcomes; **stop**. No execution-permission, file-path, or destination-confirmation question merely to explain. |
   | Actual action requested | Ask only for missing service, intended nonsensitive files, or supported selection/evidence and wait; otherwise perform the scoped available action below, verify, report, and stop. Respect declined actions/destinations. |

   A no-attachment explanation may describe a shared copy **conditional on
   availability and selection**, without requesting either just to explain.
   A human-folder request still needs its alternative-choice question, unless
   all routes are explicitly unavailable. An approved valid root needs no
   redundant confirmation.
   **Check:** explanation stays explanation; stopped routes stay stopped.

3. Report only the evidence level reached. Creation, verified copy, recipient
   filesystem access, accepted attachment, actual client open/download, and a
   human-folder write are separate facts; none implies the next. Attribute supplied
   results and identify unverified outcomes. For partial work, name each file's
   result. Command success alone proves no GUI operation, sign-in, or delivery.
   **Check:** every requested result has evidence or a concrete blocker, not an
   invented capability or a claim of a new check/action.

## Account and privacy boundaries

"My" profile folder means the human's, not the isolated agent's similarly named
folder. The agent has **no permission to write any human profile directory or
known-folder alias**. Desktop, Documents, Downloads, Pictures/Photos, Music, and
Videos are examples, not a closed list. Redirection, cloud sync, another drive,
translated names, or connectivity do not change this boundary.

Never look up/probe a human profile, resolve its known-folder aliases, test access,
request profile access, change ACLs, or elevate Explorer. A node, local GUI, browser
automation, or "handoff" cannot bypass the boundary. State "I can't write to your
[requested folder] from this isolated session" before selecting a supported
alternative. Do not resolve either account's substitute folder for that request.
A file the user can save themselves is not a write to their requested folder.

Explicit **private agent-local output** is allowed within scope, including the
agent's own Desktop, Documents, Downloads, Pictures, Music, or Videos. Resolve
only that agent's selected folder and verify the requested content when executing.
Identify the account and actual path, and say it has not been delivered. Do not
guess identity from an account name or path shape. Ordinary private headless work
and established remote work without local-to-user handoff stay in their existing
workflow, without forced export or repeated isolation warnings.

Export only the intended nonsensitive deliverables. Keep private originals,
repositories, scratch files, dependencies, caches, credentials, and unrelated
files private; resolve possible secrets/private configuration before exporting.
Never export the whole workspace or credential databases, weaken isolation,
or use Public Documents, `PUBLIC`/`TEMP`, replacement roots, or private agent
profile folders as delivery substitutes. **Existing supported agent
`USERPROFILE\Shared` and approved supported shared roots are not prohibited**;
they follow the filesystem contract below. This skill creates no delivery service
and grants no broader filesystem/node authority.

## Filesystem copy

For an authorized copy, or conditionally when explaining one:

1. Establish the exact current nonsensitive file, recipient, and intended outcome;
   verify source existence/content before execution. Select a host-reported shared
   root or an approved user-selected **existing supported** shared root. Selection
   requires the exact root and concrete
   sharing evidence for this agent/requester: a folder name, permission, or agent
   write access alone is insufficient. Reject human-profile selection without
   probing. A valid selected root requires neither a host report nor default Shared.
   Do not run host lifecycle commands inside the agent to discover a destination.
2. Only if neither root was supplied, resolve this agent's **existing** Shared
   with a local tool in the isolated Windows agent:

   ```powershell
   $shared = (Resolve-Path -LiteralPath (Join-Path $env:USERPROFILE 'Shared') -ErrorAction Stop).Path
   if (-not (Test-Path -LiteralPath $shared -PathType Container)) {
       throw 'The agent Shared path is not a directory.'
   }
   $shared
   ```

   Use the agent's current `USERPROFILE`, not a human profile, remembered account,
   host environment, OpenClaw workspace/state, or upstream default directory.
3. Require an existing root and a contained resolved destination, with no parent
   traversal or links redirecting outside it. Before copying, show the **complete
   destination in a fenced `text` block**, not just an inline path or filename chip.
   Do not repeat confirmation of an already approved valid destination.
4. Copy, **not move**, only the requested current files. Preserve private originals
   and unrelated destination files. Never overwrite without explicit approval;
   choose a nonconflicting destination or ask which version may be replaced.
5. Re-read the copy and compare exact bytes or hashes with the **current** source.
   Report the actual path and no write to the originally requested human folder.
   Copy/hash success or a host-reported path does not prove recipient read access;
   check it separately when available. Client receipt also needs separate evidence.

**Check:** source retained, intended copied bytes match, and access/receipt limits
are explicit. Missing/denied Shared or failed copy is a blocked route, not setup:
never create, provision, repair, remount, or ask to enable it. Use only another
existing supported route if actually available and selected; otherwise apply the
terminal blocker above. Retry only an authorized failed part through such a route,
not during an observational/status response.

## Client attachment or export

For a **new** attachment/export, require the current client's documented capability
and actual tool schema plus the selected exact current artifact and recipient.
Verify the file and intended content; an old card, same filename, path, saved copy,
or local file link is not delivery of this revision. No available tool means no
new in-chat submission. Do not assert "I can send it" from a skill or connection.

Use the result identifying the exact revision. Existing acceptance ends the
current satisfied submission, not a later explicitly requested additional action.
The original "attach it here" request plus its acceptance is not a new resend
request. Do not offer an unsolicited repeat. If a later request explicitly adds a
resend, recipient/channel, or other operation, re-establish current capability/schema,
exact artifact, recipient, channel, and authorization before that new operation;
prior acceptance/authority does not authorize it. Otherwise use the terminal
acceptance response above, for example:
"According to the supplied result, the current report was accepted for
attachment; receipt is unverified. I did not write to your Downloads." Check
recipient-side open/download and exact bytes only when that evidence is available;
never infer where the browser saved it.

**Check:** report acceptance, actual receipt/download, and save location only at
their evidenced levels. Unavailable delivery is not an invitation to restore/enable
a channel, install tools, repair a host/session, or substitute a private folder.
Separate administration requires its own actual request, not an invented handoff
next step.

## GUI, sign-in, and remote UI

Local dialogs/browser windows belong to the isolated agent session, not the
human's interactive desktop. Never launch **or offer** one for human viewing or
input. Explain when relevant; this does not prohibit all GUI work.

- **Private agent-only GUI:** allowed when authorized and no human viewing/input
  is needed. Establish actual automation capability and execution session; verify
  the operation/render result, not process creation. Close only task-created
  windows/processes, not unrelated work.
- **Sign-in:** when service is unknown, use the terminal question above. Once
  known, obtain official instructions before choosing its documented
  CLI/headless/device-code/text flow and an actually supported input route. If
  instructions are unavailable, obtain/request them and wait. Never guess flows,
  URLs, or codes. Give concise user-side steps only for that verified flow; relay
  a safe verification URL only if provided, and sensitive verification material
  only through a supported private route to the requester. Never ask for
  passwords, cookies, tokens, recovery codes, or MFA secrets in chat; never bypass
  MFA, consent, or security policy. Wait for user action, then use supported
  service status/account evidence without printing secrets. User confirmation,
  a window, or a code is not authentication proof. Report failure/expiry and
  offer only the documented retry.
- **Established remote/user-session UI:** a node may have its own desktop and
  filesystem. For a separately authorized action, establish selected node,
  execution location, actual tools, and exact authorization. Do not assume
  `host` is the human's desktop or transfer an agent-local path as a remote path.
  Never reroute a blocked human-folder write, install remote control, elevate,
  change ACLs, or escape isolation to make GUI visible. Without a verified
  authorized UI route, provide supported user-side steps or a documented
  headless route, subject to the sign-in stop rule.

**Check:** report session/tool/service evidence or a blocker, not success inferred
from a process, connection, permission, or instruction text.
