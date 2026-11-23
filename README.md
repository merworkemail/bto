# Blk 74A Reno Planner

An in-browser renovation planner for the HDB **4-Room Type 2** unit **#25-509** at **Blk 74A, Tanglin Halt Cascadia**. The plan is drawn to scale (in mm) from the HDB floor plan: 89 m², which is 86 m² of internal floor area plus the A/C ledge.

It's a single `index.html` file with no build step. Open it in a browser to use it.

## How it works

The 3D model fills the screen. Everything else floats on top of it, so the model stays the focus:

- **Plan inset (bottom right).** A live floor plan that shows where you're looking. Click a room on it to fly the camera there. Use the expand button, or press **Tab**, to swap the plan and the 3D view.
- **Tool rail (left).** Furnish, Finishes, Walls, Measure and Checks. Each tool opens one panel, and only that panel.
- **Selection bar (bottom).** Click anything to get its actions in one place:
  - **Furniture:** size, rotate, duplicate, delete.
  - **Rooms:** flooring and paint.
  - **Walls:** remove or restore. Structural walls show as locked.
- **Camera (top).** *Overview* to orbit the flat, *Walk* to explore at eye level (W A S D to move), and *Cut-away* to lower the walls. Double-click any floor to walk there.
- **Room labels.** Every room and the entrance are tagged on the model. Click a tag to select that room, or click the entrance tag to walk in through the front door. In Walk mode, a chip shows which room you're in.
- **View and time of day.** A 360° view of surrounding HDB blocks, trees and sky shows through the windows. Switch between **Day**, **Sunset** (low sun, long light through the windows) and **Night** (city lights, with warm lamps inside the flat).

## Features

- **Design options.** Click the card at the top left to keep several complete versions of the flat (Option A, B, C…). Each has its own layout and finishes. You can duplicate, rename or delete them, and **Compare** them side by side.
- **Before / After.** One switch (or the **B** key) flips between the flat as handed over and your design. The Before view is read-only.
- **Electrical layout.** Place ceiling lights, downlights, pendants, fans, power points, data points, switches and aircon units. They show as standard symbols on the plan and appear in 3D.
- **Ceilings.** Choose no false ceiling, a flat false ceiling, or cove lighting (an L-box with an LED strip) per room. Ceilings, lights and fans show in Walk mode, and cove lighting glows at sunset and at night.
- **Export pack.** **File → Open export pack** builds printable A4 pages: the floor plan with dimensions and electrical symbols, 3D views, a room schedule, and electrical and carpentry schedules. Print or save it as PDF, or download the plan and 3D views as images.
- **Walk mode built for comfort.**
  - A third-person, over-the-shoulder camera follows a see-through figure. First person is one tap away.
  - Movement eases in and out, and you stop at walls, closed doors and furniture.
  - Click or tap the floor to walk there.
  - Use the "You're in" chip to jump to any room with a quick fade.
  - You can open doors, and select, move and add furniture, while walking.
- **Real sunlight (Sun study).** Uses the block's orientation from the HDB site plan: the bedrooms face about 333°, north-north-west.
  - Pick a month and time to see where the sun is and which windows get direct sun.
  - See how many afternoon hours of sun each room gets.
  - Day, Sunset and Night are real times. North arrows show on the plan and in 3D.
  - The view outside the windows is drawn from level 25.
- **Neighbouring blocks.** Blocks 74A (its other wings), 74B, 75A and 75B are modelled from the site plan at their planned heights. The sun study says which windows they put in shadow, and the blocks are visible through your windows when walking.
- **Window heights.** The W1 three-quarter-height windows (bedrooms and living front) and the standard windows match the HDB plan in 3D, and are labelled on the plan.
- **Share by link.** **File → Share a link** creates a short link to the exact design, using the system share sheet on phones. Opening it adds the design as a new option.
- **Character.** Walk as a man (177 cm) or a woman (170 cm). Both heights can be edited, and first person uses that person's eye level.
- **Bare house.** The flat as handed over, with no furniture and nothing changed, is always available. Use File → Reset to bare house, the pinned row in Versions & history, or a new "Bare house" design option. All of these can be undone.
- **Mouse controls.** Left-click selects things and walks. Right-drag orbits or looks around, middle-drag pans, and the wheel zooms. Option/Alt + drag also orbits on trackpads.
- **Walking.**
  - Space jumps, and Q / E turn.
  - Walls and furniture between the camera and your figure fade out, so your figure is never hidden. Zooming out lifts the camera over the walls.
  - In Walk mode, furniture only moves after you press **Move**, which prevents accidental drags.
  - Doors swing open and shut smoothly.
  - The common corridor and lift lobby outside the front door can be walked, and you can't step off the edge.
- **Versions and history.** Your design saves continuously on each device. Under **File → Versions & history** you can save named versions of each design option. A safety copy is kept automatically just before any reset or restore.
- **Doors.** Tap any door in 2D or 3D to open or close it, or use the all-doors button.
- **Layout checks.** The **Checks** tool flags furniture that stops a door from opening (the blocked swing shows red on the plan), overlapping items, and walkways under 600 mm. A badge shows the count.
- **Custom items.** Add any product by name and W × D × H, with price and colour. It's saved under **My items** for reuse.
- **Colours and materials.** Choose fabric for sofas, wood for loose furniture, and laminate for carpentry (with "use on all carpentry"). Colours show in 3D and tint the plan.
- **Touch screens.**
  - An on-screen joystick lets you walk in Walk mode.
  - Double-tap a floor to walk there.
  - Twist two fingers to rotate the selected item.
  - Pinch to zoom.

- **Floor plan to scale** from the HDB plan, with dimension strings.
- **Walls.** Structural walls (shaded black on the HDB plan) are locked. Partitions can be removed, and bathroom walls come with HDB warnings.
- **Flooring and paint per room.** Six flooring types with tones, and 10 paint colours. You can apply one flooring across every dry room.
- **About 60 furniture, appliance and carpentry items**, including storage and bunk beds, a wall-mounted TV, a standing desk, a dishwasher, a tall oven unit, a stacked washer-dryer, a ceiling drying rack, a water heater, an aircon condenser and a piano at real sizes in mm.
  - Drag them in 3D or 2D. They snap to a 50 mm grid and to walls.
  - Clearances to the walls show in the plan.
  - An item is flagged when it overlaps a wall or another piece.
- **Measure tool** on the plan.
- **Layouts.** Undo and redo, autosave, named layouts, and a layout code for sharing.

## Performance

- The 3D scene is built once and then updated incrementally. Only the furniture that changed is rebuilt.
- Shared geometry keeps memory low.
- Shadows recalculate only when the scene changes.
- Frames are drawn only while something is moving, so the page does no work while idle.
- The 3D engine (three.js r128) loads from a CDN. If it can't load, the app falls back to the plan view.

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| R / Shift+R | Rotate selected item |
| Delete | Delete selected item |
| Ctrl+D | Duplicate |
| Arrows (Shift) | Nudge by 10 mm (100 mm) |
| M | Measure tool |
| Tab | Swap plan and 3D |
| B | Before / After |
| Space | Jump (Walk mode) |
| Q / E | Turn (Walk mode) |
| W A S D | Walk (in Walk mode) |
| Ctrl+Z / Ctrl+Shift+Z | Undo / redo |
| Esc | Deselect |

## Notes

- HDB rules always win over this app. Structural elements, the household shelter's walls, and wet-area tiles in the first 3 years can't be hacked.
- Geometry is read off the HDB sales plan, so wall thicknesses and positions are approximate, typically within about 100 mm.
