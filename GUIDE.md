# Roadmap: Reactive Spreadsheet Engine

**Deadline: [3-Week Sprint]**
- **Week 1 (Ends [Insert Date]):** Level 1 & 2 - Foundations & State.
- **Week 2 (Ends [Insert Date]):** Level 3 & 4 - The Logic Engine & Dependency Graph.
- **Week 3 (Ends [Insert Date]):** Level 5 - Persistence & Final UX.

## The Knowledge Pillars (Your Curriculum)
For each level, you must master these concepts. Ask me for a "Lecture" on any of these:

### Level 1 & 2: The UI Foundation
- **The DOM:** How JS "sees" your HTML.
- **Dynamic Creation:** `document.createElement` vs template literals.
- **State Management:** Why we store data in Objects, not just on the screen.
- **Event Listeners:** Capturing clicks and keystrokes.
- **Scope & Variables:** `let`, `const`, and why `var` is avoided in modern code.

### Level 3 & 4: The Logic Engine
- **String Manipulation:** `split()`, `slice()`, `replace()`, and RegEx basics.
- **Recursion:** A function that calls itself (crucial for dependency chains).
- **Error Handling:** `try...catch` and why apps shouldn't just crash.
- **Data Structures:** Maps and Sets for high-speed lookups.

---

## LEVEL 1: The Grid & The State
**Goal:** Create a 10x10 grid and a way to store what is in those cells.
- **Challenge 1:** Don't hardcode 100 `<div>` tags in HTML. Use a loop in JavaScript to generate them.
- **Challenge 2:** You need a "Single Source of Truth." If you type "Hello" in cell A1, where does that live in your memory? (Hint: Use an Object or a Map).
- **Success Criteria:** I can see a grid on the screen, and I can open the console to see an object representing the data of every cell.

## LEVEL 2: Cell Interaction
**Goal:** Make the cells editable and reactive to focus.
- **Challenge 1:** When I click a cell, it should become an input. When I click away, it should look like a label.
- **Challenge 2:** Differentiate between "Value" (what I typed, e.g., `=1+1`) and "Display" (what I see, e.g., `2`).
- **Success Criteria:** I can type in any cell, and when I press 'Enter', the value is saved to your state object.

## LEVEL 3: The Parser (The Core Logic)
**Goal:** Evaluate basic math.
- **Challenge 1:** Write a function that checks if a string starts with `=`.
- **Challenge 2:** If it's a formula, how do you solve `1+1` without using the dangerous `eval()` function? (Research: Shunting-yard algorithm or simple string splitting).
- **Success Criteria:** If I type `=5+5`, the cell shows `10` after I press Enter.

## LEVEL 4: Dependency Mapping (Industry Grade)
**Goal:** Reactivity.
- **Challenge 1:** If Cell B1 has `=A1+1`, and I change A1, B1 must update automatically.
- **Challenge 2:** Prevent Circular Dependencies. If A1 depends on B1, and B1 depends on A1, your app should throw an error, not crash.
- **Success Criteria:** Changing one cell triggers a chain reaction of updates across the grid.

## LEVEL 5: Persistence & UX
**Goal:** Make it a real tool.
- **Challenge 1:** Save the state to `localStorage` so refreshing the page doesn't wipe my work.
- **Challenge 2:** Add column headers (A, B, C...) and row headers (1, 2, 3...).
