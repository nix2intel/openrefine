# OpenRefine Nix Flake

This Nix flake provides a package for [OpenRefine](https://openrefine.org/), a powerful tool for working with messy data: cleaning it, transforming it from one format into another, extending it with web services, and linking it to databases.

## Credits

- The [OpenRefine project](https://openrefine.org/) for creating and maintaining this incredible tool.
- [Robert Scott](mailto:code@humanleg.org.uk) for maintaining the OpenRefine Nix package.

## Prerequisites

To use this flake, you'll need to have Nix installed with flake support enabled. See the [Nix installation guide](https://nixos.org/download.html) and [Nix flakes wiki page](https://nixos.wiki/wiki/Flakes) for more information.

## Usage

### Building

To build the OpenRefine package:

```bash
nix build
```

The built package will be symlinked to ./result.

### Running

To run OpenRefine directly:

```bash
nix run
```

This will start OpenRefine using the packaged version.

### Developing

To enter a development environment with OpenRefine available:
```
nix develop
```

This will drop you into a shell with OpenRefine in PATH, ready for hacking.

### Troubleshooting

If the build fails due to OpenRefine being marked as broken in nixpkgs, you can try one of the following:

- Set the NIXPKGS_ALLOW_BROKEN=1 environment variable before running Nix commands (note: for Nix flake commands like nix build, you must also pass --impure).
- Add { nixpkgs.config.allowBroken = true; } to your NixOS configuration.
- Add { allowBroken = true; } to your user Nix configuration (~/.config/nixpkgs/config.nix).
