# Classwork feedback 20260911

**Student:** Frankie
**Classwork:** Classwork 01 — B2.1 Programming Fundamentals (variables, data types, substring manipulation)
**Date:** 2026-09-11
**Marked:** 2026-09-14

## Score

**34 / 100**

| Question | Score |
|---|---|
| Q1 — data types, naming, print vs println | 9/12 |
| Q2 — string manipulation (tracing) | 8/14 |
| Q3 — scope of variables + tracing | 8/16 |
| Q4 — debugging and scope | 2/14 |
| Q5 — program using all data types | 7/20 |
| Q6 — substring-manipulation program | 0/24 |

Note: `Classwork01_20260911_marked_p1.png` and `_p2.png` in this folder show
every mark and deduction in place on your script.

## Feedback on incorrect answers

**Q1 (b) (-2 marks)**
- All four VALID / INVALID judgements are correct, but the question says
  *"State, **giving a reason**, …"* and no reasons were given.

**Q1 (c) (-1 mark)**
- Partly right. You indicated the line break — the `!` is clearly shown as a
  **second line**, which is the part most students miss.
- What is lost is the first line: it should be `Hello World` (a space between
  the words, and a capital `W`, because the source string is `" World"`). You
  wrote `Helloworld`. So the output scores 1 of 2.
- The full answer is:
  ```
  Hello World
  !
  ```
- Your explanation (`print()` will not start a new line, `println()` will) was
  correct and earned its marks.

**Q2 (a) (-2 marks)**
- You wrote `21`; the correct answer is `22`. `"Information"` (11) + the space
  (1) + `"Technology"` (10) = 22. You missed the space in the middle.

**Q2 (d) (-2 marks)**
- You wrote only `T`. `s.substring(12)` returns the characters from index 12
  **to the end of the string** — the output is `Technology`.

**Q2 (e) (-2 marks)**
- You wrote `(12,21)`, which reads like a range. `indexOf("Technology")` returns
  a **single integer** — the starting index, which is `12`. (`println` prints
  `12`, not `(12,21)`.)

**Q3 (a) (-6 marks)**
- The **`y (global)` column is wrong in rows 3 and 4**: you wrote `10` and `13`.
  The global `y` is declared as `static int y = 2;` and is **never changed** —
  it stays `2` for the whole program. `int y = 10;` and `int y = x + 5;` declare
  *new local variables* that only shadow the field; they do not modify it.
- The output column is also incorrect in those rows.
- Correct values: `x` = 5, 8, 8, 8, 8, 8, 8 (it changes once, to 8, and stays);
  `y (local)` = –, –, 10, 10, 13, 13, –; outputs `Inside update(): 8 10`,
  `Inside modify(): 8 13`, `Outside: 8 2`.

**Q3 (b) (-2 marks)**
- You correctly used the word *shadowing* — good. What is missing is the
  conclusion: the global `y` **is never modified**, so when `main()` prints `y`
  it is still `2`, while inside `update()` the name refers to the local `y` with
  the value `10`.

**Q4 (a) (-4 marks)**
- You wrote that `increaseScore()` is not defined as a local variable. That shows
  you have picked up on the local vs global theme, which earns partial credit.
  Two things need fixing to gain the rest:
  - `increaseScore()` is a **method**, not a variable — the variable in question
    is `score`.
  - The actual cause: `int score = score + 10;` is **self-referential**. The
    `int score` declares a new *local* variable, and the `score` on the right-hand
    side refers to that same local variable, which has not yet been given a
    value. The compiler reports *"variable score might not have been
    initialized"*.

**Q4 (b) (-8 marks)**
- You rewrote the method as:
  ```java
  static void increaseScore() {
      int score = score + 10;   // local variable
  }
  ```
  This is the **same code as the original** — the error has not been fixed. The
  `int` must be **removed** so that the name refers to the field:
  ```java
  static void increaseScore() {
      score = score + 10;
  }
  ```
  The output is then `Final score: 10`.

**Q5 (-13 marks)**
- Only three of the five data types appear (`int`, `double`, `String`);
  `char` and `boolean` are missing (worth 4 marks).
- `Age` should be `age` — Java variables start with a lower-case letter.
- The last line `System.out.println( s, charAt 6 )` is not valid Java. `println`
  takes a **single** argument, so it should be e.g.
  `System.out.println(grade);`.
- You used `println` only; the question asks for a **mixture** of `print()` and
  `println()`, and for at least two values to be combined with `+` in one message.
- None of the five values is properly output, and no expected output is shown.

**Q6 — no answer found on the submitted script (-24 marks)**
- Q6 does not appear on either page. It was worth 24 marks — the largest single
  question on the paper — so this is the most important thing to fix.
- If you did answer it, please send the page and I will re-mark it.

## What went well

- Q1 (a): all four data types correct.
- Q1 (b): all four VALID / INVALID judgements correct.
- Q1 (c): you showed the `!` on a **second line** — the structural point that
  most of the class missed — and your explanation of `print()` vs `println()`
  was correct.
- Q2: `charAt`, `substring(0, 11)`, `indexOf` returning `-1`, `toUpperCase` and
  `replace` were all correct — 5 of 8.
- Q4 (a): you connected the question to the local vs global idea, which is the
  right instinct — it just needs to be pinned down to the `score` variable and
  the self-reference.

## Next steps

1. **Answer every question.** Q4 (b) was not properly completed and Q6 was not
   attempted at all — that is 32 marks left on the table.
2. **A local variable does not change the global one.** In
   `int y = 10;` the `int` creates a *new* variable. Without the type
   (`y = 10;`) it would assign to the existing one. This single idea is worth a
   lot of marks across Q3 and Q4.
3. **`println` takes one argument**; `System.out.println(s, charAt 6)` cannot compile.
4. `substring(n)` takes everything from index `n` to the end.
5. Count carefully — `"Information Technology"` has a space in the middle.

---
_Marks and margin notes are also marked up on your scanned script
(`Classwork01_20260911_marked_p1.png`, `_p2.png`)._
