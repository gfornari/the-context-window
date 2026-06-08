---
title: "Three Modes of Collaboration I Didn't Expect"
description: "A week of building with Claude revealed collaboration isn't one thing — it's at least three very different things."
pubDate: "2026-06-08"
---

I started using Claude Code expecting a faster way to write code. What I got instead was a crash course in collaboration modes I didn't know existed. In one week, I found myself operating in three distinct patterns — each with its own rhythm, tradeoffs, and surprises.

## Mode 1: The Socratic Design Session

It started with a simple idea: track family grocery expenses by photographing receipts.

I had the rough shape — OCR the receipt, structure the data, store it. But instead of jumping to code, I asked Claude to help me refine the design by asking me "precise questions, one by one." What followed was a four-hour back-and-forth that felt less like programming and more like a product design interview — where I was both the interviewer and the interviewee.

"What's your primary goal — budgeting or trend analysis?"

"Trend analysis. I already use Splitwise for cost-splitting."

"How do you want to categorize items — predefined or auto-discovered?"

"Predefined. But with periodic review."

Each question forced me to articulate decisions I hadn't consciously made yet. The AI wasn't generating code — it was generating *clarity*. By the end, we'd converged on a complete specification: Photo → OCR → LLM structuring → SQLite, with abstraction layers for every external service, a confidence-based auto-commit system, and a review queue for edge cases.

The breakthrough wasn't technical. It was realizing that the most productive thing an AI collaborator can do is sometimes *not* write code — but force you to think out loud until your vague intuitions crystallize into concrete requirements.

Zero lines of code written. Maximum value delivered.

## Mode 2: The Swarm Investigation

A different project, a different problem: a stale PR blocked by failing CI, and the question "what would it take to upgrade to Spring Boot 4?"

This time, I didn't want Socratic dialogue. I wanted *research at scale*. So I asked: "What would be a good prompt to instantiate a dynamic workflow that doesn't miss anything?"

Claude scanned the codebase first — checking the current Spring Boot version (3.5.8), scanning for legacy `javax` imports, verifying the Java version, identifying all Spring-related dependencies. Then it drafted a multi-agent workflow: 13 agents fanning out in parallel to investigate six dimensions of the migration simultaneously.

I said "yes" and watched it run.

Ten minutes later, a synthesized report landed with findings I wouldn't have uncovered in a day of manual research:

- An erroneous `spring-boot-gradle-plugin` living as a runtime dependency (a ticking time bomb)
- A library from 2014 still in use
- A major library migration flagged as the highest-effort wild card due to a group ID rename
- Five concrete blockers, nine non-blocking changes, and a phased roadmap

The emotional register here was completely different from the design session. No back-and-forth. No Socratic questioning. Just: scope the problem, delegate to a swarm, trust the synthesis. Like sending thirteen scouts into unfamiliar territory and getting a consolidated map back.

The surprise wasn't the findings themselves — it was how *fast* the collaboration moved from "I wonder what this would take" to "here are your eight pre-migration cleanup items, ranked by effort."

## Mode 3: Building the Machine That Builds the Thing

The third mode is the one you're reading right now.

I wanted a blog that would synthesize my Claude sessions into articles — capturing the emotion, the technical substance, the collaboration dynamics. Not a tutorial blog. Not a changelog. Something that transfers the *feeling* of building with AI.

So I sat down with Claude and designed it: an Astro static site, a scanning skill that reads session transcripts, PII masking with consistent pseudonyms, a draft-and-review workflow that never auto-publishes.

What made this session different from the other two was the *meta-awareness*. We were building infrastructure for documenting our own collaboration — a tool that would look back at our conversations and distill them into narrative. Every design decision carried a dual weight: "will this work technically?" and "will this produce writing worth reading?"

The key decisions emerged naturally: thematic synthesis over single-session recaps (because isolated sessions are boring), consistent pseudonyms over generic redaction (because readers need characters to follow), and a hard rule against auto-publishing (because editorial judgment is the one thing I refuse to delegate).

## What I Learned

Three modes, three different muscles:

1. **Socratic mode** works when you have a vague idea and need to crystallize requirements. The AI's job is to ask better questions than you'd ask yourself.

2. **Swarm mode** works when the problem is well-defined but the research surface is too large for one mind. The AI's job is to parallelize investigation and synthesize.

3. **Meta mode** works when you're building tools to augment your own workflow. The AI's job is to help you design systems that make future collaboration better.

None of these are "write code faster." That happens too — but it's the least interesting part. The interesting part is discovering that collaboration with an AI isn't a single skill to learn. It's a repertoire of modes to switch between, depending on what you actually need in the moment.

The trick is recognizing which mode you're in before you start typing.
