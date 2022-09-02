# Introduction

## Windows

### Install Opencv

1. install ([opencv Releases](https://opencv.org/releases/))

![releases](resources/images/opencv/opencv-releases.png)

2. add environment variable

![env-1](resources/images/opencv/env-1.png)
![env-2](resources/images/opencv/env-2.png)
![env-3](resources/images/opencv/env-3.png)
![env-4](resources/images/opencv/env-4.png)

### Build

1. Command Line Compilation

get source code

```
git clone https://github.com/glddiv/Arducam_Opencv_Demo.git
cd Arducam_Opencv_Demo
```

Create the build directory in the project directory

```
cd build
cmake -DCMAKE_GENERATOR_PLATFORM=x64 ..
cmake --build . --config Release
```

After the compilation is complete, the following files will be generated in the build directory.

![product](resources/images/build_img/build_product.png)

Enter the Release directory to see the compiled executable program.

![exe](resources/images/build_img/build_exe.png)

Copy the compiled executable program to the same folder of the dynamic link library.

![copy_exe](resources/images/build_img/copy.png)

Execute the Arducam_Opencv_Demo program. According to the prompts, you need to set the configuration file path.

![run_exe](./resources/images/build_img/run.png)

2. cmake-gui

Use the cmake visualizer to generate project files.

Select the project directory and build directory.

![select_project](./resources/images/cmake_gui/select_project.png)

Generate project files.

![generate](./resources/images/cmake_gui/generate.png)

Select the generator.

![config](./resources/images/cmake_gui/config.png)

Open the project with Visual Studio.

![open_project](./resources/images/cmake_gui/open_project.png)

Debug 

First add command line arguments.

![add_command-1](./resources/images/cmake_gui/add_command_arg.png)
![add_command-2](./resources/images/cmake_gui/add_command_arg-2.png)

Set the dynamic link library path.

![Add_dll_path](./resources/images/cmake_gui/add_dll_path.png)

Add the dynamic library path, pay attention to be sure to add ***"PATH="*** in front.

![Add_dll_path](./resources/images/cmake_gui/add_dll_path-2.png)

perform debugging.

![debug](./resources/images/cmake_gui/debug.png)

Build

![build-1](./resources/images/cmake_gui/build-1.png)
![build-2](./resources/images/cmake_gui/build-2.png)

## Linux

## Installation dependence

1. opencv
2. arducam-usb-sdk-dev
3. arducam-config-parser-dev

```
sudo apt install libopencv-dev

curl -s --compressed "https://arducam.github.io/arducam_ppa/KEY.gpg" | sudo apt-key add -
sudo curl -s --compressed -o /etc/apt/sources.list.d/arducam_list_files.list "https://arducam.github.io/arducam_ppa/arducam_list_files.list"
sudo apt update
sudo apt install arducam-config-parser-dev arducam-usb-sdk-dev
```

### Build

```
mkdir build && cd build
cmake ..
make -j2
```

### Run

```
./Arducam_Opencv_Demo <path/config-file-name>
```