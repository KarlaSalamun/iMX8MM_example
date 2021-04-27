# iMX8MM M4 application template

C/C++ code project template for use on M4 core in iMX8MM SoC's.
Whole code is based (copied) on *NXP SDK*.

## Requirements
- GNU Arm Embedded Toolchain
    ```bash
    $ sudo apt -y install gcc-arm-none-eabi binutils-arm-none-eabi gdb-arm-none-eabi
    ```
- CMake
    ```bash
    $ sudo apt -y install cmake
    ```
- Segger JLink support
    ```bash
    $ wget https://www.segger.com/downloads/jlink/JLink_Linux_x86_64.deb
    $ sudo dpkg -i JLink_Linux_x86_64.deb
    ```

## VSCode

### Setting up

Download latest version of [VSCode](https://code.visualstudio.com/download) and install it:

```bash
$ sudo dpkg -i code_*_amd64.deb
```

Install neccessary VSCode extensions (you can do this from VSCode):

```bash
code --install-extension marus25.cortex-debug
code --install-extension ms-vscode.cpptools
```

### Building the project

To build the project in VSCode type *Ctrl+Shift+P*, the command palette
will show up. Search and select *Tasks: Run Task*. Two tasks will be
proposed *Cmake* and *make*. Running *Cmake* task will only create
build files while *make* task will also compile the project after 
(whole job).

When selecting option, you will be prompted to select one the available
build type:

* debug 
* release
* ddr_debug
* ddr_release
* flash_debug
* flash_releas

After successful *Cmake* task, build files (*CMakeFiles/*, *CMakCache.txt*, *Makefile*) and 
in the *build* folder and after successfully running *make* task, depending of the 
build type output folder with *.bin* and *.elf* will be created in *build* folder.

### Debugging the project

Connect your JLink to your development board.
After pressing the *F5* key VSCode will launch debugging. As in previous step you will be 
prompted to select one of the builds (be sure that you previously built that target). 
After selecting the build vscode will flash *.elf* from that build folder to your development board, 
start the program and open up the debugging interface.

## Useful links

https://developer.toradex.com/software/freertos/developing-m4-applications-using-visual-studio-code#1-linux