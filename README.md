# csad2526ki409dmytrokhaulin21

A C++ project with math operations library and unit tests using GoogleTest.

## Prerequisites

Before running the CI scripts, ensure you have the following installed:

### Windows
- **CMake** (version 3.14 or higher)
  - Download from: https://cmake.org/download/
  - Or install via Chocolatey: `choco install cmake`
  - Or install via winget: `winget install Kitware.CMake`

### macOS
- **CMake** (version 3.14 or higher)
  - Install via Homebrew: `brew install cmake`
  - Or download from: https://cmake.org/download/

### Linux
- **CMake** (version 3.14 or higher)
  - Ubuntu/Debian: `sudo apt-get install cmake`
  - CentOS/RHEL: `sudo yum install cmake`
  - Or download from: https://cmake.org/download/

## CI Scripts

This project includes CI scripts for automated building and testing:

### Windows
- **ci.bat** - Batch script for Windows Command Prompt
- **ci.ps1** - PowerShell script for Windows PowerShell

### Unix/Linux/macOS
- **build.sh** - Shell script for Unix-based systems

## Usage

### Windows (Command Prompt)
```cmd
ci.bat
```

### Windows (PowerShell)
```powershell
.\ci.ps1
```

### Unix/Linux/macOS
```bash
./build.sh
```

## What the CI Scripts Do

1. **Create build directory** - Creates a `build` folder for out-of-source builds
2. **Configure project** - Runs `cmake ..` to configure the project
3. **Build project** - Runs `cmake --build .` to compile the code
4. **Run tests** - Executes `ctest --output-on-failure` to run all unit tests

## Manual Build Process

If you prefer to build manually:

```bash
mkdir build
cd build
cmake ..
cmake --build .
ctest --output-on-failure
```

## Project Structure

- `math_operations.h` - Header file for math operations
- `math_operations.cpp` - Implementation of math operations
- `tests/unit_tests.cpp` - Unit tests using GoogleTest
- `CMakeLists.txt` - CMake configuration file
- `ci.bat` - Windows batch CI script
- `ci.ps1` - Windows PowerShell CI script
- `build.sh` - Unix/Linux/macOS shell CI script
