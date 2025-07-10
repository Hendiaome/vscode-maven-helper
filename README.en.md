# Maven Helper - VSCode Extension

**Language**: [中文](README.md) | [English](README.en.md)

> **Professional Maven Dependency Analysis Tool**: A Maven dependency management and conflict detection extension designed for the VSCode platform  
> **Visual Dependency Management**: Provides intuitive tree view and dependency reference path analysis  
> **Boost Development Efficiency**: Simplifies Maven dependency analysis workflow, quickly locate and resolve dependency issues

## Features

### Core Functionality
**Visual Dependency Tree**: Display project dependencies in tree structure, replacing traditional command-line output  
**Dependency Reference Analysis**: Track complete reference paths of dependencies to understand dependency sources  
**Conflict Detection**: Automatically identify version conflicts and dependency issues  
**Quick Operations**: Provide context menus and shortcuts to improve work efficiency  
**VSCode Integration**: Native integration into VSCode interface, no need to switch tools

### Main Features

#### 1. Visual Dependency Tree
```
Traditional way: mvn dependency:tree (command-line text output)
Maven Helper: Graphical tree structure + interactive operations
```
**Hierarchical Display**: Clear tree structure showing dependency hierarchy  
**Status Indicators**: Support displaying duplicate, conflict, cycle, version managed, scope conflict and other statuses  
**Quick Filtering**: Support filtering dependencies by artifactId  
**GroupID Control**: Option to show or hide GroupID to simplify view  

#### 2. Dependency Reference Path Analysis
```
Select dependency → Show all reference paths
Project root → Intermediate dependency → Target dependency
Project root → Other paths → Target dependency
```
**Path Tracking**: Complete display of dependency introduction paths  
**Multi-path Support**: Show all possible reference paths for the same dependency  
**Quick Navigation**: Click path nodes to jump to corresponding POM file locations  
**Exclusion Suggestions**: Provide exclusion configuration suggestions for dependency conflicts  

#### 3. Smart Conflict Detection
```
Supports detection of:
• Version Conflicts
• Duplicate Dependencies  
• Scope Conflicts
• Transitive Issues
```

#### 4. Convenient Operation Features
**Right-click Exclusion**: Auto-generate exclusion configuration after selecting dependencies  
**Jump to Definition**: Quickly jump to dependency definition in POM file  
**Auto Refresh**: Automatically detect POM file changes and prompt for re-analysis  

## Use Cases

### Development Scenarios
**Dependency Management**: Analyze and manage project dependency relationships  
**Problem Diagnosis**: Quickly locate dependency-related issues like ClassNotFoundException  
**Version Upgrades**: Assess the impact scope of dependency version upgrades  
**Code Review**: Check the rationality of dependency introduction  

### Enterprise Applications
**Architecture Governance**: Unified management of dependency versions in enterprise projects  
**Security Auditing**: Identify dependency versions with security vulnerabilities  
**Build Optimization**: Optimize dependency structure to reduce build time  
**Team Collaboration**: Provide visual dependency relationship diagrams for team communication  

## Installation and Usage

### Installation
1. Open VSCode
2. Press `Ctrl+Shift+X` to open Extension Marketplace
3. Search for "Maven Helper"
4. Click Install

### Prerequisites
1. Before using this tool, ensure the **Maven for Java** extension is installed and configured correctly. You need to specify the Maven execution path and `settings.xml` path in your VS Code `settings.json`, for example:
   ```json
   "maven.executable.path": "/path/to/your/mvn",
   "maven.settingsFile": "/path/to/your/settings.xml"
   ```
2. **For Windows users**: Please ensure your `JAVA_HOME` system environment variable is correctly configured and points to your JDK installation directory. If you encounter issues, this extension will attempt to use the `java.home` path configured in the VS Code Java extension as a fallback.

### Usage
1. Open a Maven project containing `pom.xml`
2. The "Maven Helper" icon will appear in the left activity bar
3. Click to expand the panel and select a project to start dependency analysis
4. Use the tree view to browse dependency relationships

## Screenshots
![Maven Helper Screenshot](https://github.com/Hendiaome/vscode-maven-helper/blob/master/image.png)

## Configuration Options
```json
{
  "maven-helper.dependency.showGroupId": false, // Whether to show GroupID
  "maven-helper.log.debug": false, // Whether to enable debug logging
  "maven-helper.maven.useNativeDependencyTree": false // Whether to use native 'dependency:tree -Dverbose' command instead of depgraph plugin
}
```

### Configuration Description

**maven-helper.dependency.showGroupId**  
Controls whether to show GroupID in dependency tree, default is false (hidden)

**maven-helper.log.debug**  
Controls whether to output debug logs, default is false

**maven-helper.maven.useNativeDependencyTree**  
Controls Maven dependency analysis execution mode:
`false` (default): Use depgraph plugin for dependency analysis
`true`: Use native `dependency:tree -Dverbose` command

> **Note**: If you encounter issues where depgraph mode cannot run properly, you can enable this option to switch to native command mode. Project-level configuration is recommended because depgraph.

## Support and Feedback
**Issue Reports**: [GitHub Issues](https://github.com/hendiaome/vscode-maven-helper/issues)  
**Feature Requests**: [GitHub Discussions](https://github.com/hendiaome/vscode-maven-helper/discussions)  
**Project Repository**: [GitHub Repository](https://github.com/hendiaome/vscode-maven-helper)  

## Technical Advantages

Compared to traditional Maven dependency analysis methods:
❌ Command-line `mvn dependency:tree` output is hard to read  
❌ Need to switch to other IDE tools  
❌ Manual POM file analysis is inefficient  
❌ Lack of visual dependency relationship display  

**Improvements provided by Maven Helper:**
✅ Native VSCode integration, no tool switching required  
✅ Graphical interface, intuitive and easy to use  
✅ Automated analysis, reducing manual operations  
✅ Professional dependency management features  

## Version Information

### v1.0.0
• Implemented visual dependency tree display  
• Support for dependency reference path analysis  
• Integrated dependency conflict detection mechanism  
• Provided convenient operation interface  

### v1.0.5, Planned
• Optimize experience issues: view loss after first exclusion
• Optimize experience issues: view still exists when excluding dependencies with multiple identical first-level introductions
• Optimize experience issues: view still exists after exclusion when dependency path has only 1 path

### v1.1.0, Planned
• Reference chain supports tree structure, clickable expansion, can locate to pom file

---
**Maven Helper** - Making Maven dependency management simpler and more efficient 
