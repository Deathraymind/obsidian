- okay so i think if i run
- ```bash 
  nix-store --import > bowos.nar 
  ```
- Then i run a command such as
- ```bash
  nixos-install --impure --flake .#nixos
  ```
- Then it sould pull from the .nar repository that i imported into the isos store