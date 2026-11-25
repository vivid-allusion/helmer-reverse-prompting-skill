---
title: Picks and addresses
kind: reference
links: [elements, coverage, video-prompts, folders]
---

# Generating, picking, addresses

## The person's part

The person runs each model folder through its generator, looks at the takes, and picks one per asset. Generation and picking are theirs; this skill never presses Generate.

## A pick's address

A video model takes references by public address only. The person puts the pick into its element's folder in `02_PRE-PRODUCTION/` and syncs it; the sync gives it an address and writes a sidecar `.md` beside it holding that address. Read the address from the sidecar.

## Where it is recorded

- In the element's ABOUT, in its reference slot: `- [x] identity: <address>`.
- In each shot that uses it, in the shot file's reference table: the address and its role.

Then rebuild coverage: [[coverage]].

## Roles

Every pick attached to a video prompt is told its role in words:

| Role | For |
|---|---|
| Identity | A face, a body, a person's costume |
| Construction | An object or garment to copy exactly |
| Environment | An environment |
| Framing | A kept still, only when its composition is wanted, never its light |

## Attaching picks to the video prompts

Once the picks have addresses, they are attached to the video prompts. A short script can do the writing; these are the rules it follows.

- **In:** the video prompts, the picks' addresses from their sidecars, and the shot files, which say which elements each shot holds and which is the hero.
- **One pick per element.** Where an element has several takes, the newest wins. A pick the person made or rewrote by hand beats a generated one. When the age of a take cannot be read from its name, ask.
- **Only what the shot needs.** Read the still first: it shows what matters in the shot. Attach the hero, the cast, the shot's environment and a prop that is held or used. Drop extras that stand far back, set dressing and props nobody touches; name them in words instead: [[hero]].
- **Where the lines go.** One `![reference_images](<address>)` line per picture, below the closed `prompt` fence and above the length. The address never goes into the prompt text. The prompt's REFERENCE USAGE block names the pictures in the same order.
- **Check.** Every address must answer before the prompt is run; one that does not breaks the whole generation.
- **Write it down.** Keep a list of which picture went to which shot, and what was dropped and why, so the person can review it.

Re-running it after a new pick replaces the attached lines; it never touches the prompt text.
