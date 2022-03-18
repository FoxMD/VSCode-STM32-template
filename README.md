# VSCode-STM32-template
STM32 template needed to open and build CUBE IDE/Atollic projects in VS Code</br>
Example on: [STM32F303 Discovery](https://github.com/FoxMD/cube_ide_cmake_c_f303)

### Used tools:
- arm-none-eabi-gcc
- STM32CubeProgrammer
- ST-Link_gdbserver[^1]
- CMake
- Ninja [Ninja build system](https://github.com/ninja-build/ninja/releases)

### Used VSCode plugins/tools:
- ms-vscode.cpptools: [Syntax highlighting and other core features for C/C++ development](https://github.com/microsoft/vscode-cpptools)
- ms-vscode.cmake-tools: [CMake core tools, build system generator tool](https://github.com/microsoft/vscode-cmake-tools)
- twxs.cmake: [CMake color highlighting](https://github.com/zyxar/Sublime-CMakeLists)
- marus25.cortex-debug: [Cortex-M debugging extension, mandatory for STM32 debug from VSCode ](https://github.com/Marus/cortex-debug)
- dan-c-underwood.arm: [ARM Assembly syntax highlighter ](https://github.com/dan-c-underwood/vscode-arm)
- zixuanwang.linkerscript: [GCC Linker script syntax highlighter ](https://github.com/TheNetAdmin/vscode-linkerscript)

## Requirements
Tools and VSCode plugins from above</br>
### Installed with STM32-CUBE IDE

```
arm-none-eabi-gcc
STM32CubeProgrammer
ST-Link_gdbserver
```
### Manual install
CMake - [Download, install](https://https://cmake.org/download/) </br>
Ninja - [Standalone version](https://github.com/ninja-build/ninja/releases)

### VSCode
To install them in one shot, copy code below to terminal in VSCode

```
code --install-extension ms-vscode.cpptools
code --install-extension ms-vscode.cmake-tools
code --install-extension twxs.cmake
code --install-extension marus25.cortex-debug
code --install-extension dan-c-underwood.arm
code --install-extension zixuanwang.linkerscript
```
## Modifications
CMakeLists.txt - everywhere under #Modified
.vscode/launch.json - CPU and Paths

## TODO
Intelisence highligting (.vscode/c_cpp_properties.json needs to be adjusted)

## Known issues
- Generated files (.hex, .bin) are bigger with same compiler settings then in STM32-CUBE IDE   

[^1]: Some AV delete ST-Link_servergdb.exe and let the .bat file exist, while trying to debug your project, you get an error:
`Debugger error: Client: Error: read ECONNRESET` </br>
**Solution:** Just install it again and put a exception in your AV for the exe file before you run it again[^1].