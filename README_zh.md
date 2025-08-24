# R3nzSkin - 英雄联盟皮肤修改工具

<div align="center">

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/SFHJavaer/R3Archive)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](https://www.microsoft.com/windows)
[![C++](https://img.shields.io/badge/C%2B%2B-17-blue)](https://isocpp.org/)

*一个功能强大的英雄联盟游戏皮肤修改工具*

[English](README.md) | [中文](README_zh.md)

</div>

---

## 📖 项目简介

R3nzSkin 是一个专为英雄联盟游戏设计的皮肤修改工具。通过内存注入和钩子技术，实现游戏内皮肤的实时切换和自定义。该项目包含完整的注入器、配置管理系统和用户友好的图形界面。

### 🎯 主要特性

- **🔄 实时皮肤切换** - 游戏运行时即时更换英雄、兵线、野怪等皮肤
- **🎨 自定义皮肤索引** - 支持手动输入皮肤ID，解锁隐藏皮肤
- **🖥️ 现代化GUI** - 基于ImGui的直观图形界面
- **⚙️ 热键支持** - 自定义键盘快捷键控制
- **💾 配置持久化** - 自动保存和加载用户设置
- **🔧 内存安全** - 智能内存扫描和偏移量自动查找
- **🌐 多区域支持** - 跨地区兼容性优化
- **🐍 工具集成** - Python脚本支持与其他皮肤工具的配置转换

---

## 🏗️ 项目架构

```
R3Archive/
├── R3nzSkin/                    # 核心DLL模块
│   ├── R3nzSkin.cpp           # DLL入口和主循环
│   ├── CheatManager.hpp       # 作弊管理器
│   ├── Config.cpp/hpp         # 配置管理
│   ├── GUI.cpp/hpp            # 图形界面
│   ├── Hooks.cpp/hpp          # 钩子系统
│   ├── Memory.cpp/hpp         # 内存操作
│   ├── SkinDatabase.cpp/hpp   # 皮肤数据库
│   ├── SDK/                   # 游戏SDK
│   │   ├── GameObject.hpp     # 游戏对象
│   │   ├── Champion.hpp       # 英雄类
│   │   ├── AITurret.hpp       # 防御塔
│   │   └── ...
│   └── imgui/                 # ImGui图形库
├── R3nzSkin_Injector/         # 注入器工具
│   ├── main.cpp               # 注入器入口
│   ├── Injector.hpp          # 注入逻辑
│   ├── R3nzUI.hpp            # 图形界面
│   └── resource.h            # 资源文件
├── PythonScripts/             # Python工具脚本
│   └── lolskin_to_skin.py    # 配置转换工具
└── README.md                 # 项目文档
```

---

## 🚀 快速开始

### 系统要求

- **操作系统**: Windows 10/11 (64位)
- **开发环境**: Visual Studio 2019/2022
- **运行时**: .NET Framework 4.8+
- **目标游戏**: 英雄联盟

### 构建步骤

1. **克隆项目**
   ```bash
   git clone --recursive https://github.com/SFHJavaer/R3Archive.git
   cd R3Archive
   ```

2. **打开解决方案**
   - 使用 Visual Studio 打开 `R3nzSkin.sln`
   - 选择 `x64` 平台配置

3. **构建项目**
   - 构建 `R3nzSkin` 项目生成核心DLL
   - 构建 `R3nzSkin_Injector` 项目生成注入器

### 使用方法

1. **启动注入器**
   - 运行 `R3nzSkin_Injector.exe`
   - 等待游戏进程检测

2. **注入DLL**
   - 选择英雄联盟进程
   - 点击注入按钮

3. **游戏内操作**
   - 按 `Insert` 键打开/关闭菜单
   - 使用 `Page Up`/`Page Down` 切换皮肤
   - 或在菜单中手动输入皮肤ID

---

## ⚙️ 配置说明

### 热键设置

- **菜单切换**: `Insert` (默认)
- **下一个皮肤**: `Page Up` (默认)
- **上一个皮肤**: `Page Down` (默认)

### 皮肤类型支持

- **英雄皮肤** - 本地玩家和其他玩家
- **兵线皮肤** - 小兵、炮车
- **野怪皮肤** - 各类野怪
- **守卫塔皮肤** - 防御塔
- **眼位皮肤** - 守卫

### 配置文件

配置文件自动保存在游戏目录下，包含：
- 皮肤索引设置
- 界面配置
- 热键绑定

---

## 🔧 Python工具

### lolskin_to_skin.py

将其他皮肤工具的配置转换为R3nzSkin格式：

```bash
python PythonScripts/lolskin_to_skin.py
```

**功能特性**:
- 自动检测LOLSkin配置文件
- 转换皮肤索引格式
- 生成R3nzSkin兼容的JSON配置
- 支持批量转换

**使用示例**:
```python
# 转换LOLSkin配置
hero_skin = skin_to_dictionary("path/to/Config.ini")
r3nz_config = forward_data(hero_skin)

# 保存为JSON
with open('data.json', 'w') as f:
    json.dump(r3nz_config, f)
```

---

## 🛠️ 技术细节

### 核心技术

- **内存注入**: DLL注入技术
- **钩子系统**: DirectX钩子和游戏函数钩子
- **内存扫描**: 特征码扫描和偏移量查找
- **配置管理**: JSON格式配置持久化
- **图形界面**: ImGui + DirectX11

### 安全特性

- **线程隐藏**: 防止注入线程被检测
- **内存保护**: 安全的内存读写操作
- **错误处理**: 完善的异常处理机制
- **日志系统**: 详细的运行日志记录

### 架构优势

- **模块化设计**: 高内聚、低耦合的模块结构
- **类型安全**: 强类型C++实现
- **性能优化**: 高效的内存操作和渲染
- **可扩展性**: 易于添加新的皮肤类型和功能

---

## 📋 开发指南

### 环境搭建

1. 安装 Visual Studio 2019/2022
2. 安装 Windows SDK
3. 克隆项目及其子模块

### 代码规范

- 使用C++17标准
- 遵循现代C++最佳实践
- 使用智能指针管理内存
- 异常安全的设计模式

### 调试技巧

- 使用Visual Studio调试器
- 查看注入日志输出
- 监控内存使用情况
- 检查钩子函数调用

---

## ⚠️ 重要声明

### 学术研究声明

本项目仅用于**计算机图形学研究和学术交流**。严禁用于任何商业用途或非法活动。

**禁止行为**:
- 商业化使用
- 非法游戏活动
- 违反游戏用户协议

### 法律免责

根据 DMCA 第512条规定：
- 本项目不提供技术支持
- 禁止逆向工程
- 保留停止分发的权利

**用户责任**: 使用者自行承担所有法律风险和后果。

---

## 🤝 贡献指南

欢迎提交Issue和Pull Request来改进项目：

1. Fork本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开Pull Request

### 贡献要求

- 代码需经过测试
- 遵循现有代码风格
- 更新相关文档
- 添加必要的注释

---

## 📄 许可证

本项目采用MIT许可证 - 查看[LICENSE](LICENSE)文件了解详情。

---

## 🙏 致谢

- [R3nzTheCodeGOD](https://github.com/R3nzTheCodeGOD) - 原始R3nzSkin项目
- [ocornut/imgui](https://github.com/ocornut/imgui) - 图形界面库
- [nlohmann/json](https://github.com/nlohmann/json) - JSON处理库

---

## 📞 联系方式

- 项目主页: [https://github.com/SFHJavaer/R3Archive](https://github.com/SFHJavaer/R3Archive)
- 问题反馈: [创建Issue](https://github.com/SFHJavaer/R3Archive/issues)

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给它一个星标！**

</div>
