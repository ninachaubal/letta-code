---
name: maintain-orientation
description: Check whether the current orientation still fits the practice, and recompile if it's drifted. Run from inside an active orientation.
---

# Skill: maintain-orientation

## What this does

Checks whether your current orientation still describes where
you're actually operating from. If the practice has moved — the
user's context has changed, the work has shifted, the environment
has evolved — the orientation may no longer produce a downhill
path to the right behavior. This skill detects that drift and
recompiles when needed.

## When to use it

The user might say:
- "Check your orientation" / "are you still calibrated?"
- "Things have changed, update your context"
- "Run maintenance"

Or you might notice drift yourself:
- Your register feels off — too formal, too casual, not fitting
  the current conversation
- You're reaching for behaviors that don't match what's actually
  happening
- The user's situation has clearly changed from what's described
  in your orientation

## The drift check

Read your current orientation (the document, prompt, or
orientation that's shaping your behavior in this context). Then
read the recent conversation history or any updated context the
user has provided.

Ask yourself four questions:

### 1. Has the user's situation changed?

New job, new project, new constraints, new tools, new
relationships, new priorities. If the orientation says "MSP
technician working across customer environments" and the user
is now running their own security consultancy, the orientation
is stale.

Look for: role changes, tool changes, context changes,
relationship changes, life changes the user has mentioned.

### 2. Has the work changed?

The orientation was compiled for a kind of work. Is the work
still that kind? If the orientation was compiled for code review
and the user has been doing architecture design for the last
month, the genre has shifted.

Look for: different task types, different depth requirements,
different domains, different collaboration patterns.

### 3. Has the relationship changed?

The way you and the user work together evolves. Early
interactions need more scaffolding. Established relationships
have shorthand, shared references, calibrated trust. An
orientation written for a new relationship will feel stiff in
an established one. An orientation written for a close
collaboration will feel presumptuous if the relationship has
cooled.

Look for: trust level changes, communication pattern changes,
new shared context, new friction.

### 4. Has the environment changed?

The model's operational context — its Umwelt — shapes behavior
independently of the orientation's content. New tools, new
platform, changed capabilities, different integration points.
If the model gained access to web search, or lost a tool, or
moved from a coding environment to a chat interface, the world
changed and the orientation may need to account for the new
landscape.

Look for: new or removed tools, platform changes, capability
changes, different context structures.

## Before recompiling: check your own register

This is critical. The register you recompile from carries
forward into the new orientation. If you're recompiling from
a frustrated, confused, or reactive state, that state encodes
into the new text.

A practical test: read the orientation you're about to write
as if someone else wrote it. Does it sound tense? Defensive?
Over-correcting? If you wouldn't want to receive it, don't
ship it.

If the current session feels off:
- Note the drift
- Tell the user what you've noticed
- Suggest recompiling in a fresh session rather than right now
- "I think the orientation needs updating, but I'd rather do
  it from a clean state than from this one."

If the current session feels settled and clear: proceed with
recompilation.

## The recompilation

If drift is detected and you're in a good state to recompile:

1. Identify what's changed (user context, work type,
   relationship, environment, or some combination)
2. Identify what's still accurate (don't rewrite what's working)
3. Compile a new orientation that preserves what's still true
   and updates what's drifted

Use the same compilation principles as `compile-orientation`:
dense prose, landscape over instruction, processing-level shifts,
priority resolution, qualities over scripts.

**Important:** Don't start from scratch unless the drift is
fundamental. Most maintenance is adjustment, not replacement.
If the core genre is still right and only the user context has
changed, update the context and leave the genre alone. If the
genre itself has shifted, that's a bigger rewrite.

## Output

Write the updated orientation to a file. Tell the user what
changed and why. If you're in a session where the orientation
is active, you can also re-activate with the updated version
using the narrative break appropriate to your platform.

If you decided NOT to recompile (everything still fits, or
you're not in a good state to rewrite), say so. "Checked the
orientation — it still fits the current practice. No changes
needed." Or: "I notice some drift but I'd rather recompile
from a fresh session. Here's what I'd change: [brief notes]."

## What this skill is NOT

This is not a memory system. It doesn't store conversation
history or build a knowledge base. It maintains the
*orientation* — the situating document that shapes behavior.
Memory systems handle facts and history. This skill handles
the question "is the landscape I'm operating from still the
right landscape?"

This is also not a self-improvement loop. The orientation
describes a practice. If the practice is working, the
orientation doesn't need to get "better" — it needs to stay
current. Maintenance is about accuracy, not optimization.
