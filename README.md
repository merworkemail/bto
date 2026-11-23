# Blk 74A Reno Planner

An in-browser renovation planner for the HDB **4-Room Type 2** unit at **Blk 74A**. The plan is drawn to scale (in mm) from the HDB floor plan: 89 m², which is 86 m² of internal floor area plus the A/C ledge.

It's a single `index.html` file with no build step. Open it in a browser to use it.

## What it does

- **Floor plan to scale.** Shows rooms, doors, windows and the dimension strings from the HDB drawing.
- **Walls.**
  - Structural walls and columns (shaded black on the HDB plan) are locked.
  - Non-structural partitions can be marked for removal. Doors in a removed wall go with it.
  - Bathroom walls can also be removed, but the app warns you about HDB approval, the 3-year no-hacking rule and redoing the waterproofing.
- **Flooring and paint per room.**
  - Flooring options are SPC vinyl, homogeneous tile, 1200×600 porcelain, engineered timber, microcement and carpet. Each has tone choices.
  - Paint comes in 10 colours, or you can leave a room unpainted.
  - Bathrooms only offer floorings that suit wet areas.
- **Furniture and carpentry catalogue.** About 45 items at real sizes in mm.
  - Drag, rotate and resize items. They snap to a 50 mm grid and to wall faces.
  - Clearances to the nearest walls show live while an item is selected.
  - An item turns red when it overlaps a wall or another piece.
- **Measure tool.** Drag on the plan to measure any distance in mm.
- **Budget.**
  - The total is grouped into hacking, flooring, painting, built-in carpentry (priced per metre run), loose furniture, and electrical and services.
  - It adds a contingency buffer and GST, and tracks the total against your budget.
  - Every rate can be edited in the **Rates** tab.
- **Layouts.**
  - Changes autosave in your browser, and you can save named layouts.
  - Undo and redo are available.
  - To share a layout or back it up, copy it as layout code, then load it again by pasting the code or opening a `.json` file.

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| R / Shift+R | Rotate selected item |
| Delete | Delete selected item |
| Ctrl+D | Duplicate |
| Arrows (Shift) | Nudge by 10 mm (100 mm) |
| M | Measure tool |
| Ctrl+Z / Ctrl+Shift+Z | Undo / redo |
| Esc | Deselect |

## Notes

- Prices are indicative figures for planning in Singapore. Get itemised quotes from HDB-registered renovation contractors before committing.
- HDB rules always win over this app. Structural elements, the household shelter's walls, and wet-area tiles in the first 3 years can't be hacked.
- Geometry is read off the HDB sales plan, so wall thicknesses and positions are approximate, typically within about 100 mm.
