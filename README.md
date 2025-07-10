# Maven Helper - VSCode 扩展

**Language**: [中文](README.md) | [English](README.en.md)

> **专业的 Maven 依赖分析工具**：为 VSCode 平台设计的 Maven 依赖管理和冲突检测扩展  
> **可视化依赖管理**：提供直观的树形视图和依赖引用路径分析  
> **提升开发效率**：简化 Maven 依赖分析流程，快速定位和解决依赖问题

## 功能特性

### 核心功能
**可视化依赖树**：以树形结构展示项目依赖关系，替代传统命令行输出  
**依赖引用分析**：追踪依赖的完整引用路径，了解依赖来源  
**冲突检测**：自动识别版本冲突和依赖问题  
**快速操作**：提供右键菜单和快捷操作，提升工作效率  
**VSCode 集成**：原生集成到 VSCode 界面，无需切换工具

### 主要功能

#### 1. 可视化依赖树
```
传统方式：mvn dependency:tree (命令行文本输出)
Maven Helper：图形化树状结构 + 交互式操作
```
**层级展示**：清晰的树状结构显示依赖层级关系  
**状态标识**：支持显示 duplicate、conflict、cycle、version managed、scope conflict 等状态  
**快速筛选**：支持按 artifactId 进行依赖过滤  
**GroupID 控制**：可选择显示或隐藏 GroupID，简化视图  

#### 2. 依赖引用路径分析
```
选择依赖 → 显示所有引用路径
项目根 → 中间依赖 → 目标依赖
项目根 → 其他路径 → 目标依赖
```
**路径追踪**：完整展示依赖的引入路径  
**多路径支持**：显示同一依赖的所有可能引用路径  
**快速定位**：点击路径节点可跳转到对应的 POM 文件位置  
**排除建议**：为依赖冲突提供排除配置建议  

#### 3. 智能冲突检测
```
支持检测：
• 版本冲突 (Version Conflicts)
• 重复依赖 (Duplicate Dependencies)  
• 作用域冲突 (Scope Conflicts)
• 传递依赖问题 (Transitive Issues)
```

#### 4. 便捷操作功能
**右键排除**：选中依赖后可自动生成 exclusion 配置  
**跳转定义**：快速跳转到依赖在 POM 文件中的定义  
**自动刷新**：POM 文件变更时自动检测并提示重新分析  

## 适用场景

### 开发场景
**依赖管理**：分析和管理项目依赖关系  
**问题诊断**：快速定位 ClassNotFoundException 等依赖相关问题  
**版本升级**：评估依赖版本升级的影响范围  
**代码审查**：检查依赖引入的合理性  

### 企业应用
**架构治理**：统一管理企业级项目的依赖版本  
**安全审计**：识别存在安全漏洞的依赖版本  
**构建优化**：优化依赖结构，减少构建时间  
**团队协作**：提供可视化的依赖关系图，便于团队沟通  

## 安装使用

### 安装方式
1. 打开 VSCode
2. 按 `Ctrl+Shift+X` 打开扩展市场
3. 搜索 "Maven Helper"
4. 点击安装

### 环境依赖
1. 使用本工具前，请确保 **Maven for Java** 扩展已正确安装和配置。您需要在 VS Code 的 `settings.json` 文件中指定 Maven 的执行路径和 `settings.xml` 路径，例如：
   ```json
   "maven.executable.path": "/path/to/your/mvn",
   "maven.settingsFile": "/path/to/your/settings.xml"
   ```
2. **Windows 用户请注意**: 请确保您的 `JAVA_HOME` 系统环境变量已正确配置并指向您的JDK安装目录。如果遇到问题，本扩展会尝试使用 VS Code Java 插件中配置的 `java.home` 路径作为备选方案。


### 使用方法
1. 打开包含 `pom.xml` 的 Maven 项目
2. 左侧活动栏会显示 "Maven Helper" 图标
3. 点击展开面板，选择项目开始分析依赖
4. 使用树形视图浏览依赖关系

## 功能截图
![Maven Helper 功能截图](https://github.com/Hendiaome/vscode-maven-helper/blob/master/image.png)
![image](https://github.com/user-attachments/assets/f8608a87-8607-489c-8bc9-d0084671d67f)


## 配置说明

**maven-helper.dependency.showGroupId**  
控制依赖树中是否显示GroupID，默认为false（隐藏）

**maven-helper.log.debug**  
控制是否输出调试日志，默认为false

**maven-helper.maven.useNativeDependencyTree**  
控制Maven依赖分析的运行模式：
`false`（默认）：使用depgraph插件进行依赖分析
`true`：使用原生的`dependency:tree -Dverbose`命令

> **注意**：如果遇到depgraph模式下无法正常运行的情况，可以启用此选项切换到原生命令模式，推荐配置project级别的运行模式，因为depgraph。

## 支持与反馈
**问题报告**：[GitHub Issues](https://github.com/hendiaome/vscode-maven-helper/issues)  
**功能建议**：[GitHub Discussions](https://github.com/hendiaome/vscode-maven-helper/discussions)  
**项目地址**：[GitHub Repository](https://github.com/hendiaome/vscode-maven-helper)  

## 技术优势

相比传统的 Maven 依赖分析方式：
❌ 命令行 `mvn dependency:tree` 输出难以阅读  
❌ 需要切换到其他 IDE 工具  
❌ 手动分析 POM 文件效率低下  
❌ 缺乏可视化的依赖关系展示  

**Maven Helper 提供的改进：**
✅ 原生 VSCode 集成，无需工具切换  
✅ 图形化界面，直观易用  
✅ 自动化分析，减少手工操作  
✅ 专业的依赖管理功能  

## 版本信息

### v1.0.0
• 实现可视化依赖树展示功能  
• 支持依赖引用路径分析  
• 集成依赖冲突检测机制  
• 提供便捷的操作界面  

### v1.0.5，计划
• 优化部分体验问题 首次排除后，视图丢失
• 优化部分体验问题 排除依赖如果存在多个相同的一级引入的问题，视图依然存在
• 优化部分体验问题 依赖路径只有1个，排除后依然存在

### v1.1.0，计划
• 引用链路支持树，可点击展开，可定位到pom文件

---
**Maven Helper** - 让 Maven 依赖管理更加简单高效
