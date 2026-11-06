# Classwork feedback 20261106

**Student:** Frankie
**Classwork:** Classwork 20261106 — B2.2 Data structures
(arrays · ArrayLists)
**Date:** 2026-11-06 · **Marked:** 2026-11-06
**Answer language:** written in Java — accepted (full credit for correct content).

## Score

**81 / 100**

| Question | Score |
|---|---|
| Q1 — Reading arrays | 27/30 |
| Q2 — Writing array methods and a complete program | 24/30 |
| Q3 Part A — ArrayList | 30/40 |

Full marked pages: `Classwork20261106_marked_p1..p3.png`

## Feedback on incorrect answers

**Q1(a) — 8/10**
- The last value is `nums[4] - nums[0]` = 15 − 9 = **6**, not −5.

**Q1(b) — 9/10**
- The trace and the output 8 21 are right. Check the "a[i] before" cell for i = 1 — it should be 6.

**Q2(a) — 6/10**
- You **redeclare `data`** inside the method, then loop over an undefined array `a`. The semicolon after `if` means `count++` runs for every element.
- Use the parameter directly: `for (int i = 0; i < data.length; i++)` and `if (data[i] % 2 == 0)` with no semicolon.

**Q3(c) — 5/12**
- An enhanced `for` cannot be used to remove from the list, and `num.remove(num)` calls `remove` on the `Integer`, not on the list.
- Use an index loop backwards: `for (int i = nums.size() - 1; i >= 0; i--) if (nums.get(i) < limit) nums.remove(i);`

**Q3(d)(i) — 3/6**
- You explain the left shift. Add the consequence: a **forward** loop then skips the element that moves into the removed position.

## What went well

- **Q2(b) — 18/20.** A complete program with a correct average method; only `Scanner.nextInt()` → `scan.nextInt()`.
- **Q1(c) — 6/6.** Runtime error, bounds and termination are correct.
- **Q3(a), Q3(b)** and **Q3(d)(ii)** (noted, no deduction) are correct.

## Next steps

- Write the method from the parameter: never redeclare a parameter inside the method.
- Check that the program compiles — class names such as `Scanner` are not objects.
- For removal from an ArrayList: backwards index loop; `nums.remove(i)`.
