# Parallax Framework

**Parallax** is a modular and performance-focused framework for Garry's Mod, built for serious roleplay communities that want modern systems, clean structure, and high customization. Developed as a continuation and reimagining of previous projects, Parallax prioritizes long-term maintainability, gameplay flexibility, and developer accessibility.

## 🔧 What is Parallax?

Parallax is not just a gamemode, it's a full-featured development framework designed for roleplay experiences. Whether you're building a Half-Life universe server, a modern-day setting, or a completely original world, Parallax gives you the tools to bring it to life.

### Key Features

- 🔩 **Modular Architecture**  
  Built around isolated modules and libraries with low coupling and clear responsibilities.

- 🎮 **Custom UI Framework**  
  An immersive interface inspired by Valve’s Gamepad UI, tailored for roleplay.

- 📦 **Weight-Based Inventory**  
  Realistic inventory system with drag-and-drop interactions and item weight handling.

- 🔐 **Secure Networking**  
  Custom networking library using compression and encryption for efficient communication.

- 💾 **SQLite Integration**  
  Simple, powerful database tools to persist characters, items, logs, and more.

- 📚 **Clean Code Standards**  
  Enforced formatting style (K&R Lua + LDoc) with full documentation for maintainability.

## 🔍 Repositories

Parallax is divided into several repositories for better separation of concerns:

- [`parallax`](https://github.com/Parallax-Framework/parallax) — Core framework
- [`parallax-skeleton`](https://github.com/Parallax-Framework/parallax-skeleton) — Blank base schema for developers

> ⚠️ Some repositories are private while early development continues.

## 📦 Installing Parallax

1. Clone the core framework into your `garrysmod/gamemodes/` folder.
2. Clone or build a schema and place it within the same directory where the core framework is located.
   - The schema should be a separate folder, not a subfolder of the core framework.
   - The schema folder should contain a `gamemode` folder with the necessary files.
3. Ensure the schema folder is named appropriately (e.g., `parallax-skeleton`).
4. Ensure the core framework and schema are in the same directory.
5. Start Garry's Mod and select the schema from the menu if you are playing locally, or set the gamemode in your server configuration.

Example:
```
garrysmod/
└── gamemodes/
├── parallax/
└── parallax-skeleton/
```

## 👥 Who is this for?

- Server owners seeking modern RP features
- Developers who want a modular Lua codebase
- Communities looking for long-term support and quality-of-life improvements

## 🤝 Contributions

Contributions are welcome! Please follow our [style guide](https://github.com/Parallax-Framework/.github/blob/main/STYLE.md), and open a pull request when ready.

## 📜 License

Parallax is released under the MIT License. See the [LICENSE](LICENSE) file for more details.
