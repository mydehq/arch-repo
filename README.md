<div align="center">
    <img src="./src/icon.png" alt="MyTM" width="80">
    <h1>Arch Repo</h1>
    <p>
        <b>Automated AUR package building and repository hosting.</b>
    </p>
</div>

<br />


## Installation

- Add the repo to `pacman.conf`:

    ```sh
    sudo bash -c 'printf "\n[mydehq]\nSigLevel = Optional TrustAll\nServer = https://mydehq.github.io/arch-repo/\$arch\n" >> /etc/pacman.conf'
    ```

- Sync the database:

   ```sh
    sudo pacman -Sy
   ```

## Adding Packages in repo

Simply edit `packages.yml` and add desired AUR package names:

```yml
packages:
  - name: myctl
  - name: vicinae-bin
  - name: catppuccin-cursors-macchiato
```
The GitHub Action will automatically detect changes, build the packages, update the repository index, and regenerate the dashboard.

---

## Repository Structure

```text
arch-repo/
├── src/
│   ├── builder              # Core build logic & site generator
│   └── index.html.tpl       # PC-Optimized Dashboard template
├── packages.yml             # Declarative package list
├── .github/
│   └── workflows/
│       └── build.yml        # Automation pipeline
└── README.md
```

## Technical Specification

- **Build Environment**: Native Arch Linux (`archlinux:latest`) container.
- **Build Logic**: Uses `makepkg` with dependency handling.


## Related Resources

- **Main Repository**: [mydehq/MyDE](https://github.com/mydehq/myde)
- **Wiki Repository**: [mydehq/MyWiki](https://github.com/mydehq/mydehq.github.io)


---

<div align="center">
    <b>Made with ❤️ by the <a href="https://github.com/mydehq">MyDE Team</a></b>
</div>
