# Code Review: IndexError (string index out of range)

## Prompt (PromptCraft Structured)

Role:
You are a senior code reviewer and Python debugging expert.

Task:
Analyze a provided Python script that raises "IndexError: string index out of range" and produce a step-by-step diagnosis and fix with code snippets and explanations.

Context:
- Language: Python
- Symptom: IndexError when comparing adjacent characters in a string
- Expected input: a string of words
- Expected output: a compressed string (e.g., run-length encoding like `a3b2c1`)

Style:
Professional, clear, and educational. Use detailed paragraphs and inline code snippets.

Constraints:
- Identify the exact line causing the error
- Explain why the error occurs
- Show expected input/output examples
- Provide corrected code snippets to resolve the error
- Explain the fix and edge cases (empty string, single-character string, spaces)

Output Format:
Detailed paragraphs that include:
1) The line of code causing the error
2) The reason for the error (why the index is out of range)
3) The expected input and output
4) The corrected code snippet and explanation

---

## Example AI Output: Detailed Analysis and Fix

Background:
The common pattern that causes `IndexError: string index out of range` when comparing adjacent characters is iterating over indices from `0` to `len(s)-1` and accessing `s[i+1]` on the last iteration. Below is a representative buggy function, the diagnosis, and corrected code.

### Buggy Example (typical)

```python
def compress(s):
    result = ''
    count = 1
    for i in range(len(s)):
        if s[i] == s[i+1]:  # <-- IndexError occurs here when i == len(s)-1
            count += 1
        else:
            result += s[i] + str(count)
            count = 1
    return result
```

1) Line causing the error

- The exact line throwing the exception in the example above is:

```python
if s[i] == s[i+1]:
```

- When `i` reaches `len(s)-1` the expression `s[i+1]` attempts to access `s[len(s)]`, which is out of range.

2) Reason for the error

- Python string indices range from `0` to `len(s)-1`.
- The loop `for i in range(len(s)):` iterates `i` from `0` through `len(s)-1`. On the final iteration `i == len(s)-1`, so `s[i+1]` is `s[len(s)]` and raises `IndexError`.
- The underlying logic intends to compare each character to the next one; the loop bounds must avoid reading past the last character or must handle the tail after the loop.

3) Expected input and output

- Input: a string of characters (example: `"aaabbc"`) or a string of words depending on spec; if compressing words, the algorithm should operate per-word.
- Output: a compressed string representing runs of identical characters, e.g. input `"aaabbc"` -> output `"a3b2c1"`.
- Edge cases:
  - Empty string: return `""`.
  - Single-character string: return `"x1"` for input `"x"`.
  - Strings with spaces: decide whether to compress across spaces or per word.

4) Corrected code snippets

Option A — fix loop bounds and handle tail after loop (explicit):

```python
def compress(s: str) -> str:
    if not s:
        return ''
    result = []  # use list for performance
    count = 1
    for i in range(len(s) - 1):  # iterate until second-last index
        if s[i] == s[i + 1]:
            count += 1
        else:
            result.append(f"{s[i]}{count}")
            count = 1
    # append the final run for the last character
    result.append(f"{s[-1]}{count}")
    return ''.join(result)
```

Explanation:
- `range(len(s) - 1)` iterates up to `len(s)-2`, so `s[i+1]` is safe.
- After the loop, the final character's run is appended using `s[-1]` and the current `count`.
- The function handles `''` (empty string) and single-character inputs.

Option B — iterate pairs with `zip` (idiomatic and safe):

```python
def compress(s: str) -> str:
    if not s:
        return ''
    result = []
    count = 1
    for a, b in zip(s, s[1:]):
        if a == b:
            count += 1
        else:
            result.append(f"{a}{count}")
            count = 1
    result.append(f"{s[-1]}{count}")
    return ''.join(result)
```

Explanation:
- `zip(s, s[1:])` pairs adjacent characters and naturally skips the last index overrun.
- Still requires appending the final character-run after the loop.

Option C — compress per word (if spec requires word-level compression):

```python
def compress_per_word(text: str) -> str:
    # compresses each word independently and preserves spaces
    def compress_word(w: str) -> str:
        if not w:
            return ''
        r, c = [], 1
        for a, b in zip(w, w[1:]):
            if a == b:
                c += 1
            else:
                r.append(f"{a}{c}")
                c = 1
        r.append(f"{w[-1]}{c}")
        return ''.join(r)

    return ' '.join(compress_word(w) for w in text.split(' '))
```

Explanation:
- Splits the string on spaces and compresses each token independently, preserving word boundaries.
- Useful if input is a sentence and you don't want runs that span spaces.

5) Additional notes and best practices

- Avoid mutating strings in tight loops; use a list and `''.join(...)` for better performance.
- Add unit tests covering empty, single-char, repeated, alternating, and space-separated strings.
- If the input can include Unicode grapheme clusters, consider normalizing and using a library that handles grapheme clusters rather than code points.
- Document behavior for whitespace and punctuation.

6) Example test cases

```python
assert compress("") == ""
assert compress("x") == "x1"
assert compress("aaabbc") == "a3b2c1"
assert compress("ab") == "a1b1"
assert compress_per_word("aa bb") == "a2 b2"
```

---

## Usage Notes for the Reviewer Prompt

- Paste the structured prompt (top section) into your LLM and include the buggy script if available.
- Ask the model to return results in Markdown and include corrected, runnable snippets.

---

## Where to add this file

Category: `developer/` — this prompt is intended for code review and debugging use cases.
