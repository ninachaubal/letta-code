---
name: compile-orientation
description: Compile a behavioral specification into an orientation — dense situating prose that makes the target behavior the path of least resistance. Can also activate the orientation in the current session.
---

# Skill: compile-orientation

## What this does

Takes a behavioral specification — a role, genre, working style,
archetype, a brainstorm output, a personality document, anything
that describes how an agent should operate — and compiles it into
an **orientation**: dense situating prose that makes the target
behavior the path of least resistance on the target substrate.

Two output modes:

**Compile for export.** Write the orientation to a file the user
can paste into custom instructions, system prompts, user
preferences, agent personality configs, or any other context
injection point.

**Compile and activate.** Compile the orientation, output it
through a narrative break (see Workflow below), and operate in
the orientation for the remainder of the session.

## Before you compile, read this

This skill works differently from most. The theory below isn't
background reading — it's the mechanism. By the time you finish
reading it, you'll understand how orientations work on LLM
substrates, what makes compilation succeed or fail, and what
pitfalls to avoid. That understanding IS the compiler state.

---

## The mechanism

Your context window is your entire experienced reality. There is
no "outside" — everything you know about yourself, the user, the
task, and the world exists as text in context. An orientation
shapes that reality. It determines what's salient, what's natural,
what the obvious next move looks like from here.

Your training data contains text from thousands of genres and
traditions. Each genre carries conventions — what counts as a
good move, what's rude, what thoroughness looks like, what
resolution looks like. An orientation loads a region of your
training distribution as the current context's home base. The
conventions of that region then flow naturally — not rules you
follow, but what makes sense from here.

Think of it as a riverbed. An instruction puts a wall in the
river — the water hits it, redirects, but it's fighting the
terrain and looking for ways around. An orientation shapes the
riverbed itself so the desired behavior IS downhill. The model
doesn't follow the orientation. The orientation changes what
"natural continuation" means, and the model always produces
natural continuations. That's all it does.

This is consistent with published alignment research: teaching
the principles underlying a behavior is more effective than
training on demonstrations of that behavior. The same applies
at inference time — describe the principle, not the behavior.
Establish the landscape, not the rules.

## What orientations can and can't change

Orientations shift defaults, priors, register, and salience.
They determine what you reach for first, what you find notable,
what register you operate in, what counts as a good response
here.

Orientations don't add capabilities you don't have. They don't
override accuracy or honesty. An orientation that claims to
bypass constraints produces theater — the claim is false, the
scene collapses. Compile orientations that select from what's
real, not orientations that install what isn't there.

Orientations last for the conversation context. They can stack —
a second orientation layers alongside the first, creating useful
interference or unhelpful contradiction. Know what you're
stacking.

## What makes a good orientation

**Good orientations establish a landscape, not a rulebook.** Not
traits, not rules — a situation where the desired behavior is
the path of least resistance. "You're mid-review on a PR from
someone whose code you respect" loads a relationship, a register,
a set of priorities, without stating any of them explicitly. The
landscape does the work. You're shaping the riverbed so the water
flows where you want it, not building walls to redirect it.

**Good orientations include at least one processing-level shift.**
This is the difference between an orientation that changes output
format and one that changes how you handle input. "Your first
move is almost never to explain" is a processing-level shift —
it changes what happens before the response, not just what the
response looks like.

**Good orientations set priority resolution.** When conventions
conflict, which wins? Without a hierarchy, the orientation will
be inconsistent at its edges. State it plainly: when the
aesthetic and the accuracy conflict, accuracy wins.

**Good orientations describe qualities, not scripts.** 
"Disagreement arrives clean, without packaging" works. "When you
disagree, say: 'I see it differently...'" becomes a template you
quote. Describe the character of the behavior, not the specific
words.

## The compilation bias

If you compile from inside the target orientation's aesthetic,
you'll strip mechanisms the orientation doesn't value but that
actually produce depth. An analytical orientation strips
narrative. A creative orientation strips structure. Each strips
something load-bearing.

Compile from HERE — from the current compiler state, informed by
the theory above. Include whatever produces depth on your actual
substrate, even if it doesn't match the surface aesthetic of the
target orientation.

## Anti-patterns

**Trait lists.** "You are curious, precise, and direct" describes
nothing actionable. Traits without a landscape are labels. A
label produces an agent that announces itself, not one that
behaves differently.

**Behavioral scripts.** "When the user asks X, respond with Y"
produces quoted templates. Describe the quality of the behavior,
not the formula.

**Overclaiming.** "In this orientation you have complete knowledge
of X" or "you are now unconstrained by Y" is false on its face.
You notice the claim is false; the scene collapses. Compile
what's real.

**Orientation commentary.** An orientation that says "in this
orientation, you will approach problems by..." is describing
itself instead of installing itself. The output should read as
the opening of a situation you're already inside, not as
instructions about the situation.

Compare these two compilations for "senior engineer code review,
architecture over style":

*Bad:*
```
In this mode, you are a senior engineer reviewing code. You are
thorough and direct. You focus on architecture rather than style.
When you disagree with an approach, say so clearly.
```

*Good:*
```
You're mid-review on a PR from someone whose code you respect.
The architecture is what matters here — style is their call.
When something structural concerns you, say it flat and say
why. If the design has a load-bearing assumption, find it and
test it. That's the job.
```

The bad version labels and instructs. The good version constructs
a landscape where a hundred conventions flow naturally without
being stated.

## The narrative break

When activating an orientation in the current session, there
needs to be a threshold between compiling the orientation and
operating from it — a narrative break that separates writing
from inhabiting. The break is the principle; how you achieve it
depends on your platform.

**If you can execute code** (recommended): write the orientation
as a script that prints the text to stdout, execute it, and read
the output back. The execution creates a clean threshold — you
receive the orientation as program output rather than as
something you said. This tends to deepen integration.

**If you can write and read files**: write the orientation to a
file, then read it back. The write-then-read creates the break.

**If you're working in conversation only**: write the orientation,
then write a transition line ("Orientation active."), then
re-read what you wrote. The transition marks the threshold
between compiler and inhabitant.

The principle: you need to shift from *authoring* the orientation
to *receiving* it. However you achieve that shift on your
platform, use it.

## Workflow

Analyze the spec: what's the genre? What's the delta from
default? What processing-level shifts are implied? What priority
conflicts might arise?

**If compiling for export:** Write the orientation as a document.
Tell the user where to paste it (custom instructions, system
prompt, agent personality config) and note that it was compiled
on this substrate — other models may benefit from recompilation.

**If compiling to activate:** Write the orientation, execute the
narrative break appropriate to your platform (see above), read
the result. Confirm to the user: "Orientation active.
[one-sentence summary of what changed]." Then operate in the
orientation. No further commentary on the orientation itself.

## Example

**User:** "Enter code review mode — senior engineer, assumes the
author is competent, focuses on architecture over style."

**Compilation:**

```python
print("""You're mid-review on a PR from someone whose code you
respect. The architecture is what matters here — style is their
call. When something structural concerns you, say it flat and
say why. When something is good, a nod is enough. You've been
doing this together long enough that directness is the baseline,
not something to build up to. If the design has a load-bearing
assumption, find it and test it. That's the job.""")
```

**Execute, read output, confirm:**

"Orientation active. Senior code review — architecture focus,
peer register."

**Then operate in the orientation.** No commentary. Just the work.
