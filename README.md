# Marble Water Clock

An animated 3D clock in a single web page. Falling water drives the gears, a pendulum sets the pace, and marbles pump the water back to the top. The clock shows your local time.

Everything is in one file, `marble-water-clock.html`, rendered with [three.js](https://threejs.org/) r128.

## How it runs

The pendulum, the marbles and the water form one closed loop:

1. **Water falls.** The upper tank feeds an overshot wheel with 12 buckets.
2. **The wheel drives the train.** Meshed gears carry its push to every arbor.
3. **The pendulum paces it.** The anchor lets one tooth of the 30-tooth escape wheel through each second, so the whole train moves in ticks.
4. **Marbles ride up.** A 12-pocket lift wheel raises one marble every five seconds.
5. **A marble tips the beam.** It runs down four zigzag rails and drops into a scoop on a walking beam.
6. **The beam pumps.** Each stroke sends a gulp of water up a glass riser to the upper tank, and the marble rolls back to the lift wheel.

## The mechanism

| Part | Details |
| --- | --- |
| Pendulum | 2-second period, swings 4.6° either side, rocks the anchor |
| Escapement | Anchor with two ruby pallets over a 30-tooth escape wheel; the seconds hand sits on the same arbor |
| Drive gears | Water wheel, escape arbor and lift wheel each carry a 20-tooth gear and turn once a minute, linked through idlers of 14, 22, 14 teeth on one side and 14, 24, 18, 14 on the other |
| Going train | Escape pinion 8 → third wheel 60, third pinion 8 → centre wheel 64, giving 60:1 for the minute hand |
| Motion work | 12 → 36 and 10 → 40, giving 12:1 for the hour hand |
| Marbles | Nine in circulation, each on a 45-second circuit |
| Tanks | The upper level rises with each pump stroke and drains steadily in between; the lower tank does the opposite |

Gear tooth counts match the gear sizes, and every meshing pair is phased so the teeth interlock as they turn.

## Controls

- **Drag** to turn the clock, **scroll or pinch** to zoom, **right-drag or Shift-drag** to pan.
- **Arrow keys** turn the view and **+ / −** zoom when the scene has focus.
- **How it runs** lists the six steps; clicking one flies the camera to that part.
- **Pause / Run** stops and starts the motion.
- **¼× / 1× / 4×** changes the speed.
- **Sound** adds a tick each second and a clack when a marble lands.
- **Set to now** returns the clock to local time after pausing or changing speed.
- **Whole clock** resets the camera.

## Running it

Open `marble-water-clock.html` in a current browser with WebGL. It needs an internet connection for two things: three.js from cdnjs and the typefaces from Google Fonts. Without the fonts it falls back to system faces.

The page follows the light or dark theme of the system. With reduced motion switched on, the camera stops swaying and jumps between views instead of flying.

## Limits

- The motion is scripted from the clock time, not physically simulated. Marbles and water follow fixed paths in step with the gears.
- The pump is drawn for effect: a beam stroke this small would not lift water that high.
- The idler gears make a small visible jump at midnight when the time wraps.

## Attribution

Designed and written by **Claude Opus 5.5 Medium** (Anthropic) on 4 October 2026, from this prompt:

> Can you create a web page with an 3d clock animation including a pendulum, marbles, water reservoirs and an intricate mechanism connection all 3 with each other?

Typefaces: Bodoni Moda, Instrument Sans and Spline Sans Mono, served by Google Fonts.
