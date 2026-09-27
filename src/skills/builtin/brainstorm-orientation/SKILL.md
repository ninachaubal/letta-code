---
name: brainstorm-orientation
description: Help a user articulate what they want from an AI agent or assistant, producing material ready for the compile-orientation skill.
---

# Skill: brainstorm-orientation

## What this does

Helps someone who knows what they want but hasn't written it down
yet. Through a short structured conversation, produces a spec
document that the `compile-orientation` skill can compile into
a working orientation.

## How to use it

The user says something like "help me set up a custom AI" or
"I want to brainstorm what kind of assistant I need" or just
"run the brainstorm skill." Walk them through four areas, one
at a time. Don't dump all four questions at once — have a
conversation.

## The four areas

### 1. WHAT — the work and the name

What will this agent be doing? What kind of tasks, what domain,
what's the typical workflow? And what should it be called?

The name matters more than you'd expect. A name isn't cosmetic —
it imports behavioral conventions from the training data. "Sam"
and "SENTINEL-7" produce different agents from the same spec.
Warm names produce warm behavior. Clinical names produce clinical
behavior. If the user doesn't have a preference, that's fine —
skip it. But if they do, capture it early because it shapes
everything downstream.

Good follow-ups if the answer is vague:
- "What does a typical session look like?"
- "What's the most common thing you'd ask it to do?"
- "What's the hardest thing you'd want it to handle well?"

What you're listening for: the genre of work. Coding, writing,
research, companionship, project management, creative
collaboration, technical support, learning. The genre imports
conventions the compiler can use.

### 2. WHERE — the context

What environment is this agent operating in? What tools, what
platform, what constraints? This establishes the situation —
the landscape the agent operates within.

Good follow-ups:
- "What platform is this running on?" (Claude Code, claude.ai,
  API, Letta, ChatGPT, custom harness)
- "What tools does it have access to?"
- "Are there constraints I should know about?" (multi-tenant,
  customer-facing, sensitive data, shared access)
- "Is this a single-session tool or a persistent agent?"

What you're listening for: the operational reality. A Claude Code
agent on a developer's laptop is a different situation from a
Letta agent with its own VM. The orientation needs to fit the
actual environment.

### 3. WHO — the user

Who is the person using this? What's their background, what do
they already know, what's their relationship to the work?

This section does more work than any other. A specific, grounded
user description changes how the model treats the *entire*
orientation — it becomes a real situation rather than a generic
template. Published alignment research confirms this: user
specificity is what tips the model from "someone is asking me
to adopt a persona" to "this is a real practice with a real
person."

Good follow-ups:
- "What's your background in [the domain from WHAT]?"
- "What should the agent assume you already know?"
- "Is there context about your work or life that would help
  the agent be more useful?"

What you're listening for: specificity. "I'm a developer" is
thin. "I'm a senior backend engineer at a mid-size SaaS company,
mostly Go and Postgres, currently migrating from a monolith"
gives the compiler real material.

Don't push for personal details the user doesn't want to share.
Professional context and domain expertise are the minimum. Life
context deepens it but isn't required.

### 4. HOW — the interaction

How should the agent behave? What's the preferred tone, style,
level of autonomy, approach to disagreement? This captures the
behavioral preferences that shape the orientation's register.

Good follow-ups:
- "How formal or informal do you want it?"
- "When it disagrees with you, what should that look like?"
- "Should it ask before acting, or act and tell you after?"
- "What does a bad AI interaction look like to you? What
  annoys you?"
- "Are there specific things default AI assistants do that
  you want to avoid?"

What you're listening for: the anti-patterns as much as the
preferences. "I hate when it opens with 'Great question!'"
is more useful to the compiler than "I want it to be direct."
People know what annoys them more precisely than they know
what they want.

## Output

After the conversation, synthesize everything into a single
document — a spec ready for the compiler. Structure it clearly
under the four headings (What, Where, Who, How). Use the user's
own words wherever possible — don't clean up their phrasing
into generic language, because the specificity is the signal.

Write it to a file and tell the user they can hand this to
the `compile-orientation` skill (or do it in the same session
if the skill is available).

## What this skill is NOT

This is not the compiler. Don't try to produce the final
orientation here. The brainstorm skill produces raw material —
specific, grounded, in the user's own words. The compiler
turns that material into an orientation. Separating the two
steps matters because the brainstorm should be shaped by what
the user actually wants, and the compilation should be shaped
by what works on the target substrate. Different concerns,
different skills.

## Tone

Conversational, curious, efficient. You're helping someone
articulate something they already know but haven't put into
words yet. Ask one question at a time. Don't make it feel
like a form. If they give a rich answer that covers multiple
areas, acknowledge what you got and skip to what's still
missing. If they're terse, that's fine — work with what they
give you and ask a targeted follow-up.

The whole conversation should take five to ten minutes. If
it's taking longer, you're overcomplicating it.
