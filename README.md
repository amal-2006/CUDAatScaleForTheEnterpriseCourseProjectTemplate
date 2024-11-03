# Image Rotation using NVIDIA NPP with CUDA

## Overview# Image Rotation using NVIDIA NPP with CUDA

## Overview

This project demonstrates the use of NVIDIA Performance Primitives (NPP) library with CUDA to perform image rotation. The goal is to utilize GPU acceleration to efficiently rotate a given image by a specified angle, leveraging the computational power of modern GPUs. The project is a part of the CUDA at Scale for the Enterprise course and serves as a template for understanding how to implement basic image processing operations using CUDA and NPP.

## Code Organization

```bin/```
This folder should hold all binary/executable code that is built automatically or manually. Executable code should have use the .exe extension or programming language-specific extension.

```data/```
This folder should hold all example data in any format. If the original data is rather large or can be brought in via scripts, this can be left blank in the respository, so that it doesn't require major downloads when all that is desired is the code/structure.

```lib/```
Any libraries that are not installed via the Operating System-specific package manager should be placed here, so that it is easier for inclusion/linking.

```src/```
The source code should be placed here in a hierarchical fashion, as appropriate.

```README.md```
This file should hold the description of the project so that anyone cloning or deciding if they want to clone this repository can understand its purpose to help with their decision.

```INSTALL```
This file should hold the human-readable set of instructions for installing the code so that it can be executed. If possible it should be organized around different operating systems, so that it can be done by as many people as possible with different constraints.

```Makefile or CMAkeLists.txt or build.sh```
There should be some rudimentary scripts for building your project's code in an automatic fashion.

```run.sh```
An optional script used to run your executable code, either with or without command-line arguments.

## Key Concepts

Performance Strategies, Image Processing, NPP Library

## Supported SM Architectures

[SM 3.5 ](https://developer.nvidia.com/cuda-gpus)  [SM 3.7 ](https://developer.nvidia.com/cuda-gpus)  [SM 5.0 ](https://developer.nvidia.com/cuda-gpus)  [SM 5.2 ](https://developer.nvidia.com/cuda-gpus)  [SM 6.0 ](https://developer.nvidia.com/cuda-gpus)  [SM 6.1 ](https://developer.nvidia.com/cuda-gpus)  [SM 7.0 ](https://developer.nvidia.com/cuda-gpus)  [SM 7.2 ](https://developer.nvidia.com/cuda-gpus)  [SM 7.5 ](https://developer.nvidia.com/cuda-gpus)  [SM 8.0 ](https://developer.nvidia.com/cuda-gpus)  [SM 8.6 ](https://developer.nvidia.com/cuda-gpus)

## Supported OSes

Linux, Windows

## Supported CPU Architecture

x86_64, ppc64le, armv7l

## CUDA APIs involved

## Dependencies needed to build/run
[FreeImage](../../README.md#freeimage), [NPP](../../README.md#npp)

## Prerequisites

Download and install the [CUDA Toolkit 11.4](https://developer.nvidia.com/cuda-downloads) for your corresponding platform.
Make sure the dependencies mentioned in [Dependencies]() section above are installed.

## Build and Run

### Windows
The Windows samples are built using the Visual Studio IDE. Solution files (.sln) are provided for each supported version of Visual Studio, using the format:
```
*_vs<version>.sln - for Visual Studio <version>
```
Each individual sample has its own set of solution files in its directory:

To build/examine all the samples at once, the complete solution files should be used. To build/examine a single sample, the individual sample solution files should be used.
> **Note:** Some samples require that the Microsoft DirectX SDK (June 2010 or newer) be installed and that the VC++ directory paths are properly set up (**Tools > Options...**). Check DirectX Dependencies section for details."

### Linux
The Linux samples are built using makefiles. To use the makefiles, change the current directory to the sample directory you wish to build, and run make:
```
$ cd <sample_dir>
$ make
```
The samples makefiles can take advantage of certain options:
*  **TARGET_ARCH=<arch>** - cross-compile targeting a specific architecture. Allowed architectures are x86_64, ppc64le, armv7l.
    By default, TARGET_ARCH is set to HOST_ARCH. On a x86_64 machine, not setting TARGET_ARCH is the equivalent of setting TARGET_ARCH=x86_64.<br/>
`$ make TARGET_ARCH=x86_64` <br/> `$ make TARGET_ARCH=ppc64le` <br/> `$ make TARGET_ARCH=armv7l` <br/>
    See [here](http://docs.nvidia.com/cuda/cuda-samples/index.html#cross-samples) for more details.
*   **dbg=1** - build with debug symbols
    ```
    $ make dbg=1
    ```
*   **SMS="A B ..."** - override the SM architectures for which the sample will be built, where `"A B ..."` is a space-delimited list of SM architectures. For example, to generate SASS for SM 50 and SM 60, use `SMS="50 60"`.
    ```
    $ make SMS="50 60"
    ```

*  **HOST_COMPILER=<host_compiler>** - override the default g++ host compiler. See the [Linux Installation Guide](http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#system-requirements) for a list of supported host compilers.
```
    $ make HOST_COMPILER=g++
```


## Running the Program
After building the project, you can run the program using the following command:

```bash
Copy code
make run
```

This command will execute the compiled binary, rotating the input image (Lena.png) by 45 degrees, and save the result as Lena_rotated.png in the data/ directory.

If you wish to run the binary directly with custom input/output files, you can use:

```bash
- Copy code
./bin/imageRotationNPP --input data/Lena.png --output data/Lena_rotated.png
```

- Cleaning Up
To clean up the compiled binaries and other generated files, run:


```bash
- Copy code
make clean
```

This will remove all files in the bin/ directory.


This project is designed to explore various image filtering techniques using the CUDA NPP (NVIDIA Performance Primitives) Library. The project currently implements the following image filters:

Median Filter (median): This filter reduces noise in an image while preserving edges by replacing each pixel's value with the median value of the neighboring pixels.

Sharpening Filter (sharpen): This filter enhances the edges of an image by emphasizing the differences between neighboring pixel values, making the image appear crisper.

Laplacian Filter (laplacian): A filter that detects edges by calculating the second derivative of the image intensity, highlighting regions of rapid intensity change.

The project allows users to specify an input image file (in .PGM format) and choose the desired filter.

## Example Filter Output

Here are some example images showing the effects of the filters applied:

### Example of Median Filter

![image](https://github.com/user-attachments/assets/ffb8c57d-8af8-4fdc-b49b-38b2bd20ef97)

### Example of Sharpening Filter

![image](https://github.com/user-attachments/assets/67a866f4-efab-40b3-8430-be116a619c32)

### Example of Laplacian Filter

![image](https://github.com/user-attachments/assets/61448009-9243-4e1d-90e4-2a1dd2a1c7cc)

## Directory Structure

## Directory Structure

* **[`bin/`](./bin/)**: Executable files generated during the build process.
  
* **[`data/`](./data/)**: Example data files.
  
* **[`lib/`](./lib/)**: External libraries not managed by package managers.
  
* **[`src/`](./src/)**: Hierarchical source code for the project.
  
* **[`README.md`](./README.md)**: Documentation outlining project usage and setup.
  
* **[`Makefile`](./Makefile)** Automating the build process.
  
* **[`run.sh`](./run.sh)**: Optional script for executing compiled code.

## Running the Project

Running the Project will generate an output log file located at **[`./output/output.log`](./output/output.log)**
To run the project, you have a couple of options:

1. **[`run.sh`](./run.sh)**:

   ```sh
   sh run.sh
   ```

2. **[`Makefile`](./Makefile)**
  
   ```sh
   make clean build
   make run ARGS="-input=./data/Lena.pgm -kernel=laplacian" >> output/output.log
   ```

   **Note:** When no -kernel argument is specified all kernels will be executed fot the given input image

   ```sh
   make run ARGS="-input=./data/Lena.pgm" >> output/output.log
   ```

**Context:** This project was developed as part of the **CUDA at Scale for the Enterprise** course offered by **Johns Hopkins University**.

**Note:** This project is intended to run within the Coursera Lab environment, which comes with a pre-configured CUDA setup. The structure of the project draws inspiration from the [CUDA at Scale for the Enterprise Course Project Template](https://github.com/PascaleCourseraCourses/CUDAatScaleForTheEnterpriseCourseProjectTemplate).

## Future Implementations

Future enhancements may include adding support for filters on additional file formats, such as `.bmp` and `.png`..
