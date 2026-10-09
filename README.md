# Analog Clock

A real-time **analog clock** built with HTML, CSS and a few lines of vanilla JavaScript.

**Live demo:** https://rexhinokovaci.github.io/Analogtime/

## How it works

- The clock face, the 12 hour numerals and the hour/minute/second hands are drawn with CSS (rounded borders, absolutely positioned elements), with no images or canvas.
- `index.js` runs `updateClock()` once a second. It reads the current time, works out each hand's fraction of a full turn, and applies a CSS `rotate()` transform:

```js
const sec  = date.getSeconds() / 60;
const min  = (date.getMinutes() + sec) / 60;   // minute hand moves smoothly between minutes
const hour = (date.getHours() + min) / 12;     // hour hand moves smoothly between hours
secDiv.style.transform = `rotate(${sec * 360}deg)`;
```

Because the minute and hour hands take the smaller units into account, they sweep gradually like a real clock instead of jumping.

## Tech stack

HTML, CSS and vanilla JavaScript. No dependencies and no build step. Hosted on GitHub Pages.

## Running locally

Open `index.html` in any browser.

---

Built by [Rexhino Kovaci](https://github.com/rexhinokovaci) — DevOps & AI engineer in Tirana, Albania. Need an app built? [Get in touch](mailto:kovacirexhino@gmail.com).
