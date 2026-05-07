---
name: New plugin proposal
about: Propose a new plugin for the marketplace
labels: new-plugin
---

<!--
  New plugins go through a one-week comment period before a PR is opened.
  This gives the community time to raise concerns about scope, naming,
  or overlap with existing plugins.
-->

## Plugin name

<!-- Lowercase, hyphenated. Check existing plugins for conflicts. -->

## Category

<!-- 
  Existing categories: Instruction Health, Context Preservation, Utility,
  Resource Governance, Regression Testing, Foundational, Intent Capture,
  Confidence Calibration, Session Continuity, Pre-Flight Gate, LLM Judges,
  Security, Synthesis, Agent Learning
  
  Or propose a new category and explain why.
-->

## What problem does this plugin solve

<!-- Be specific. What agent behavior does it improve or what failure mode does it address? -->

## How it works

<!-- High-level description: which hooks does it use, what does it do in each hook, what does it output? -->

**Hooks:**

**Agents (if any):**

**Commands (if any):**

**Events written to Onlooker (if any):**

## Why it doesn't overlap with existing plugins

<!-- 
  Review all existing plugins before proposing. If there's overlap, 
  explain why a new plugin is preferable to extending an existing one. 
-->

## Dependencies on other plugins

<!-- Does this plugin require or benefit from other plugins being installed? -->

## Runtime support

- [ ] Claude Code
- [ ] Other (specify):

## Are you planning to build this?

- [ ] Yes, I plan to submit a PR after the comment period
- [ ] No, I'm proposing it for the community to build
