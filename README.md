
# Adobe Illustrator CC 2017 (v17) for Linux via Wine

![Adobe Illustrator CC Logo](illustrator.png)

> **Professional-grade vector design on Linux**  
> A repackaged version of Adobe Illustrator CC 2017 optimized for Linux with Wine integration.

---

## 🚀 Features
- **Native-like Performance**  
  Pre-configured Wine prefix with performance tweaks
- **Dark Mode Support**  
  Auto-configured Yaru dark theme (modifiable)
- **One-Click Launch**  
  Desktop entry + CLI command (`illustrator-cc`)
- **Dependency Automation**  
  Installs required components (VC++ 2013, corefonts)
- **Isolated Environment**  
  Dedicated Wine prefix in `/opt/illustratorCC`

---

## 📥 Installation

### Prerequisites
- Arch Linux (or derivatives with AUR support)
- Base-devel package group

### Steps
```bash
# Clone the repository
git clone https://github.com/yourusername/illustrator-cc-wine.git
cd illustrator-cc-wine

# Build and install
makepkg -si
```
# Post-install setup (automatic)
# - Wine prefix initialization
# - Dependency installation
# - Permission fixes


---

## 🛠️ Technical Details
| Category       | Specification                  |
|---------------|-------------------------------|
| **Package**   | `illustrator-cc-wine`         |
| **Version**   | 17 (CC 2017)                  |
| **Arch**      | x86_64                        |
| **Wine**      | Win64 prefix                  |
| **Deps**      | wine, winetricks, lib32-*     |

---

## 🖥️ Usage
### CLI Launch
```bash
illustrator-cc
```

### Desktop
Search for "Illustrator CC" in your application menu.

---

## ⚠️ Legal & Licensing
**Important**: This package **does not** include Adobe Illustrator. You must:
1. Own a legal copy of Illustrator CC 2017
2. Comply with [Adobe's EULA](https://www.adobe.com/legal/terms.html)
3. Provide your own `IllustratorCC64.exe`

This project only provides:
- Wine configuration
- Linux integration scripts
- Packaging infrastructure

---

## ❓ FAQ
### Q: Why version 17 specifically?
A: CC 2017 has the best Wine compatibility balance between features and stability.

### Q: How to enable GPU acceleration?
```bash
winetricks -q vkd3d
```

---

## 🌍 Contributing
Pull requests welcome for:
- [ ] Improved Wine configurations
- [ ] Better HiDPI support
- [ ] Additional distro compatibility

Report issues for:
- Crashes with specific tools
- Installation problems
- Performance bottlenecks

---

## 📜 License
See [LICENSE](LICENSE) for packaging terms.  
Adobe software requires separate legal acquisition.

## 📬 Contact
- Email: miladalizade8282@gmail.com  
- Telegram: [@miladalizadw](https://t.me/miladalizadw)
