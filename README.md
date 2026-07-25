SAFe & SOUND: Agile Release Trivia

A real-time multiplayer quiz game for SAFe POPM training. The trainer hosts the game on a projector, participants join on their phones by scanning a QR code, and everyone plays together: synced countdowns, speed-based scoring, streak bonuses, a live leaderboard, and a podium finale with confetti.

Built by BARY with Love for the Wavestone London POPM Training in July 2026.

How it works

The host picks one of five lesson "stations", each themed as a stop on a neon release train:

Mindset Central (L1): roles, responsibilities, value streams, and AI fundamentals
WSJF Junction (L2): PI Planning preparation, features, vision, roadmaps, and prioritization
Planning Platform (L3): leading PI Planning, PI objectives, dependencies, and risks
Iteration Station (L4): stories, estimating, iteration events, and flow
Inspect & Adapt Terminal (L5): syncs, System Demo, the IP iteration, I&A, and responsible AI

Each lesson has a pool of 30 exam-style questions. Every game deals 10 at random, so the game can be replayed without repeats feeling stale. Answers score up to 1000 points scaled by speed, plus a streak bonus for consecutive correct answers. A commentary engine (the Conductor) reacts to what actually happened each round.

Playing

Host: open the site, choose "Drive the Train", pick a lesson, and share the QR code or the four-letter game code shown in the lobby. Start when everyone is aboard.

Players: scan the QR or open the site and choose "Board a Game", enter the code, pick a name and a travel badge, and answer on your phone. Late joiners can hop on at any point, and a page refresh puts you back in the game with your score intact.

Comfortably supports a full classroom of 15+ players.

Tech
One self-contained index.html. No build step, no dependencies to install.
Firebase Realtime Database keeps everyone in sync. The host is the single source of truth: it deals the questions, runs the clock, and computes all scores.
Hosted on GitHub Pages.
Sound effects are synthesized in the browser, so there are no audio files to load.
Respects reduced-motion settings and works on phones, laptops, and projectors.
Setup
Create a Firebase project with a Realtime Database and publish the database rules found in the comment block at the top of index.html.
Put your Firebase configuration in the clearly marked block near the top of the script in index.html. The databaseURL must match your database region.
Serve index.html from GitHub Pages (Settings, then Pages, deploy from branch, main, root).

Full step-by-step instructions live in the comment block at the top of index.html.

Testing

In the lobby, the host can press the B key to add 15 bots that answer with random speed and accuracy. Run a full game with bots before using it in class to see the leaderboard and final screen under a realistic load.

Troubleshooting

Tap the version tag in the bottom corner to open the debug panel. It shows the live game state and a timestamped log of any errors (connection problems, timeouts, and so on), with a copy button. Every network call has a visible timeout, and the status bar shows a live connection indicator at all times.
