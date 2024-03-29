# Developing for Cypress PSoC6 on VSCode

### Project boilerplate

1. Prerequisites
    - VS Code
        - https://code.visualstudio.com/download
    - ModusToolbox 1.1 (for PDL, Device Configurator, CyMCUElfTool and OpenOCD)
        - https://www.cypress.com/products/modustoolbox-software-environment
    - GNU Arm Embedded Toolchain
        - https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads
    - CMake
        - https://cmake.org/download/
    - Make
        - depending on your OS (for Windows MinGW can be used, macOS homebrew GNU make)

1. VS Code Extensions
    - ARM Support For Visual Studio Code (dan-c-underwood)
    - C/C++ IntelliSense, debugging (microsoft)
    - CMake language support (twxs)
    - CMake Tools (vector-of-bool)
    - Cortex-Debug GDB support (marus25)
    - LinkerScript support for GNU (Zixuan Wang)
    - Open in Application (Fabio Spampinato)
    - Output Colorizer (IBM)
    - Tasks (actboy168)
    
1. Configure
    - Command Palette (CTRL+SHIFT+P) > type: JSON > Click Preferences: Open Settings (JSON)
    - Add the following lines to the VS Code User settings:
    ```json
    {
        "C_Cpp.default.configurationProvider": "vector-of-bool.cmake-tools",
        "C_Cpp.default.compilerPath": "arm-none-eabi-gcc",
        "C_Cpp.loggingLevel":"Debug",
        "cmake.cmakePath": "/Applications/CMake.app/Contents/bin/cmake",
        "cortex-debug.openocdPath": "/Applications/ModusToolbox_1.1/tools/openocd-2.1/bin/openocd",
        "cortex-debug.JLinkGDBServerPath": "/Applications/SEGGER/JLink_V650b/JLinkGDBServerCLExe",
        "cmake.configureOnOpen": true,
        "cmake.sourceDirectory": "${workspaceRoot}"
    }
    ```
1. Check
    - if make is installed by typing 'make -v' into the terminal window of VS Code
        (make needs to be added to the system's path variable)
        
1. Remind
    - after changing the device configuration to use
        - Clean Reconfigure
        - Clean Rebuild
        
        in order to build the image properly.
