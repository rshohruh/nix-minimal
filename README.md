# 🌟 My NixOS Configuration minimal config
## 📂 Directory Structure
This repository contains my NixOS configuration files structured for use with flakes and Home Manager. The directory structure is as follows:
```
.
├── flake.nix
├── flake.lock
├── home-manager
│   └── home.nix           # Main Home Manager configuration file
└── nixos
    ├── configuration.nix   # Main NixOS system configuration file
    └── hardware-configuration.nix # Hardware-specific configurations
```
## 📄 Important Files
- `flake.nix`: The entry point for managing the configuration and its dependencies.
- `home.nix`: The main Home Manager configuration file, where user-specific packages and settings are managed.
- `configuration.nix`: The main NixOS system configuration file for managing system-wide settings.
- `hardware-configuration.nix`: Contains hardware-specific configurations generated during installation.

## 🛠️ Managing Packages with Home Manager

### ➕ Adding Packages
All user-specific packages are installed through Home Manager. To add a new package, you can update the `home.nix` file.

For example, to install `htop`, follow these steps:

1. Open the `home.nix` file.
2. Add the desired package to the `home.packages` list. Here’s how to include htop:

```nix
# home-manager/home.nix

{
  ...
  home.packages = with pkgs; [
    # Existing user packages
    ...
    htop   # Add your desired package here
  ];
  ...
}
```
3. After making changes, run the following command to apply them:
```bash
home-manager switch --flake .#rshohruh@nixos
```
## 💡 Tips
- **Installing New Packages**: Whenever you want to install a new package, just add it to the `home.packages` list in your Home Manager configuration file.
- **Modular Configuration**: Feel free to create additional configuration files to keep your setup organized. Import these files in `home.nix` to include their settings.
- **Be Aware**: Always ensure that any hardware-specific settings are defined in the `hardware-configuration.nix` file and referenced correctly in your NixOS configuration.

- 🙏 Thanks
Special thanks to the owner of the [Nix Starter Configs](https://github.com/Misterio77/nix-starter-configs/tree/main) repository for providing a great template that helped in setting up this configuration! 🎉

## 📜 License
This repository is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.