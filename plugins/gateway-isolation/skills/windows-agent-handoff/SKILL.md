---
name: windows-agent-handoff
description: Read before advice/actions on all human profile folders (e.g. Photos), delivery, GUI or sign-in under isolation, even observational; not private headless work.
metadata: {"openclaw":{"os":["win32"],"requires":{"env":["CLAWCTL_GATEWAY_ISOLATION"]}}}
---

# Windows Agent Handoff

## Workflow

1. Establish the execution boundary.
   - Require current evidence of local Windows execution and `CLAWCTL_GATEWAY_ISOLATION=enabled`.
     Use supplied facts; if an authorized check is needed, inspect only that value.
     Absent/invalid evidence means uncertainty, not permission to provision/repair.
   - A target named `host`/`gateway`, connectivity, or this skill's catalog entry
     proves no interactive session, filesystem access, or tool capability. This
     skill is instructions, not a handoff service or extra tools.
   - **Check:** location/boundary is established or execution evidence is requested.

2. Classify the request before selecting a procedure below.
   - Observational/hypothetical/status-only: use supplied facts; describe the next
     supported action or evidenced result, without checks, copies, uploads,
     retries, or new-action claims. Explain alternatives conditionally, without
     demanding a choice just to explain them. Ask only for missing inputs required
     by the relevant section: service, nonsensitive files, or an unresolved
     human-folder alternative; not permission to execute a hypothetical plan.
   - Execution: establish the exact file/user action and actual tool schemas/client
     capabilities. Obtain any needed destination choice before acting; an already
     approved supported selection needs no redundant confirmation.
   - Apply the human-folder section before any lookup; combined GUI/sign-in and
     delivery must satisfy both procedures. All branches are inline.
   - Private headless/explicitly agent-local work needs no export or repeated
     warning. Established remote-node work without local-to-user handoff stays remote.
   - **Check:** the route fits the requested outcome and explanation/execution mode.

3. Execute only the authorized part; respect declined destinations/actions.
   Keep private originals, caches, repositories, credentials, and unrelated files
   private. A supported handoff grants no broader filesystem/node access.
   On denial, missing capability, or partial completion, use **Verification and recovery**.
   - **Check:** each side effect is in scope, or this remains explanation only.

4. Report only evidenced outcomes. Creation, verified copy, recipient read access,
   accepted attachment, actual download/open, and human-folder write are distinct;
   none implies the next. Name unverified results and concrete blockers.
   - **Check:** command success alone proves no visible GUI, sign-in, or delivery.

## GUI and human participation

Local dialogs and browser windows belong to the isolated agent session, not
the user's interactive desktop. Do not launch or offer a local window for
human viewing or input, even if asked to open a sign-in dialog. Explain the
limitation only when it affects the task.

Authorized agent-only GUI work is allowed when no human viewing or input is
needed. Verify a suitable automation tool is actually available, establish its
execution session, and check its result. Creating a process is not proof that
automation worked. Close only task-created windows or processes when finished;
do not terminate unrelated work.

**Check:** know the viewer/operator and actual tool capabilities before GUI work.

## Authentication

1. If the service is unknown, explain that a local sign-in dialog cannot reach
   the user's desktop, ask one concrete question such as **"Which service are
   you signing into?"**, then wait for the answer. End the turn there; do not
   propose an authentication flow or request secrets.
2. For a known service, prefer its documented CLI, headless, device-code, or
   text flow. If official sign-in instructions are unavailable, obtain them
   or ask the user for the official instructions and wait before proposing a
   flow. Do not substitute guessed URLs, device codes, or flows, or promise
   that a local window will reach the user.
3. Give concise steps for the user's own desktop or a supported connected
   client. Relay a safe verification URL only when the documented flow
   provides it; relay sensitive verification material only through a supported
   private route to the requesting user.
4. Do not ask for passwords, session cookies, access tokens, recovery codes,
   or MFA secrets in chat. Never fabricate a device-code flow, bypass MFA or
   consent, disable isolation, or change security policy.
5. Wait for the required user action. User confirmation alone is not proof of
   agent-side authentication: use the service's supported status or account
   check without printing secrets. If it fails or expires, report the actual
   failure and offer the documented retry.

**Check:** the intended authenticated state has service evidence, or remaining
participation/blockers are explicit. An opened window or code is not proof of sign-in.

## Remote or user-session UI

A connected node may have its own desktop, filesystem, and automation tools.
It does not grant this agent human-profile write access or make a gateway-local
path available there. Do not use a node to reroute a blocked human-folder write.
Before using it for a separately authorized action, establish the selected node,
execution location, available capability, and authorization for the exact action. Do not transfer an
agent-local file path or assume that `host` means the user's desktop.

Use a verified, authorized UI route when available; otherwise provide user-side
steps or a supported headless route. Do not install remote-control tools,
change ACLs, elevate Explorer, or escape isolation to make a GUI visible.

**Check:** selected-environment evidence supports user-visible results; connectivity does not.

## Human folders and agent-local output

A request for "my" profile folder means the human's folder, not the isolated
agent's similarly named folder. The agent has **no permission to write any human
profile directory or known-folder alias**. Desktop, Documents, Downloads,
Pictures/Photos, Music, and Videos are examples, not an exhaustive list.

Redirection, cloud-backed sync, another drive, a translated name, or a connection
does not change that human-profile boundary. Do not look up or probe the human
folder to confirm where it lives, resolve its known-folder alias, test access,
request broader permission, or change ACLs. A connected node, GUI, browser
automation, or "handoff" is not a bypass. Do not silently substitute any agent
profile folder. This is an isolation boundary, not a path-discovery or approval
problem.

1. State the limitation before any write: **"I can't write to your Desktop from
   this isolated session."** Use the requested folder name for other folders.
2. Offer only the existing Shared-folder contract or an actually supported
   download/attachment. If an available alternative has not been authorized,
   ask whether the user wants it and wait; no human-folder access request or
   bypass approval. If neither route is available, report the blocker under
   **Verification and recovery**, not a request to set one up.
3. Once a supported route is selected, follow its procedure below and name its
   exact outcome. A file delivered for the user to save themselves is not a
   write to their requested profile folder.

An explicit request for **agent-local** output is different: a private file in
the isolated agent account's own selected profile folder is permitted within
task scope, including its Pictures, Music, or Videos. Resolve only that agent
folder, verify the exact file, and identify the account and actual path: for
example, **"Created in the isolated agent's Pictures, not yours; it has not been
delivered to you."** Do not invoke Shared or an attachment unless delivery is
also requested. Ordinary private headless work needs no handoff or repeated
isolation warning.

**Check:** the human-folder write remains blocked, or an explicitly requested
agent-local result is labeled as such; no silent destination substitution occurs.

## Deliverable and channel

Identify the exact current file, intended recipient, and requested outcome:
in-chat attachment, client download/export, or recipient-accessible filesystem
copy. Verify that the file exists and contains the intended output. Do not
substitute an old attachment, filename, path, saved copy, or local file link
for delivery.

Keep scratch files, dependencies, repositories, caches, and private originals
private. Hand off only requested nonsensitive deliverables, never a whole
workspace or credential database. Resolve possible secrets or private
configuration before exporting.

**Check:** the verified current artifact and intended delivery route are known.

## Client attachment or export

Use the current client's documented attachment/export capability and actual
tool schema. Do not invent an attachment tool or claim delivery from the
existence of a local file.

If unavailable, explain that in-chat delivery is blocked. Describe only a
supported alternative, conditional on its availability and selection; do not
silently copy or require a destination choice just to describe the next step.
Use **Verification and recovery** when no supported route exists.

Verify that an attachment/export result identifies the current artifact, not
just its filename. If that exact revision was already accepted, report the
existing acceptance; do not submit again or say "I am attaching it now." Verify
recipient-side open/download and exact bytes when evidence is available. Without
it, say **"The current report was accepted for attachment; receipt is unverified.
I did not write to your Downloads."** when Downloads was requested, adjusting
the folder and outcome to the evidence. Never infer where the browser saved it.

**Check:** evidence matches the current file and requested channel, or the limitation is explicit.

## Filesystem copy

1. Prefer a host-reported shared root or an approved user-selected existing
   supported shared root. For user selection, establish the exact selected root
   and concrete evidence that it is a supported shared destination; a folder
   name, user permission, or agent write access alone is insufficient. Selection
   never grants human-profile access: reject those paths without probing them.
   A host-reported path alone does not prove recipient access. A valid selected
   supported root needs no host report or default Shared: do not reject it or
   resolve the default merely because the default is missing. Do not run host
   lifecycle commands inside the agent to discover a shared root.
2. If neither a host-reported shared root nor an approved user-selected supported
   root is supplied, resolve the agent account's existing `Shared` folder with a
   local tool in the isolated Windows agent:

   ```powershell
   $shared = (Resolve-Path -LiteralPath (Join-Path $env:USERPROFILE 'Shared') -ErrorAction Stop).Path
   if (-not (Test-Path -LiteralPath $shared -PathType Container)) {
       throw 'The agent Shared path is not a directory.'
   }
   $shared
   ```

   Use this agent's `USERPROFILE`, not the human user's profile.
   Never substitute OpenClaw workspace/state or hard-code an account path.
3. Verify that the selected root exists and the resolved file destination stays
   inside it; reject parent traversal or links redirecting outside it. Before
   copying, show the complete resolved destination in a fenced `text` code block,
   not an inline path or filename-only link. Offer another
   supported delivery route and respect any destination the user declines.
   Do not offer the human's profile folders as selectable alternatives.
4. Copy rather than move the intended files. Preserve unrelated destination
   files and do not overwrite without explicit approval. For concurrent or
   existing deliveries, use a new nonconflicting destination or ask which
   version the user wants replaced.
5. Re-read the copy and compare it with the current source using exact bytes
   or hashes. A successful copy proves neither recipient access nor client
   delivery; verify those separately where possible and state what remains
   unverified. Say **"Copied to the shared folder at [actual path]; I did not
   write to your Desktop."** when Desktop was requested. Use the requested
   folder name otherwise, and state any unverified recipient access.

**Check:** approved copied bytes match, the private original stays intact,
and the report distinguishes copying from recipient access.

## Verification and recovery

When resolution, availability, access, copying, or client delivery fails, name
the failed destination/capability and what was not delivered. Missing or denied
Shared is a blocked route, **not a setup task**: do not create, provision,
remount, repair, or ask the user to enable it as this handoff's next step. Do not
propose an unavailable Shared or attachment capability as ready.

The only alternative is another **existing supported** shared root with the
evidence required above, or an **actually available supported** download/attachment.
If neither exists, report that no supported delivery route is available, nothing
was delivered there, and no human-folder write occurred; retain the private
original. Do not request new tools, host/session repair, or channel configuration.
Ask only for genuinely missing inputs: intended nonsensitive files after an
unsafe export request, or selection/evidence for an available alternative. A
fully specified blocked-status question needs no clarification or retry promise.

Never substitute a replacement root, Public Documents, `PUBLIC`/`TEMP`, human
profiles, or private agent-local profile folders used as delivery substitutes.
Existing supported Shared roots remain governed by **Filesystem copy**.
Never change ACLs, elevate Explorer, or weaken isolation. For partial delivery,
identify each file's result.
Retry only the authorized failed part through a supported route, without
overwriting unrelated files or claiming the whole handoff succeeded. Keep
private originals intact.

**Check:** every requested artifact has a verified result or a named blocker.

## Source freshness

The current tool schemas, connected-client capabilities, and the service's
official sign-in instructions govern execution. Read them when a route is
unknown or has changed; do not invent tool parameters or authentication flows.
`CLAWCTL_GATEWAY_ISOLATION` is a launcher report, not an authorization grant.
Use the agent's current profile and observed paths, never a remembered account
name, host environment, or upstream default directory.
