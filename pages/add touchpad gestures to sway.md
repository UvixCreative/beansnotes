tags:: issue, nixos, beanmachine, sway
issue-status:: Research

- # Problem
	- Add touchpad gestures to sway:
		- 3-finger left/right: next/prev workspace
		- 3-finger up/down: volume up/down(?)
		- 4-finger up/down: brightness up/down(?)
	-
- # Research
	- ```
	  # man 5 sway
	  
	  bindgesture [--exact] [--input-device=<device>] [--no-warn] <gesture>[:<fingers>][:directions] <command>
	             Binds gesture to execute the sway command command when detected. Currently supports the hold, pinch or swipe gesture. Optionally can be limited to bind to a certain number of fingers or, for a pinch or swipe gesture, to certain directions.
	  ```
- # Troubleshooting
	-
- # Solution
	-