tags:: issue, beanmachine, NixOS, swayidle, home-manager
issue-status:: Solved
solved-date:: 2024-05-09

- # Problem
	- Lid close does not lock
	- Timeouts don't work
- # Research
	- `swayidle` man pages
	- `services.swayidle` options in [home-manager option search](https://home-manager-options.extranix.com/?query=swayidle&release=master)
	- `logind` man pages and NixOS Options search
- # Troubleshooting
	- Looked at `systemctl --user edit --full swayidle.service` to see the full command being added
- # Solution
	- For lid close, I used the [logind options](https://search.nixos.org/options?channel=unstable&from=0&size=50&sort=relevance&type=packages&query=services.logind) to set `lidSwitch` and `lidSwitchExternalPower` to lock
	- For timeouts, I had to [change to absolute paths](https://github.com/UvixCreative/beanlaptop/commit/f0f82bdfdbf342b4f4d0b75dbcdb92168ea76611) for binaries (e.g. `/nix/store/jfaiowefjaweio-swaylock/bin/swaylock` instead of just `swaylock`)