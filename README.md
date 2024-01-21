
- Enable flakes in your default configuration.nix by adding this:

```
# Enable Flakes and the new command-line tool
nix.settings.experimental-features = [ "nix-command" "flakes" ];
```

This file should be located at /etc/nixos/configuration.nix

- Ensure you have Git listed in your pkgs in the configuration.nix.
- Rebuild your system.
- Clone this repo.
- Then go into repo folder (stay in this folder)
- Change username, hostname, theme, and any other variables you may want under user information in flake.nix
- Ensure you have selected the proper profile in the flake as well. I use amd-desktop.
- Generate your hardware.nix like so:

```
nixos-generate-config --show-hardware-config > hardware.nix
```

- Run this command:

```
sudo nixos-rebuild switch --flake .
```

Now when you want to rebuild the configuration you have access to an alias called flake-rebuild that will rebuild the flake based of the flakeDir variable you set in flake.nix!

