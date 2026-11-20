# Beef Bourguignon — Working Version

**Serves 4–6 · ~2 h 15 min · 90 min hands-off**

Adapted from the NYT recipe, with four changes and nothing else touched. The base recipe is tested and tuned; this is not a rebuild.

Companion file: `beef_bourguignon_cook_live.html`

---

## The four changes

| # | Change | Reason |
|---|---|---|
| 1 | Salt to **1%** — 14 g for 1.36 kg | Original runs ~0.5–0.8%, under-seasoned once the liquid reduces |
| 2 | Tomato paste **5 g → 30 g**, fried to brick | A teaspoon disappears in 750 ml of liquid |
| 3 | **250 ml stock** replacing a third of the wine | All-wine gives no savory floor |
| 4 | Mushrooms and pearl onions in **separate pans** | Different cooking curves — together, the mushrooms waterlog before the onions are tender |

**Not changed, deliberately:** the flour, the 175°C oven, the 90-minute braise, the whole-bottle wine approach. Those work.

---

## Ingredients

### Beef
- 1.36 kg beef chuck, 5 cm cubes
- 14 g fine sea salt *(1% of meat weight)*
- 2 g black pepper

### Base
- 140 g lardons, pancetta, or slab bacon, diced
- 150 g onion, finely chopped
- 100 g carrot, sliced
- 2 garlic cloves, minced
- 30 g tomato paste
- 16 g flour

### Braise liquid
- 500 ml red wine
- 250 ml beef stock
- 1 bay leaf
- 1 thyme sprig

### Garnish
- 225 g pearl onions, peeled
- 225 g cremini, halved
- 15 ml olive oil
- Pinch of sugar
- Chopped flat-leaf parsley

---

## Method

**1. Salt the beef.** Cube, weigh, salt at 1%, add pepper. Rest 30 minutes at room temperature, or up to 24 hours uncovered in the fridge.

**2. Render the lardons.** Dutch oven, medium-low, until the fat is out and the edges crisp. Slotted spoon them onto a plate. **Leave all the fat in the pot.**

**3. Sear the beef in two batches.** Heat the fat until it threads smoke. Single layer, space around every cube, don't move anything until it releases cleanly. Deep brown on three faces. Both batches out.

> **Fond check.** Brown and glossy, lifts when you drag a spoon through — good, carry on. Black, dry, welded to the base — pour off the fat, wipe the pot, restart the aromatics on fresh fat. A bitter wine braise can't be fixed later.

**4. Aromatics.** Onion and carrot in the fat over medium, ~10 minutes, until the edges brown. Garlic for the last minute.

**5. Tomato paste, then flour.** Paste in, **fry a full 2–3 minutes** until it darkens to brick and smells sweet. Then the flour, stirred through, one minute.

**6. Braise.** Wine and stock in, scrape the base clean. Bay, thyme, the beef, and half the lardons. Lid on, 175°C, 90 minutes, turning the beef once halfway.

> The liquid simmers at this setting and that's intended — it's a fast-hot braise, and the speed is what makes 90 minutes work.

> **Doneness gate.** Ninety minutes is a floor. A fork should enter with light resistance and the cube should hold its shape when lifted. Still springy — another 20 minutes, test again. Falling apart when lifted has gone too far.

**7. Mushrooms, own pan.** Dry, hot skillet, no fat. They go quiet, release liquid, reabsorb it, then brown. Wait out the wet phase. Butter and salt at the end.

**8. Pearl onions, own pan.** Olive oil, 60 ml water, pinch of sugar, salt, pepper. Simmer covered ~15 minutes until tender. Uncover, high heat, ~6 minutes to a dark syrup that coats them. Shake the pan rather than stirring.

> **Salt gate.** Taste the braising liquid before adding anything. The 1% brine, the cured lardons, and 90 minutes of reduction have all contributed. If it needs lifting, salt in 2 g steps. If it's already salty, loosen with unsalted stock and lean on pepper and parsley.

**9. Plate.** Scatter mushrooms, glazed onions, and the reserved lardons over the top. **Don't stir them in** — that undoes the point of separate pans. Parsley over. Egg noodles or crushed potatoes underneath.

---

# Post-mortem: the rebuild that failed

Recorded because the failure is more instructive than the recipe.

## What was attempted

A restructured version replacing flour with gelatinous stock, pre-reducing the wine, separating and reducing the sauce off the meat, and cooking every garnish apart. Executed 26 July. Result: over-tender meat, a sauce that wouldn't set, and no wine flavor at all.

## What went wrong

**1. The braise spec was physically impossible.** Lid plus a parchment cartouche, 150°C oven, claimed 88°C liquid. Sealing the pot eliminates the evaporative cooling that keeps braise liquid below boiling — at that ambient it goes to 96–100°C. The recovery instruction, "drop to 140°C if boiling," wouldn't have worked either.

**2. Worse, it was two incompatible systems welded together.** 88°C is a low-temperature braise target, where chuck needs 6–8 hours. Three hours is a classical-braise duration, which only works at simmer temperatures. Either system is coherent. The hybrid isn't. Lowering the oven alone wouldn't have fixed it.

**3. Pre-reducing the wine destroyed the dish's defining flavor.** Reducing 1125 ml to 350 ml, then diluting that into 1.2 L of stock for three hours. The stated justification — braising destroys wine's top notes, so concentrate first — is not reasoning. Reduction destroys top notes by the same mechanism. It front-loads the loss rather than avoiding it. The finished sauce tasted like thick stock.

> Reducing wine first is a real technique — for pan sauces and bordelaise, where wine is one component and stock is the base. In a braise where the wine *is* the flavor, it removes the point of the dish.

**4. Removing the flour eliminated the safety margin.** The gelatin-instead-of-flour architecture only pays off with stock that sets to a jelly. With ordinary stock there's no fallback, and powdered gelatin added late failed to rescue it. Beurre manié — the flour — is what finally worked.

## What the failure actually taught

- **A self-audit that misses the load-bearing assumptions is worse than none.** The red-team sections covered salt load and acid balance. The braise temperature and the wine handling — the two decisions that determined the outcome — were never examined. The audit bought confidence it hadn't earned.
- **Technique stacking is not improvement.** Five sophisticated changes at once, none tested, each adding failure modes.
- **A tested recipe carries information that reasoning can't reconstruct.** The NYT version has been cooked thousands of times. Changes should be small, few, and individually justified.
- **Where a number can't be stated with confidence, give a target and a control loop.** "Probe at 20 minutes and adjust the oven ±15°C to hold 93–96°C" survives contact with a real kitchen. "150°C" does not.

## Retained from the rebuild

Only what earned its place, and it's already folded into the four changes above: salt at 1%, meaningful tomato paste, some stock in the liquid, garnishes in separate pans.

Everything else — pre-reduced wine, no flour, separated sauce reduction, low-temperature braise, added shank — is discarded.

---

# Cooked

This card, as written above, has been cooked in this kitchen, and it was good. It is the tested version. Do not depart from it on arithmetic alone.

Open: which oven mode the 175 °C was set in. The house convention is that oven numbers are fan numbers, so the card reads as fan. If it was a conventional mode on the Miele, write that onto the card, because the next cook will otherwise set fan.

---

## Salt and acid audit

**Salt, stacked.**

| Source | Into the dish | Basis |
|---|---|---|
| Beef brine | 14 g | Computed, 1% of 1.36 kg |
| Lardons, half in the braise | about 2–3 g | Asserted, from pancetta at about 3–4% salt |
| Lardons, the held half | about 2–3 g | Same, eaten on top |
| Beef stock, 250 ml | about 2 g if standard boxed; under 0.4 g if unsalted | Asserted from typical labels |
| Onions and mushrooms | unmeasured, to taste | The card says salt without a number |

That comes to about 1% of the finished stew, which is where the salt gate is meant to land it. The swing factor is how far the liquid reduces.

**Acid.** The wine is the acid: 500 ml, under a lid, barely reduced. The 30 g of tomato paste is fried to brick, which blunts its edge. Nothing is added at the pass, and nothing needs to be.

---

## Numbers

**Measured in this kitchen, by cooking it:** the card as a whole: 175 °C, 90 minutes, a lid, the flour, and the four changes.

**Computed from a rule:** salt at 1% is 14 g.

**From the source, not re-checked against the NYT page:** the beef, lardon, aromatic, flour, wine, and garnish quantities.

**Asserted:** the step timers, and the salt in the lardons and the stock.

---

## Red team, not applied

These came from a red team done on 2026-11-20, before it was known that this card had been cooked. They are proposals for a later cook, one at a time. None of them is part of the recipe.

- **Oven.** The red team read 175 °C as a conventional number carried onto the fan dial and moved it to 155 °C fan. That is withdrawn. The cook was good at 175 °C, and the cook's result beats the arithmetic. What remains is the question of the oven mode, above.
- **Salt window.** At 30 minutes the brine is still sitting on the surface. Overnight uncovered on a rack, or searing within 10 minutes of salting, gives a drier sear.
- **Stock.** Unsalted stock leaves room for any reduction before the salt gate.
- **Skim.** Lift the fat off before the salt gate, because fat hides salt.
- **Lardons.** Re-crisp the held half in the mushroom pan for the last minute.
- **Garnish timing.** Start the onions during the last 30 minutes of the braise, so the stew does not wait for them.
- **Sauce body.** If the sauce runs thin, reduce it before the salt gate, with beurre manié (15 g butter, 15 g flour) as the fallback.
