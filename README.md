# Track Bar & Drag Link Simulator

A simple visual tool to check your track bar and drag link geometry, and catch bump steer before it bites you.

## 👉 [Open the tool](https://charleskh.github.io/track-bar-and-drag-link-simulator/)

Runs right in your web browser. Nothing to download or install, and it works on your phone too.

## How to use it

1. **Drag** the ends of each bar, or **type** exact lengths and angles in the boxes.
2. Every square on the grid is **1 inch**.
3. The faint curves show how each bar swings as your suspension moves up and down.
4. Keep an eye on the **bump-steer mismatch** number. The smaller it is, the less your steering wanders over bumps.

Play with the lengths and angles until the two bars move together. That is the sweet spot.

## How the analysis works

**The core idea:** as the suspension moves up and down, the axle-side end of each bar does not move straight up and down. It also moves sideways, because it follows an arc. The panel measures that sideways movement.

### 1. Sideways movement for each bar

Choose a wheel-travel amount using the "± in" field, which defaults to ±4 inches.

The tool moves the axle-side end of each bar up and down along its actual travel arc, then measures how far it shifts sideways over that range. That side-to-side distance, measured in inches, is the bar's sideways movement.

### 2. Bump-steer mismatch

Bump steer is not the gap between the two arcs on the grid, and it is not each arc's total width. It is how differently the two ends move sideways for the **same** wheel travel.

So the tool steps both ends through the travel range together and, at each step, compares how far each one has shifted sideways from ride height. The **bump-steer mismatch** is the largest difference between those two shifts across the whole range:

    largest value of | track bar sideways shift − drag link sideways shift |

If both ends move sideways by the same amount through the same travel, they stay in sync and suspension movement does not steer the wheels. If they move by different amounts, the drag link pulls on the steering as the suspension cycles, and that difference is what causes bump steer.

Two bars can sit far apart on the grid and still have a small mismatch. A static offset is not bump steer. What counts is whether the two ends move **together**.

### 3. Good, caution, and warning ratings

The color scale currently uses these general guidelines:

- Under about 0.05 inches: Excellent
- Under about 0.15 inches: Minor
- Above about 0.15 inches: Noticeable

The geometry calculations are exact, but these thresholds are just reasonable defaults for quick feedback. They do not come from a published industry standard, and can be adjusted if better reference values are available.
