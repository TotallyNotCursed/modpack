# Totally Not Cursed Installation Guide

This guide explains how to install Totally Not Cursed for both client and server setups on Minecraft 1.20.1 with Forge 47.4.0. It covers general preparation steps, client instructions (including keybindings), server deployment, troubleshooting, and important notes.

## 📑 Index

- [System Requirements](#system-requirements)
- [General Preparation](#general-preparation)
- [Client Installation](#client-installation)
  - [Loading Keybinding Preset (Important!)](#loading-keybinding-preset)
  - [Method 1: Pre-Launch Command (Recommended)](#method-1-pre-launch-command)
  - [Method 2: Manual Method](#method-2-manual-method)
- [Server Installation](#server-installation)
- [Important Notes](#important-notes)
- [Troubleshooting](#troubleshooting)

<a name="system-requirements"></a>

## 🖥️ System Requirements

### Minimum Requirements

- **Java**: Java 17 or higher
- **RAM**: 4GB allocated to Minecraft
- **Storage**: 2GB free space
- **Minecraft Version**: 1.20.1
- **Forge Version**: 47.4.0

### Recommended Requirements

- **Java**: Java 21 ([Eclipse Adoptium](https://adoptium.net/temurin/releases?version=21) recommended)
- **RAM**: 8GB allocated to Minecraft
- **Storage**: 4GB free space

> **Performance Note**: Java 21 provides better performance and lower memory usage compared to older versions. Eclipse Adoptium is the recommended distribution.
>
> **RAM Allocation Tip**: For smoother gameplay and more consistent tick rates, it is recommended to set the **minimum and maximum allocated RAM to the same value** in your launcher settings (e.g., both set to 8GB). This can help reduce stutters, especially on systems with limited RAM or when running heavily modded instances.
>
> <details>
> <summary>Technical explanation (optional)</summary>
>
> By default, the JVM starts with a small heap (minimum RAM) and grows it as needed up to the maximum. When the heap needs to grow, the JVM may pause the game to allocate more memory, causing stutters or inconsistent tick rates. Setting the minimum (`-Xms`) and maximum (`-Xmx`) heap size to the same value pre-allocates all the memory at startup, avoiding these pauses and making garbage collection behavior more predictable.
>
> This benefit is particularly noticeable with heavily modded Minecraft instances like this one, where memory usage can be significant and unpredictable. The performance improvement is most pronounced on systems with limited available RAM.
>
> </details>

<a name="general-preparation"></a>

## 📋 General Preparation

1. **Create a Minecraft 1.20.1 Instance**

   - Set up Minecraft 1.20.1 with Forge 47.4.0 using your preferred launcher
   - Allocate memory according to the system requirements above

2. **Download the Bootstrap JAR**
   - Download `packwiz-installer-bootstrap.jar` from the [GitHub releases page](https://github.com/packwiz/packwiz-installer-bootstrap/releases)
   - Place the `.jar` file in your **Minecraft instance folder** (the folder containing `options.txt` for clients or `server.properties` for servers)

<a name="client-installation"></a>

## 🖥️ Client Installation

<a name="loading-keybinding-preset"></a>

### 🔑 Loading Keybinding Preset (Important!)

After installing the modpack for the first time or after any update, load the correct keybinding preset to avoid conflicts:

1. Launch Minecraft and go to **Options** → **Controls** → **Key Binds**
2. At the bottom center, click **Key Preset**
3. Select the preset named **Totally_Not_Cursed**, then click **Load**

**Important**: Repeat this step after every modpack update to ensure you have the latest keybinding configuration. If you experience keybinding conflicts after loading the preset, please report it on our GitHub issues page.

<a name="method-1-pre-launch-command"></a>

### 🚀 Method 1: Pre-Launch Command (Recommended)

For launchers that support pre-launch commands (Prism Launcher, ATLauncher, etc.):

1. Enable pre-launch commands in your launcher's instance settings
2. Add the following command to the pre-launch field:
   ```bash
   "$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/TotallyNotCursed/modpack/refs/heads/main/src/pack.toml
   ```

**Note**: Replace `$INST_JAVA` with your launcher's Java variable syntax if different.

**Benefits**: Automatic updates, seamless experience, Forge version notifications.

<a name="method-2-manual-method"></a>

### 🔧 Method 2: Manual Method

For environments without pre-launch command support:

1. Open a terminal/command prompt in the folder containing `packwiz-installer-bootstrap.jar`
2. Run the following command:
   ```bash
   java -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/TotallyNotCursed/modpack/refs/heads/main/src/pack.toml
   ```

**Important Limitations**:

- No automatic updates
- Must manually run this command for each modpack update
  - Check for updates using the in-game notification on the title screen

<a name="server-installation"></a>

## 🗄️ Server Installation

To set up a dedicated server:

1. Follow the [General Preparation](#general-preparation) steps
2. Open a terminal in the folder containing the bootstrap jar
3. Run this command:
   ```bash
   java -jar packwiz-installer-bootstrap.jar -g -s server https://raw.githubusercontent.com/TotallyNotCursed/modpack/refs/heads/main/src/pack.toml
   ```

This will download and install server-compatible mods only.

<a name="important-notes"></a>

## ⚠️ Important Notes

- **Tested Environments**: Prism Launcher and manual methods have been thoroughly tested
- **Manual Method Support**: Limited support available due to varying environment behaviors
- **Java Recommendation**: [Eclipse Adoptium](https://adoptium.net/) Java 21 provides optimal performance
- **Update Notifications**: The modpack displays update notifications on the main menu
- **Keybinding Conflicts**: Always load the preset after updates to avoid issues

<a name="troubleshooting"></a>

## 🆘 Troubleshooting

### Common Issues and Solutions

**"Java not found" error**

- Ensure Java is installed and added to your system PATH
- Use the full path to Java: `/path/to/java -jar packwiz-installer-bootstrap.jar ...`
- Verify Java version meets minimum requirements (Java 17+)

**Out of memory errors**

- Increase RAM allocation in your launcher settings
- Ensure sufficient system memory is available
- Consider upgrading to Java 21 for better memory management
- Close other applications to free up memory

**Mod download failures**

- Check your internet connection stability
- Verify the pack.toml URL is correct and accessible
- Retry the command after a few minutes (temporary network issues)
- Check firewall/antivirus settings that might block downloads

**Keybinding conflicts**

- Load the Totally_Not_Cursed preset as described above
- Report persistent conflicts on our GitHub issues page

**Modpack won't launch**

- Verify Minecraft version (1.20.1) and Forge version (47.4.0) are correct
- Check that all mods downloaded successfully
- Review the latest log files for specific error messages
- Ensure sufficient disk space is available

### Getting Additional Help

For support, see our [official support instructions](https://github.com/TotallyNotCursed/.github/blob/main/.github/SUPPORT.md).
