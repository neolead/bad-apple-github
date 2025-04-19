# GitHub Calendar Bad Apple Dance 🎵

![Bad Apple Demo](https://raw.githubusercontent.com/neolead/bad-apple-github/refs/heads/main/Bad_apple_github_mus.gif)

**Turn your GitHub profile into a musical spectacle!**

This project combines a built-in MIDI player and synthesizer with a visualization of the iconic "Bad Apple" dance on your GitHub contributions calendar. Watch as your calendar transforms into a dynamic canvas, syncing animations with music.

---

## Features

- **Built-in MIDI Player & Synthesizer**:  
  The script includes a custom MIDI player with multiple instruments (`marimba`, `piano`, `organ`) and supports ADSR envelopes for realistic sound synthesis.

- **Dynamic Calendar Animation**:  
  The GitHub contributions calendar is transformed into a pixel-art display, showcasing the "Bad Apple" animation frame by frame.

- **Customizable Palette**:  
  The color palette can be inverted or modified to match your preferences.

- **Seamless Integration**:  
  The script runs directly in the browser, leveraging the GitHub contributions calendar for a unique visual experience.

---

## How It Works

### MIDI Playback
- The script processes a sequence of MIDI notes (`notes` array) and assigns them to different instruments (`instruments` array).
- Each note is played with precise timing, velocity, and duration using the Web Audio API.
- Instruments are cycled through dynamically to create a rich, layered sound.

### Calendar Animation
- The GitHub contributions calendar is treated as a grid of pixels.
- Frames of the "Bad Apple" animation are pre-rendered as base64-encoded images.
- Each frame is mapped to the calendar grid, updating the background color of each cell to create a smooth animation.

### Text Overlay
- Before the main animation starts, the text "BAD APPLE" is displayed on the calendar using a monospace font.
- After 4 seconds, the calendar transitions to the main animation.

---

## Installation

### Prerequisites
- A modern web browser with support for the Web Audio API and JavaScript ES6+.
- Access to your GitHub profile page with a visible contributions calendar.

### Usage
1. Open your GitHub profile page in a browser.
2. Copy the entire script and paste it into the browser's developer console (F12 → Console tab).
3. Press Enter to run the script.

The animation will start immediately, and the MIDI synthesizer will play the "Bad Apple" theme.

---

## Technical Details

### MIDI Synthesizer
The synthesizer is implemented using the Web Audio API. Each instrument has the following properties:

- `oscType`: Oscillator type (`square`, `triangle`, `sawtooth`).
- `detune`: Fine-tuning in cents (+/- values).
- `octave`: Octave shift (positive or negative).
- `envelope`: ADSR envelope parameters (`attack`, `decay`, `sustain`, `release`).
- `amp`: Amplitude multiplier.

Example instrument configuration:

```javascript
{
  name: 'marimba',
  oscType: 'square',
  detune: 3, // +3 cents
  octave: -1, // Lowered by one octave
  envelope: { attack: 0.005, decay: 0.1, sustain: 0.2, release: 0.2 },
  amp: 0.3
}
```

### Calendar Animation
- The calendar grid is treated as an 18x14 pixel canvas.
- Each frame of the animation is encoded as a base64 image and rendered on the canvas.
- Pixel colors are mapped to the GitHub contributions palette (`#ebedf0`, `#9be9a8`, etc.).

### Text Display
- The text "BAD APPLE" is rendered on a hidden canvas using a monospace font.
- The text is then mapped to the calendar grid, ensuring proper alignment and visibility.

---

## Customization

You can modify the following variables to customize the behavior:

- `palette`: Change the color scheme of the calendar.
- `invertPalette`: Reverse the color order.
- `FPS`: Adjust the animation frame rate.
- `DELAY`: Set the delay between frames.
- `OFFSET`: Shift the animation horizontally.

Example:

```javascript
const palette = ['#ffffff', '#cccccc', '#999999', '#666666', '#000000'];
const invertPalette = true;
const FPS = 24; // Increase frame rate
```

---

## Acknowledgments

Special thanks to the open-source community for their contributions to Web Audio API and GitHub customization projects.

---

## License

This project is licensed under the GPLOverfuck License. Feel free to use, modify, and share it as you wish!

---

Enjoy the show! 🎶✨
