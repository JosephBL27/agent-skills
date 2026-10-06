# Probe: platform, hooks, runtime

**Question:** should the harness itself do part of this, and what should it run on?

Some requirements are not code. "Every time X happens, do Y" is not a thing to
remember — it is a hook, executed by the harness rather than by a model that may
or may not recall the rule. Recognising that early is the difference between a
reliable behaviour and a prompt that mostly works.

## Harness features

Automation phrased as *"from now on"*, *"whenever"*, *"each time"*, or
*"before/after X"* is a hook in `settings.json`, not an instruction. The
`update-config` skill owns that configuration; route there rather than
hand-editing settings.

Also in scope: permissions and allowlists, environment variables, subagent
definitions, scheduled jobs.

## Hooks are not free, and on this machine they are deliberately absent

Joseph runs **zero hooks**, on purpose. gstack's `SessionStart` auto-update hook,
its plan-tune hooks, and impeccable's design hook were all considered and
skipped — a hook fires on *every* session including scheduled and unattended
runs, which is exactly when a slow or network-touching hook does the most damage.

So do not propose a hook casually. It has to earn the cost: state what fires it,
how long it takes, and what happens when it fails during an unattended job. A
hook that runs on every prompt to save an occasional mistake is a bad trade.

## Runtime and language

Usually settled by the project and not worth a probe. It becomes a real question
for something new, something with a hard performance floor, or something that has
to run unattended.

When it *is* a question, the deciding factors are rarely aesthetic: what the
deployment target actually supports, what the rest of the codebase already uses
(a second language is a permanent tax), what the libraries you need exist for,
and what can be tested without a device or a network.

## Reporting

Most of the time the honest answer here is "nothing — existing project settings
cover it", and that is a fine result to report in one line. When something *is*
needed, name the specific setting or hook, what triggers it, and its failure
behaviour during an unattended run. Anything touching permissions or secrets goes
to Joseph rather than into the pathway as a decided item.
