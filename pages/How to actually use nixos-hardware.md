- #beanmachine #nixos
- # Question
	- How do you actually use [nixos-hardware](https://github.com/NixOS/nixos-hardware)?
- # Context
	- I'm using this specifically for the [[beanmachine]], my Framework 16 laptop
	- My [[NixOS]] configuration has [[flakes]] enabled, which I think is necessary to use nixos-hardware but I'm not sure. You should probably be using flakes anyway.
- # Answer
	- You need to add nixos-hardware as an input to your `flake.nix`:
		- ```nix
		  inputs = {
		    nixos-hardware.url = "github:NixOS/nixos-hardware";
		  }
		  ```
	- You then need to include it in the outputs and then select the right "module". You can search for the correct name of the module by looking through the [flake.nix](https://github.com/NixOS/nixos-hardware/blob/master/flake.nix). Mine is `framework-16-7040-amd`
		- ```nix
		  outputs = inputs@{ nixpkgs, nixos-hardware, ... }: {
		  	nixosConfigurations.beanmachine = nixpkgs.lib.nixosSystem {
		      	modules = [
		          	nixos-hardware.nixosModules.framework-16-7040-amd
		          ]
		      }
		  }
		  ```
	- In case you're still new to NixOS, this is not a minimum viable configuration. Your modules for your system should also include your configuration.nix and possibly some other things like [[home-manager]]
- # See also
	- [This commit](https://github.com/UvixCreative/beanlaptop/commit/0ab5c00ba2dd0c32698c581a29ca7f534faecf51#diff-206b9ce276ab5971a2489d75eb1b12999d4bf3843b7988cbe8d687cfde61dea0) where I added nixos-hardware to my own NixOS configuration. And also changed some other things because I'm bad at Git.