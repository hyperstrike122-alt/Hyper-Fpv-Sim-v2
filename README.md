The Hyper FPV Sim

A lightweight FPV drone simulator that runs in your browser, a good fit for older or low-end PCs. It's a single HTML file with no install and no heavy downloads. Fly racing and freestyle quads in first person through 20 maps, with a flight model built from real quadcopter behaviour (mass, thrust, drag), Betaflight-style rates, gamepad and radio support, and latency simulation.

No install, no build step. Open index.html in a browser. It uses three.js (r128), loaded from the cdnjs CDN, so you need an internet connection the first time.

Features

Game modes

Race: fly gates against the clock. Choose 1, 3, 5, 10, or infinite laps, or enter your own. Best lap is saved per track. Some tracks are point-to-point.
Freestyle: no timer. Fly free, dive buildings, and hit gates your own way.

14 drones, from a 22 g micro whoop to a 2.6 kg heavy lifter

Class	Drones
Whoops	Micro Whoop 65, Tiny Whoop, Whoop 75 Brushless
3" / 3.5"	Toothpick 3", Freestyle 3.5", Cinewhoop 3.5"
5" / 6"	Racer 5", Sprint 5" Race, Freestyle 5", Cruiser 5" (slower), Bando 6"
Big	Cinelifter 7", Long Range 7", Heavy Lifter 10"

20 maps (11 race, 9 freestyle): parks, a figure eight, canyons and mesas, night city circuits and rooftops, pine forests, a stadium, a harbor, a concrete skate plaza, a wind farm, a quarry, and more. Maps have different lighting: day, sunset, dawn, mist, and night.

Flight model

Thrust follows a prop-style throttle curve, so hover is not at mid-stick (about 25% on a racer, higher on a whoop).
Drag comes from real physics: 0.5 · ρ · CdA · v² / mass. The drag area changes with attitude, depending on whether air hits the frame edge or the props.
Thrust fades as air flows up through the props, which limits top speed.
Added weight: add 0 to 400 g of payload. It lowers the thrust ratio, slows response, adds drag area, and lowers the crash speed.
Motors spool up faster than they spin down, and there is propwash wobble when you drop through your own prop wash at low throttle.
Heavy drones carry momentum. Light drones are slowed hard by the air.
Three flight modes: Angle, Horizon, and Acro.
Betaflight-style rates (RC rate, super rate, expo) that you can edit per drone.
Selectable gravity: real (9.81 m/s²) or the earlier version's 9.0.
Crashes depend on impact speed and weight. Light drones survive harder hits, and gentle touches bounce instead of crashing. Crashing can be turned off.

Latency simulation: control lag, video lag, and jitter (each adjustable, with None / Analog / Digital / Bad link presets).

Other

Procedural 4-motor engine sound and synthwave music, with no audio files.
Adjustable FOV and camera tilt.
Change drone, weight, FOV, drag, gravity, and latency mid-flight from the menu (Esc).
Settings, mappings, rates, and best laps are saved in the browser.
Controls

Keyboard

Key	Action
W / S	Throttle up / down (springs back to hover)
Arrow keys or I J K L	Pitch and roll
A / D	Yaw
Shift	Fine control
M	Cycle Angle / Horizon / Acro
C	Camera tilt
N	Music on / off
R	Reset
Esc	Controls and flight menu

Gamepad / FPV radio: pick a controller in the menu, map each axis (with Detect and invert), and choose a preset (Gamepad, Radio AETR, Radio TAER). Deadzone is adjustable. The throttle is the real stick position, and you lower it to arm after each reset. If a radio isn't listed, move a stick once and set the radio to USB joystick mode.

Running it
Download or clone the repo.
Open index.html in a modern desktop browser (Chrome, Edge, or Firefox work well).

To host it on GitHub Pages, go to Settings → Pages and deploy from the main branch.

Tech
One HTML file with all JavaScript and CSS inline
three.js r128 (cdnjs)
Web Audio API for sound and music
Gamepad API for controllers
Procedural geometry, textures and audio, with no external assets
Notes

This is an independent project. The flight model is based on general quadcopter physics and is not a copy of any other simulator.
