**Modes:**

- **Command Mode:** Press `esc` to enter. Use single key commands for navigation, editing, and file operations.
- **Insert Mode:** Press `i`, `a`, or `o` to enter. Type text normally. Press `esc` to return to Command Mode.

**Movement:**

- **h, j, k, l:** Move left, down, up, right (one character)
- **H, M, L:** Move to top, middle, bottom of screen
- **0 (zero):** Move to beginning of line
- **$:** Move to end of line
- **n, N:** Find next/previous occurrence of current word
- **b, B:** Move to beginning/end of word
- **G:** Go to specific line number (e.g., `G10`)
- **gg:** Go to the very beginning of file
- **Ctrl-f, Ctrl-b:** Page forward/backward

**Editing:**

- **x:** Delete current character
- **X:** Delete current line
- **d:** Delete (repeat for more characters/lines)
- **dw, de:** Delete word or to end of word
- **yy, yank:** Copy current line
- **p:** Paste copied text
- **r:** Replace current character with new character
- **c:** Change (replace) text (e.g., `cw` to change word)
- **I:** Enter Insert Mode at beginning of line
- **A:** Enter Insert Mode at end of line
- **o:** Enter Insert Mode below current line

**Saving and Quitting:**

- **:w (write):** Save changes
- **:wq (write & quit):** Save changes and quit
- **:q (quit):** Quit without saving (may prompt)

**Other:**

- **:set nu (number):** Show line numbers
- **/, ?:** Search forward/backward for text
- **!:command:** Run shell command

**Remember:**

- `esc` is your escape key in Command Mode.
- Most commands can be prefixed with a number for repetition (e.g., `3dd` deletes 3 lines).
- Explore `:help` for more advanced commands and options.