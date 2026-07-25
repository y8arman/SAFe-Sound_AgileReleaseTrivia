SAFe & SOUND: Agile Release Trivia

A real-time multiplayer quiz game for SAFe POPM training. The trainer hosts the game on a projector, participants join on their phones by scanning a QR code, and everyone plays together: synced countdowns, speed-based scoring, streak bonuses, an animated live leaderboard, and a podium finale with fireworks and medals.

Built by Yusuf Barman (BarY) with Love for the Wavestone London POPM Training in July 2026.

How it works

The host picks one of five lesson "stations", each themed as a stop on a neon release train:

Mindset Central (L1): roles, responsibilities, value streams, and AI fundamentals
WSJF Junction (L2): PI Planning preparation, features, vision, roadmaps, and prioritization
Planning Platform (L3): leading PI Planning, PI objectives, dependencies, and risks
Iteration Station (L4): stories, estimating, iteration events, and flow
Inspect & Adapt Terminal (L5): syncs, System Demo, the IP iteration, I&A, and responsible AI

Each lesson has a pool of 30 exam-style questions. The host chooses the journey length (5, 10, or 15 stops) and the game deals that many questions at random, so every run is different.

Scoring

A correct answer scores between 500 points (at the buzzer) and 1000 points (instant), so speed matters. Every consecutive correct answer beyond the first adds a +100 streak bonus, capped at +500. On the final stop, all points pay double, announced by a klaxon and a warning banner, so comebacks stay possible until the very end.

After every question, players see whether they were right, the correct answer in full, and what they picked, so the game teaches while it entertains. The Conductor comments on each round: fastest fingers, hot streaks, photo finishes, and last-second saves.

Playing

Host: open the site, choose "Drive the Train", pick a journey length and a lesson, and share the QR code or the four-letter game code (tap the code to enlarge it for the projector). Start when everyone is aboard. After the last leaderboard, hit Celebrate for the podium, medals, and fireworks, then end the celebration to reveal the full passenger manifest and the Class Report: hardest question, sharpest fingers, longest streak, and overall class accuracy.

Players: scan the QR or open the site, choose "Board a Game", enter the code, pick a name and a travel badge, and answer on your phone, tablet, or laptop. Late joiners can hop on at any point, and a page refresh puts you back in the game with your score intact. Your final screen shows your placement plus your personal journey stats.

Practice solo: anyone can also pick "Practice solo" on the start screen for a self-paced run through any lesson, with instant feedback and the correct answer shown after every question. No host needed, works entirely on your own device.

Comfortably supports a full classroom of 15+ players.

Tech
One self-contained index.html. No build step, no dependencies to install.
Firebase Realtime Database keeps everyone in sync. The host is the single source of truth: it deals the questions, runs the clock, and computes all scores.
Hosted on GitHub Pages.
All sound is synthesized in the browser, including the ambient rolling-train loop on the host screen. The speaker button in the status bar mutes everything and remembers your choice.
Respects reduced-motion settings and works on phones, laptops, and projectors.
Setup
Create a Firebase project with a Realtime Database and publish the database rules found in the comment block at the top of index.html.
Put your Firebase configuration in the clearly marked block near the top of the script in index.html. The databaseURL must match your database region.
Serve index.html from GitHub Pages (Settings, then Pages, deploy from branch, main, root).

Full step-by-step instructions live in the comment block at the top of index.html.

Testing

In the lobby, the host can press the B key to add 15 bots that answer with random speed and accuracy. Run a full game with bots before using it in class to see the leaderboard and final screen under a realistic load.

Troubleshooting

Tap the version tag in the bottom corner to open the debug panel. It shows the live game state, a phase history, the age of the last update from the server, and a timestamped error log where every entry carries a code (E01 through E28) that pinpoints what failed, from a missing database connection to a blocked storage API. The tag itself shows a red badge whenever errors have been caught, and "Copy log" puts the full diagnosis on the clipboard. Every network call has a visible timeout, and the status bar shows a live connection indicator at all times.
