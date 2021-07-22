# esp-idf-clion
configuration and setup clion with esp-idf

## Install and setup esp idf
1. Create directory esp
```
mkdir -p ~/esp
cd ~/esp
git clone --recursive https://github.com/espressif/esp-idf.git
```

2. change directory to esp-idf
```
cd ~/esp/esp-idf
```

3. run script install.sh
```
./install.sh
```

## Set up a sample project using CLion

1. Open clion IDE and make new project
2. Setup clion toolchain and cmake configuration **Build, Execution, Deployment**

    Setup clion toolchain
    
4. Create directory main

    In this directory contain main.cpp or main.c of your esp program
    
    after create main.c/main.cpp, add another CMakeList.txt in this directory
    ```
    set(SOURCES "main.cpp")

    idf_component_register(SRCS ${SOURCES}
    INCLUDE_DIRS "")
        
    ```
    
5. Add CMakeList.txt inside application project

    ```
    cmake_minimum_required(VERSION 3.5)

    include($ENV{IDF_PATH}/tools/cmake/project.cmake)

    #set(CMAKE_FIND_ROOT_PATH /Users/your_user/.espressif/tools/xtensa-esp32-elf/esp-2021r1-8.4.0/xtensa-esp32-elf)
    set(CMAKE_C_COMPILER /Users/your_user/.espressif/tools/xtensa-esp32-elf/esp-2021r1-8.4.0/xtensa-esp32-elf/bin/xtensa-esp32-elf-gcc)
    set(CMAKE_ASM_COMPILER /Users/your_user/.espressif/tools/xtensa-esp32-elf/esp-2021r1-8.4.0/xtensa-esp32-elf/bin/xtensa-esp32-elf-g++)
    set(CMAKE_C_COMPILER /Users/your_user/.espressif/tools/xtensa-esp32-elf/esp-2021r1-8.4.0/xtensa-esp32-elf/bin/xtensa-esp32-elf-gcc)

    project(esp32t)

    include_directories("src")
    ```
7. 

