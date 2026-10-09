# Classwork feedback 20261009

**Student:** Frankie
**Classwork:** Classwork 20261009 — B2.3 Programming Constructs
(functions · selection · repetition · library functions incl. `Random`)
**Date:** 2026-10-09 · **Marked:** 2026-10-09
**Answer language:** Java (required for DP1).

## Score

**77 / 100**

| Question | Score |
|---|---|
| Q1 — Reading functions and loops | 29/30 |
| Q2 — Library functions: the `Random` class | 22/30 |
| Q3 — Writing a complete program (Collatz) | 26/40 |

Full marked pages: `Classwork20261009_marked_DP1_20261009_Frankie_p1..p3.png`

Your **Q2 (a) (iv)** was the best library-functions answer in the class — read the note at the end.

## Feedback on incorrect answers

**Q1 (d) — 5/6**
- The value-returning case is explained well and you gave an example from this paper (`area`).
- The `void` case has no example. Use `countUp()` in part (b): it returns nothing at all and simply
  prints — which is why it could not be written inside `System.out.println(...)`.

**Q2 (a) (i) — 0/2**
- `nextInt(6)` returns **0 to 5**, not 1 to 6. The argument is the **upper bound**, and it is
  **excluded** — slide 42 writes this as `[0, <upper_bound>)`.
- (Your answer to (ii) was right, so it looks as though the two parts were swapped in your head. Be
  careful to separate *what the method returns* from *what the program prints*.)

**Q2 (a) (iii) — 1/2**
- Correct that the loop runs four times. Add that `nextInt()` produces a **new** value on every call.

**Q2 (c) (ii) — 3/4**
- You correctly identify `cnt` as the points inside the circle and `N` as the total, and the square's
  area as 1. The radius of the circle is 0.5, so its area is `πr² = 0.25π` — the fraction
  `A_square / A_circle` you wrote does not come out to `π × 0.5`. Cleaner chain:
  `cnt / N ≈ A_circle / A_square = 0.25π / 1`, therefore `π ≈ 4 × cnt / N`.

**Q2 (c) (iii) — 1/3**
- `cnt` is an `int`, not a decimal. The reason `4.0` is written is **integer division**: `cnt` and
  `N` are both whole numbers, so `4 * cnt / N` is worked out in whole numbers and the fraction is
  thrown away. `4.0` forces the expression into `double` arithmetic.

**Q2 (b) (i) — 4/5**
- The body is right, but the keyword is **`static`**, not `class`. `public class int roll()` is not
  a method declaration — it will not compile. It should be
  `public static int roll() { return rnd.nextInt(6) + 1; }`

**Q3 (c) — not answered (0/6)**
- You left a single "?" here. This is worth 6 marks.
- The answer: a `for` loop needs its repetition count to be **known before the loop starts** (e.g.
  `for (int i = 0; i < 5; i++)`). Here the number of steps depends on the starting value and can
  only be discovered by running the sequence, so the loop must keep going **until a condition
  (`n == 1`) becomes true** — which is what a `while` loop is for.

**Q3 (d) — 8/16**
- Three problems:
  1. **No spaces.** You used `System.out.print("" + n)`, so the output is `63105168421` — one
     unreadable run of digits. The question requires a space between each pair of numbers:
     `System.out.print(n + " ")`.
  2. **`n` is destroyed.** By the time you reach `steps(n)`, `n` is 1, so it prints `Steps:0`, not
     `Steps:8`. Save the user's number in a second variable before the loop.
  3. **Your expected output for 7 is wrong.** The second term of 7's sequence is **22**
     (3 × 7 + 1 = 22, since 7 is odd), not 12. The remainder of the sequence from 11 onwards is
     correct, so this looks like a slip — but it is a slip that proves the code was not run.

## What went well

- **Q1 (a), (b), (c)** — all three outputs exact.
- **Q2 (a) (iv) — the strongest answer in the class.** You named both advantages (reusability and
  code reliability) *and* linked them back to `nextInt()` replacing code you would otherwise have to
  write yourself. That is a 4-mark answer of the kind the examiner is looking for.
- **Q2 (c) (i)** — the range with the upper bound excluded, plus a correct description of the shape.
- **Q3 (a) and (b)** — both perfect. Your `steps()` is exactly right, including the initial
  `count = 0`.
- **Q2 (b) (ii)** — the loop and the space-separated output are correct.

## Next steps

1. **Never leave a part blank.** Q3 (c) was 6 marks for two sentences. A blank scores zero even when
   you know the topic (and you clearly do — your Q3 (a) and (b) are perfect).
2. **Run the program, or trace it, before writing the expected output.** Q3 (d) is a 16-mark question
   built around two traps, and both of them caught you. Two minutes with the code would have shown
   both the missing spaces and `Steps:0`.
3. **Separate "what the method returns" from "what the program prints".** Q2 (a) (i) and (ii) ask
   about those two different things, and your answers came out swapped.
4. **`static`, not `class`.** A method needs `public static <type> <name>(...)`. Worth writing out
   five times until it is automatic — the same slip costs marks in every programming question.
