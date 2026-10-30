# Calculator

Type a calculation and the result appears as you go: a highlighted card at the top of the list shows
it, and it is also shown faintly next to what you typed. **Enter** copies the result. Recent results
are kept so you can reuse them.

> [!NOTE]
> The calculator only reacts when the **whole** text looks like a calculation, so an ordinary search is
> left alone. The full reference is also available inside the app, in **F1 → Calculator**.

## What you can type

| You can type | Examples |
| --- | --- |
| Arithmetic, powers, factorials | `(2+3)*4`, `2^10`, `5!` |
| Percentages | `15%`, `100 - 15%`, `20% of 150` |
| Functions | `sqrt`, `cbrt`, `abs`, `round`, `floor`, `ceil`, `trunc`, `sign`, `sin`, `cos`, `tan`, `asin`, `acos`, `atan`, `sinh`, `cosh`, `tanh`, `log`, `ln`, `log2`, `exp`, `fact` |
| Constants and the last result | `pi`, `e`, `tau`, `phi`, `ans` |
| Units and bases | `10 km to mi`, `100 f to c`, `255 to hex`, `0xFF`, `0b1010`, `0o17` |

## Details that matter

- Trigonometry works in **radians**.
- `mod` is the remainder: `10 mod 3`.
- `%` after a number is a fraction (`15%` = 0.15), except after `+` or `-`, where it applies to the
  left side: `100 - 15%` = 85.
- While a valid calculation is on screen, the web and Settings results are hidden — you are typing
  maths, not looking for an app.

> [!TIP]
> `ans` is the previous result. `100 + ans` chains calculations without retyping anything, and
> **Enter** copies the current result to the clipboard.

## Settings

| Setting | Default | What it does |
| --- | --- | --- |
| Calculator | `On` | Turns the result on or off. |
| Calculator display | `Card and inline text` | Card, inline text, or Both. |

---

**Prev:** [Custom entries](custom-entries.md) | **Next:** [Appearance and sounds](appearance.md) →
