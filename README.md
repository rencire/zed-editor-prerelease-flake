# About
This is a flake to 


# Quickstart

Import flake into your flake:

e.g. flakelight flake.nix
```nix
{
  inputs.nixpkgs.url = "github:NixOS/nixpkgs/nixpkgs-unstable";
  inputs.flakelight.url = "github:accelbread/flakelight";
  inputs.zed-editor-pre.url = "github:rencire/zed-editor-prerelease-flake";

  outputs =
    { flakelight, ... }@inputs:
    flakelight ./. {
      inherit inputs;
      devShell = pkgs: {
        packages = with pkgs; [
          # Add zed-editor package here
          inputs'.zed-editor-pre.packages.default
        ];
      };
    };
}

```


  
