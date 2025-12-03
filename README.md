
<div align="center"> 
  
<img src="https://github.com/AlejandroSQR/RenderMan27-RHEL10-Temporary-Workaround/blob/main/images/RMAN_TF1.svg" width="600" alt="RockyL10XPI">

# RenderMan 27 RHEL10 Temporary Workaround Fix (v0.5)

RenderMan 27 Temporary Installation guide to RHEL 10 and based Distributions (Rocky/Alma/Oracle/CentOS) using provisional dependencies and packages

</div>

# Disclaimer

>[!WARNING]
>This repository is not affiliated with or endorsed by Pixar. RenderMan is the property of Pixar Animation Studios. The methods documented here are unofficial and intended only as a temporary workaround for users who require RenderMan 27 on RHEL 10–based distributions before official support is available. Use at your own discretion. When there is official solution or supported build is released, this repository will be archived.

>[!WARNING]
>The logo used in this repository is an original design created solely for documentation purposes. It is inspired by the visual style of the RenderMan logo engine but is not an official Pixar asset. It holds no commercial value, is not intended for commercial use, and should not be interpreted as an official RenderMan or Pixar mark.

# 0.5 Before Downloading

## [IMPORTANT] RHEL-Based Distros Compatibility 

100% Compatibility is not guaranteed, tools or packages may work differently depending on the specific distribution including repositories and even previous versions.

## [WARNING] Temporary Workaround, NOT for Professional Work

This approach is a temporary workaround and should only be used when testing or evaluating the software, it may produce instability or unresolved library issues causing to crash the software.

# 1. Download RenderMan® (NCR / COMMERCIAL)

[!IMPORTANT]
> You need to create an account to download the version that you want

https://renderman.pixar.com/install

# 2. Install Commercial/ Non-Commercial RenderMan® using the command

### Non Commercial
```
sudo rpm -ivh RenderMan-InstallerNCR-27.0.0_2386582-linuxRHEL9_gcc11icx232.x86_64.rpm --force --nodeps 
```
### Commercial
```
sudo rpm -ivh RenderMan-Installer-27.0.0_2386582-linuxRHEL9_gcc11icx232.x86_64.rpm --force --nodeps
```

>[!NOTE]
>You can install it through the Software Center, but for a proper installation it is necessary to do it through the terminal.

>[!IMPORTANT]
> **--force** Allows the package to install even if it conflicts with existing files or versions on the system and **--nodeps** ignore and skip dependency status during package installation or removal.

# 3. RHEL Repositories
Enable the CodeReady Builder repository. You have two methods to do this. (CRB)
#### Method 1 - Terminal
```sudo dnf config-manager --enable crb```
#### Method 2 - Software Manager
Software > Main Menu > Software Repositories > "CRB"

>[!NOTE]
> Rocky/AlmaLinux and other distros repository appears under the same identifier (CRB) even when enabled through their own tools.

# 4. Packages and Dependencies

Command that installs all the libraries listed below

``` sudo dnf install mesa-libGLU libicu67 pcre2-utf16 xcb-util-cursor xcb-util-wm xcb-util-keysyms ```

## Package List
- mesa-libGLU
- libicu67
- pcre2-utf16
- xcb-util-cursor
- xcb-util-wm
- xcb-util-keysyms

# 5. Render Engine Installation

Start the RenderMan Installer

``` sudo /opt/pixar/RenderMan-Installer-ncr-XX.X/bin/./RenderManInstaller``` 

Here, you must first download the render engine then its license and select the plugin/software that you need to use RenderMan

>[!NOTE]
> Depending on the version installed, you will need to adjust the version number according to what you downloaded earlier.


# 6. Software Installation add-ons

After you complete Renderman Installer, depending of your software, you need to do extra steps (Blender tested at the moment)

## Blender

you only need to download the RenderMan plugin.

https://github.com/prman-pixar/RenderManForBlender/releases/tag/v_27.0

>[!IMPORTANT]
> Renderman works only with Blender 4.2 LTS due to Python version (3.11 and Below)
