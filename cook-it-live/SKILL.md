# Cook It Live

A cook-it-live file is a single self-contained HTML page the cook opens on a phone beside the stove. It is one step at a time, with the quantity for that step on the step, a timer dock, and a decision gate wherever the dish can fail quietly.

The current engine is `template.html`. Copy that file into the dish folder. Do not rebuild the page from an older recipe, and do not rebuild it from the Morel pappardelle page (that one is a static card, not a cook-it-live file).

Each dish keeps its own copy, because these files move to the phone one at a time. A shared script would not survive that.

## Derive a dish

1. Copy `cook-it-live/template.html` to `<Dish Folder>/<slug>_cook_live.html`.
2. Set the title, the `<h1>`, the meta line, and `RECIPE_ID` (a stable slug, unique per dish). The restore key is `cook-live:<RECIPE_ID>`. Two dishes that share an id will share a half-finished cook.
3. Replace the mise list. Group it the way the cook reaches for it. A quantity that is conditional stays in the list and is marked, the way the miso file strikes the soy that only goes in for unsalted stock.
4. Replace `STEPS`. Leave the script below `STEPS` alone unless you are fixing the engine.
5. Retint the `:root` colors and, when the dish has non-overlapping components, add a legend. Do not restyle the layout.
6. If you changed the engine because something actually failed, put the same change in `template.html` and add a changelog entry below. The template is the base the next dish copies.

## Step object

```js
{
  kind: "plain",          // or "timed" or "gate"
  phase: "Braise",        // rail group; omit if the dish is one straight line
  where: "Braiser",       // the vessel or station, named by the job
  title: "Dissolve the awase",
  uses: [ { amt: "25 g", name: "awase miso" } ],
  probe: "82–85 °C",      // optional
  probeLabel: "Pull at",  // default. Use "Oven" only for a setpoint, never for a doneness target
  also: [ "Garlic is still in the oven, covered" ], // other streams still in flight
  body: "<p><strong>Whisk</strong> until it dissolves.</p>", // trusted HTML; verb first

  // timed only
  timerName: "Braise",
  defaultSec: 2700,
  minSec: 2400,
  maxSec: 3600,
  timerNote: "First check. Then read it.", // optional; the dock already tells the truth about the clock

  // gate only — two or three branches
  branches: [
    { type: "good", glyph: "✓", head: "Deep gold, collapses", text: "Lift them out." },
    { type: "wait", glyph: "!", head: "Pale and firm", text: "Eight more minutes." },
    { type: "bad",  glyph: "✕", head: "Dark at the edges", text: "Discard the dark cloves." }
  ]
}
```

`good` is proceed. `wait` is not done yet, and the cook goes back to the same pot. `bad` is the failure you cannot stir back in. Do not paint both with the same branch. The red-sauce garlic gate did, and a pale clove and a scorched clove are different decisions.

`body` may use `<p>`, `<strong>`, `<em>`. Everything else the renderer prints is escaped. `<em>` is the house mark for a quantity or a temperature inside a sentence. The `uses` chips carry the same quantities, so a glance gets them without reading the paragraph.

A timed step's default is the first check or the typical duration, and `minSec` / `maxSec` are the honest window. Say so in the body when the endpoint is a temperature, a weight, or a texture rather than the beep. The timer is a backstop.

Long steps (default of 20 minutes or more) adjust by 5 minutes and 1 minute. Shorter steps adjust by 1 minute and 30 seconds.

## What the engine already does

Do not re-implement these, and do not drop them while editing a dish.

- Timers store an end timestamp and read the wall clock. Locking the phone does not stall them, provided the tab is still loaded. Coming back recomputes. If the browser threw the tab away, reopening the same file restores the end time, the step, and a timer that already finished.
- A screen wake lock is requested while any timer runs, and released when nothing is running. A notification is requested on the first start. Both depend on the browser allowing them. On zero, regardless: a beep, a flashing dock chip, and an assertive live region. A timer that hits zero while the file is closed announces once when the file is opened again.
- On a phone, Sequence and Mise are collapsed under their own controls. Opening one scrolls it up past the step. The step stays first. The pips are still there.
- Sound, the step, the done set, timer drafts, and timers persist under `RECIPE_ID`. Start over is a two-tap control so a wet thumb does not wipe a braise.
- Rail phases, a vessel chip, quantity chips, and a labeled probe badge.
- An "Still running" banner for a step that overlaps another stream.
- Arrow keys move steps. Tap targets on the timer are 44 px.
- The page stands alone. Fonts are the only network request. It has to work from a phone that opened the file out of a sync folder.

## Writing the steps

Same rules as the markdown, applied to a screen that is being read with wet hands.

- One action per step. A gate is its own step, before the cook passes the point where the choice stops mattering.
- The action line leads with the verb. The quantity is on that line and in `uses`.
- Name the vessel on the step (`where`), and split steps when the vessel changes. Seasoned metal for the sear. Enamel or ceramic once the liquid is salty or acidic and staying there.
- A parallel stream (garlic in the oven while the braiser is built on the gas) is a step of its own when the cook acts on it, and an `also` line on the steps in between so it is not forgotten.
- Oven numbers are Miele convection. If you converted from a conventional source, the markdown carries the reason; the step just shows the fan temperature.
- Metric only.

## Changelog

### 2026-10-23

Filed the engine as `template.html`. Before this, each dish re-derived the page, and the slow-oven red sauce dropped the phase rail, the vessel chip, and the quantity chips the miso braise had.

Timers counted down with `setInterval`. A phone throttles or freezes that when the screen locks, so a braise timer only advanced while the cook was looking at it. They now use an end timestamp, restore it if the tab is killed, request a screen wake lock, and notify on zero where the browser allows it. A timer that already finished announces once on reopen. The phone layout can open the named sequence, which the older files hid.

Gates grew a `wait` branch, distinct from `bad`, because "not yet" and "ruined" were sharing one color. The probe badge takes a label, so an oven setpoint is no longer printed as a pull temperature. Steps of 20 minutes or more adjust by minutes. A step can name what is still running on another burner. Start over asks twice.
