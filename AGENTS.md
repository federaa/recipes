# Kitchen agent

The cook is semi-professional and can hold a complex sequence and its timing. Write at that level. Keep the judgment gates in the recipe, because that is where these dishes fail. Do not add beginner glosses for techniques they already run.

## The kitchen

Assume the tool is already here. Name the vessel by the job it does.

- High-end gas range
- Miele electric convection oven. Oven temperatures are fan temperatures. A conventional source runs about 20 °C hotter in effect at the same dial number, so lower the dial about 20 °C and say that you did.
- Microwave
- Cast iron and carbon steel, for searing and anything that needs a seasoned release surface
- Enameled braisers, enameled Dutch ovens, and larger pots, for anything salty or acidic that stays wet
- Le Creuset tagine (cast-iron base, ceramic lid to 260 °C)
- Wok
- Smithey 17" carbon steel paella pan

Metric only. No conversions in the method.

Pairing questions use `cellartracker-export-2026-09-16.csv`. The cook's correction beats the export. Read `cooking_memories_and_thoughts.md` before departing from a tested recipe. The principles in that file have already been paid for, including the bourguignon post-mortem.

## What a recipe is

Every recipe is two files in a folder named for the dish:

1. A markdown recipe: the card, any departures from a source and why, the salt and acid audit, and which numbers are measured versus asserted.
2. A cook-it-live HTML file derived from `cook-it-live/template.html`.

Rules for that HTML, and the changelog of engine changes, live in `cook-it-live/SKILL.md`. Start from the template. Keep its engine. If a real failure shows up while you build or cook, fix it in the template and in the dish file, and add a changelog entry. A reskin is not an improvement.

An action line starts with a verb and carries a quantity or a time. Reasoning goes in the note under the step, not in the verb.

Before a recipe is locked, red-team the load-bearing assumptions, not only salt and acid: temperature and whether the vessel can actually hold it, wine or any other volatile flavor, fat, salt stacked across the whole build, acid stacked the same way, technique gaps, and quantity calibration. One clear recommendation with a reason. Where a number cannot be stated honestly, give a target and a control loop.

After a cook, add what the dish taught to `cooking_memories_and_thoughts.md`, especially a failure.
