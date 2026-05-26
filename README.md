# Glass Video Player 🎥✨

A premium, highly interactive iOS-style React video player component featuring glassmorphism design, native mobile gestures, keyboard shortcuts, custom volume/brightness sliders, and speed controls.

---

## Key Features 🚀

- **Glassmorphism UI:** Translucent layout that fits elegantly over any video background.
- **Mobile Touch Gestures:**
  - **Horizontal Swipe:** High-fidelity touch scrubbing/seeking with live feedback.
  - **Vertical Swipe:** Left-side swipe controls brightness; right-side swipe controls volume (similar to VLC or native iOS video players).
- **Double Tap / Click Actions:** Easy double-tap to enter/exit fullscreen or play/pause the video.
- **Custom Elastic Sliders:** A custom fluid progress bar and volume slider using Spring Physics (`motion/react`).
- **Keyboard Shortcuts:**
  - `Space` or `K`: Play / Pause.
  - `ArrowLeft` / `ArrowRight`: Seek backward/forward 10 seconds.
  - `M`: Toggle mute.
  - `F`: Toggle Fullscreen.
  - `Esc`: Close the player.
- **Speed Controller:** Live playback speed customization (0.5x, 1x, 1.5x, 2x).

---

## Tech Stack 🛠️

- **Core:** [React](https://react.dev/) (compatible with React 18 & 19)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **Animations:** [Motion / Framer Motion](https://motion.dev/)
- **Icons:** [Lucide React](https://lucide.dev/)

---

## Installation 📦

1. Copy the files under `src/components/` into your React project:
   - `src/components/AppleVideoPlayer.jsx`
   - `src/components/ElasticSlider.jsx`
   - `src/components/Forward10Icon.jsx`
   - `src/components/Rewind10Icon.jsx`
   - `src/components/player/` (all context, hooks, UI elements and utilities)

2. Install the required peer dependencies in your project:
   ```bash
   npm install motion lucide-react
   ```

3. Ensure Tailwind CSS is configured in your project.

---

## How to Use 💻

Import `MarsPlayer` (exported from `AppleVideoPlayer.jsx`) and pass the video URL or local file source.

### Basic Example

```jsx
import React, { useState } from "react";
import MarsPlayer from "./components/AppleVideoPlayer";

export default function App() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div className="flex flex-col items-center justify-center min-h-screen bg-neutral-900 text-white">
      <button 
        onClick={() => setIsOpen(true)}
        className="px-6 py-3 bg-blue-600 hover:bg-blue-500 rounded-full font-bold transition-all shadow-lg"
      >
        Open Premium Player
      </button>

      {isOpen && (
        <MarsPlayer
          videoUrl="https://your-s3-bucket.s3.amazonaws.com/your-video.mp4"
          title="Neural Odyssey - MARS AI"
          onClose={() => setIsOpen(false)}
        />
      )}
    </div>
  );
}
```

---

## Component API 📖

### `<MarsPlayer />` (default export from `AppleVideoPlayer.jsx`)

| Prop | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `videoUrl` | `string` | `undefined` | The source URL of the video (supports AWS S3, Cloudfront, local files, etc.). |
| `src` | `string` | `undefined` | Alternative prop for the video source. |
| `title` | `string` | `""` | The title displayed at the top bar of the player. |
| `onClose` | `function` | `undefined` | Callback function triggered when the user clicks the close button (`X`) or presses `Escape`. |

---

## Custom CSS / Tailwind Requirements 🎨

Make sure your `tailwind.config.js` or CSS layout handles absolute positions and blur effects correctly. The player makes heavy use of:
- `backdrop-blur-2xl` and `backdrop-blur-xl`
- `bg-white/5` and `bg-black/65`
- Flexbox layouts with absolute positioning for overlays.

---

## License ⚖️

> **⚠️ This software is proprietary. All rights reserved.**

This component is **NOT open-source**. The source code is publicly visible for evaluation purposes only.

**You may NOT:**
- ❌ Use this component in any project without purchasing a license.
- ❌ Copy, fork, or redistribute the code.
- ❌ Create derivative works for distribution.

**You MAY:**
- ✅ View and study the source code for learning purposes.
- ✅ Purchase a commercial license to use it in your projects.

### 💰 Purchase a License

For pricing and licensing inquiries, contact:
- **GitHub:** [@syrinedev-06](https://github.com/syrinedev-06)

See the full [LICENSE](./LICENSE) file for details.
