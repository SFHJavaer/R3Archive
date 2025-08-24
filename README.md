# R3nzSkin - League of Legends Skin Changer

<div align="center">

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/SFHJavaer/R3Archive)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](https://www.microsoft.com/windows)
[![C++](https://img.shields.io/badge/C%2B%2B-17-blue)](https://isocpp.org/)

*A powerful skin modification tool for League of Legends*

[English](README.md) | [中文](README_zh.md)

</div>

---

## 📖 Project Overview

R3nzSkin is a powerful skin modification tool specifically designed for League of Legends. Through memory injection and hooking techniques, it enables real-time skin switching and customization within the game. The project includes a complete injector, configuration management system, and user-friendly graphical interface.

### 🎯 Key Features

- **🔄 Real-time Skin Switching** - Instantly change skins for champions, minions, monsters, etc. during gameplay
- **🎨 Custom Skin Index** - Support manual skin ID input to unlock hidden skins
- **🖥️ Modern GUI** - Intuitive graphical interface based on ImGui
- **⚙️ Hotkey Support** - Customizable keyboard shortcuts
- **💾 Configuration Persistence** - Automatic save and load of user settings
- **🔧 Memory Safety** - Intelligent memory scanning and automatic offset detection
- **🌐 Multi-region Support** - Cross-region compatibility optimization
- **🐍 Tool Integration** - Python scripts for configuration conversion with other skin tools

---

## 🏗️ Project Structure

```
R3Archive/
├── R3nzSkin/                    # Core DLL Module
│   ├── R3nzSkin.cpp           # DLL Entry and Main Loop
│   ├── CheatManager.hpp       # Cheat Manager
│   ├── Config.cpp/hpp         # Configuration Management
│   ├── GUI.cpp/hpp            # Graphical Interface
│   ├── Hooks.cpp/hpp          # Hooking System
│   ├── Memory.cpp/hpp         # Memory Operations
│   ├── SkinDatabase.cpp/hpp   # Skin Database
│   ├── SDK/                   # Game SDK
│   │   ├── GameObject.hpp     # Game Objects
│   │   ├── Champion.hpp       # Champion Class
│   │   ├── AITurret.hpp       # Turrets
│   │   └── ...
│   └── imgui/                 # ImGui Graphics Library
├── R3nzSkin_Injector/         # Injector Tool
│   ├── main.cpp               # Injector Entry
│   ├── Injector.hpp          # Injection Logic
│   ├── R3nzUI.hpp            # GUI Interface
│   └── resource.h            # Resource Files
├── PythonScripts/             # Python Utility Scripts
│   └── lolskin_to_skin.py    # Configuration Converter
└── README.md                 # Project Documentation
```

---

## 🚀 Quick Start

### System Requirements

- **OS**: Windows 10/11 (64-bit)
- **Development Environment**: Visual Studio 2019/2022
- **Runtime**: .NET Framework 4.8+
- **Target Game**: League of Legends

### Build Instructions

1. **Clone the Repository**
   ```bash
   git clone --recursive https://github.com/SFHJavaer/R3Archive.git
   cd R3Archive
   ```

2. **Open Solution**
   - Open `R3nzSkin.sln` with Visual Studio
   - Select `x64` platform configuration

3. **Build Projects**
   - Build `R3nzSkin` project to generate the core DLL
   - Build `R3nzSkin_Injector` project to generate the injector

### Usage Instructions

1. **Launch Injector**
   - Run `R3nzSkin_Injector.exe`
   - Wait for game process detection

2. **Inject DLL**
   - Select League of Legends process
   - Click inject button

3. **In-Game Controls**
   - Press `Insert` to toggle menu
   - Use `Page Up`/`Page Down` to switch skins
   - Or manually input skin ID in the menu

---

## ⚙️ Configuration

### Hotkey Settings

- **Menu Toggle**: `Insert` (default)
- **Next Skin**: `Page Up` (default)
- **Previous Skin**: `Page Down` (default)

### Supported Skin Types

- **Champion Skins** - Local player and other players
- **Minion Skins** - Minions, siege engines
- **Monster Skins** - Various jungle monsters
- **Turret Skins** - Defense turrets
- **Ward Skins** - Wards

### Configuration Files

Configuration files are automatically saved in the game directory, including:
- Skin index settings
- UI configuration
- Hotkey bindings

---

## 🔧 Python Tools

### lolskin_to_skin.py

Convert configurations from other skin tools to R3nzSkin format:

```bash
python PythonScripts/lolskin_to_skin.py
```

**Features**:
- Automatic detection of LOLSkin configuration files
- Skin index format conversion
- Generate R3nzSkin-compatible JSON configuration
- Support batch conversion

**Usage Example**:
```python
# Convert LOLSkin configuration
hero_skin = skin_to_dictionary("path/to/Config.ini")
r3nz_config = forward_data(hero_skin)

# Save as JSON
with open('data.json', 'w') as f:
    json.dump(r3nz_config, f)
```

---

## 🛠️ Technical Details

### Core Technologies

- **Memory Injection**: DLL injection techniques
- **Hooking System**: DirectX hooks and game function hooks
- **Memory Scanning**: Signature scanning and offset detection
- **Configuration Management**: JSON format configuration persistence
- **Graphics Interface**: ImGui + DirectX11

### Security Features

- **Thread Hiding**: Prevent injection thread detection
- **Memory Protection**: Safe memory read/write operations
- **Error Handling**: Comprehensive exception handling mechanisms
- **Logging System**: Detailed runtime logging

### Architecture Benefits

- **Modular Design**: High cohesion, low coupling module structure
- **Type Safety**: Strong typed C++ implementation
- **Performance Optimization**: Efficient memory operations and rendering
- **Extensibility**: Easy to add new skin types and features

---

## 📋 Development Guide

### Environment Setup

1. Install Visual Studio 2019/2022
2. Install Windows SDK
3. Clone the project and its submodules

### Code Standards

- Use C++17 standard
- Follow modern C++ best practices
- Use smart pointers for memory management
- Exception-safe design patterns

### Debugging Tips

- Use Visual Studio debugger
- Check injection log output
- Monitor memory usage
- Verify hook function calls

---

## ⚠️ Important Notices

### Academic Research Declaration

This project serves as a **computer graphics research experiment for academic exchange and technical validation only**. Strictly prohibited for commercial use or unlawful activities.

**Prohibited Activities**:
- Commercial use
- Unlawful gaming activities
- Violation of game user agreements

### Legal Disclaimer

Pursuant to 17 USC §512 (DMCA):
- No technical support provided by this project
- Reverse engineering prohibited
- Right to halt regional distributions reserved

**User Responsibility**: Users assume all legal risks and consequences.

---

## 🤝 Contributing

Issues and Pull Requests are welcome to improve the project:

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

### Contribution Requirements

- Code must be tested
- Follow existing code style
- Update relevant documentation
- Add necessary comments

---

## 📄 License

This project is licensed under MIT - see [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [R3nzTheCodeGOD](https://github.com/R3nzTheCodeGOD) - Original R3nzSkin project
- [ocornut/imgui](https://github.com/ocornut/imgui) - Graphics interface library
- [nlohmann/json](https://github.com/nlohmann/json) - JSON processing library

---

## 📞 Contact

- Project Homepage: [https://github.com/SFHJavaer/R3Archive](https://github.com/SFHJavaer/R3Archive)
- Issue Reports: [Create Issue](https://github.com/SFHJavaer/R3Archive/issues)

---

<div align="center">

**⭐ If this project helps you, please give it a star!**

</div>
