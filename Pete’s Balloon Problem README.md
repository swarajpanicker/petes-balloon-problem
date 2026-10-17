# Pete’s Balloon Problem 🎈

A funny, family-friendly twist on hangman. Pete is floating above a pool of pudding, held up by balloons. Every wrong guess pops one. Guess the word before he takes a dip.

The whole game is one self-contained HTML file with no build step and no dependencies.

## How to play

1. Pick a **theme** and a **danger level**.
2. Press **Launch Pete**.
3. Guess letters using the on-screen keyboard or your physical keyboard.
4. Right letters fill in the word. Wrong letters pop a balloon and Pete sinks lower.
5. Reveal the whole word to win. Lose every balloon and Pete becomes dessert.

You can use the **Hint** button to reveal a random letter. It costs one balloon, and it is disabled when only one balloon is left.

## Themes

| Theme | Vibe |
| --- | --- |
| 🍕 Snack Attack | Food, glorious food |
| 🦦 Weird Wildlife | Animals, from sloths to hippopotamuses |
| 🚀 Cosmic Nonsense | Planets, rockets and astronomy |
| 📎 Corporate Chaos | Office jargon and meeting culture |
| 🐉 Dragons & Drama | Fantasy creatures and magic |

Each theme has roughly 40 words. The game cycles through every word for your chosen theme and difficulty before repeating any.

## Difficulty levels

| Level | Balloons | Word length |
| --- | --- | --- |
| 😎 Chill | 8 | 6 letters or fewer |
| 🌶️ Spicy | 6 | 7 to 8 letters |
| 🤯 Unhinged | 4 | 9 letters or more |

## Features

- Animated SVG scene. Pete gradually sinks, his face changes mood as balloons pop, and he wears a crown if you win.
- Funny commentary from Pete after every guess, win and loss.
- Sound effects built with the Web Audio API, with a mute toggle.
- Confetti celebration on a win.
- Session scoreboard showing wins, losses and a win streak.
- Automatic light and dark appearance based on your device setting.
- Responsive layout that works on phones, tablets and desktops.

## Accessibility

- Full keyboard play, with visible focus outlines.
- The commentary bubble is an `aria-live` region, so screen readers announce updates.
- Animations and transitions are turned off when the system’s “reduce motion” setting is on.

## Running it

Open `petes-balloon-problem.html` in any modern browser. No server needed.

An internet connection is only used to load the Fredoka font from Google Fonts. Without it, the game falls back to a system font.

## Customizing

Everything lives in the `<script>` block of the HTML file.

**Add or change words.** Each theme in the `THEMES` object has a `w` property, which is a space-separated list of uppercase words. Letters only, with no spaces or hyphens:

```js
food:{ n:"Snack Attack", e:"🍕", t:"Calories not included",
  w:"PIZZA TACO BAGEL ...".split(" ") }
```

Words are sorted into difficulty levels automatically by length, so add a few of each length to keep every level stocked.

**Add a theme.** Add a new entry to `THEMES` with a name (`n`), emoji (`e`), tagline (`t`) and word list (`w`). It shows up on the setup screen automatically.

**Tune difficulty.** Edit the `DIFFS` object to change the balloon count (`lives`) or the word-length rule (`ok`).

**Change Pete’s jokes.** Edit the `LINES` object. Each key holds an array of messages and one is picked at random.

## Project structure

```
petes-balloon-problem.html   # markup, styles and game logic in one file
README.md
```

## Tech notes

- Plain HTML, CSS and vanilla JavaScript.
- The scene is redrawn as inline SVG on each frame of the sinking animation.
- The page is hosted as a static file, so any static host will do.

## License

Add your preferred license here.