---
title: Environments
kind: reference
links: [scenes, hero, models, prompt-files, reading-a-still]
---

# Environments

An environment is the place with nobody in it, in the project's look, from where the scene's camera stands. It is the environment reference the video model rebuilds the scene in.

## How many

- **One environment per scene per camera side.** A scene shot from two sides (the window wall and the door wall) needs two environments: `@FERRY_CABIN_A`, `@FERRY_CABIN_B`. A scene shot from one side needs one, however many stills it has.
- **An environment belongs to one scene.** Two scenes in the same kind of place, or the same place at another time, get two environments. Never merge stills from different scenes into one environment.
- **Every shot has an environment behind it, close-ups too.** Even an extreme close-up of hands needs the place behind them, or the video model invents one. A close-up uses its scene's environment for the side it faces; its shot table gives the reason `Scene environment, side A`. When no wider shot of the scene faces that side, or the scene is only close-ups, the close-up gets an environment of its own, built from its still.

## Built from the stills

The still is the environment already; it only has people in it. So the environment is an edit of the still, not a new picture: the people come out and everything else stays as the still has it, the light and the look included. Start from the scene's still of that side that shows most of the place.

It drops only the people and what they hold or carry. It keeps what stays put where it stands: the chopping block, the table, the vat, the gangplank from the boat to the quay, moored ships, the crane, a parked lorry, the street's traffic, the deck the camera stands on: [[elements]].

## The prompt

```prompt
Provided image shows [the place, where, when]. This is a simple editing job to remove all the people[, and what they hold]. Keep [what must not go with them].
```

then `![ref](<still address>)` below the fence. That is the whole prompt.

- **Keep** names what a model might take out along with the people: the traffic, the chopping block, the boats, the loaves on the table. Name what matters, not every object.
- **Name the hero in the removal.** "Remove all the people, and the glass the woman raises" mentions her only as the glass's owner, and the model keeps her and takes the glass. Write "remove the laughing woman in front with her glass, and everyone behind her".
- **In a close-up** there are no whole people to remove, so name the parts: "remove the arms, the hands and the paddle. Keep the vat and the foaming mash."
- **A prop the hero holds goes with them** (the axe, the bottle), and so does a vehicle that acts (the boat in its wake): each has its own asset, and the video prompt puts it back.
- **Never describe the place again,** never add a format, look, light or negative block. A long text prompt makes the model build a new place from the words, and the environment no longer matches the still. The project's look belongs in the video prompt.

## Which model

Both Seedream and GPT Image, then pick: [[models]]. Soul does badly on environments.

## Files

`PROMPTS/SEEDREAM-5.0/03_ENVIRONMENTS/Scene_NNN/@NAME.md` and the same file under `GPT-IMAGE-2.5/`. Same text in both.
