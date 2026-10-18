# Lab Timer & Practice Tracker

# Problem

A lab instructor wants a small screen where students can track how many practice
problems they have solved and how long they have been working.

# Approach

- **LabScreen** (parent) owns the shared state: `solved` and `isRunning`
  (both with `useState`). It also calls the custom hook `useStopwatch`.
- **PracticeTracker** displays the solved count with "Solve +1" and "Reset"
  buttons, and shows "Great job!" (conditional rendering) once solved reaches 5.
- **Stopwatch** displays the elapsed time (mm:ss) and "Running..." or "Paused"
  based on `isRunning`.
- **useStopwatch(isRunning)** is a custom hook that uses `useState` for seconds
  and `useEffect` with `setInterval`. Its cleanup function (`clearInterval`)
  runs when `isRunning` changes and when the component unmounts.
- State is lifted to LabScreen so the sibling components PracticeTracker and
  Stopwatch stay in sync through their shared parent.

## How to Run in Expo Go

1. Install dependencies: `npm install`
2. Start the app: `npx expo start`
3. Scan the QR code with Expo Go on your phone (same Wi-Fi), or press `w` to
   open it in the browser.
