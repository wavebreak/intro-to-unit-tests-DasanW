[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=18068271)
# C++ Calculator with Unit Tests

This project demonstrates a simple calculator implementation with comprehensive unit testing using Google Test framework. It serves as an example of how to structure a C++ project with unit tests, CMake build system, and development containers.

## Project Structure 
```
├── .devcontainer/ # Development container configuration
│ └── devcontainer.json
├── src/ # Source code
│ ├── calculator.cpp
│ └── calculator.h
├── tests/ # Unit tests
│ └── calculator_test.cpp
├── CMakeLists.txt # CMake configuration
├── Dockerfile # Container definition
├── main.cpp # Main program
└── README.md
```

## Prerequisites

- Docker Desktop
- Visual Studio Code
- VS Code Extension: Remote - Containers

## Getting Started

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. Open in VS Code:
   ```bash
   code .
   ```

3. When VS Code prompts, click "Reopen in Container" or:
   - Press F1
   - Type "Remote-Containers: Reopen in Container"
   - Press Enter

   This will build the development container with all necessary dependencies (may take a few minutes on first run).

## Building the Project

Once inside the development container:

1. Create and enter the build directory:
   ```bash
   mkdir build
   cd build
   ```

2. Configure the project with CMake:
   ```bash
   cmake ..
   ```

3. Build the project:
   ```bash
   make
   ```

This will create two executables:
- `calculator_demo`: The main program
- `calculator_test`: The unit test executable

## Running the Program

From the build directory:

```bash
./calculator_demo
```

This will run the demo program showing basic calculator operations.

## Running the Tests

There are several ways to run the tests:

1. Direct execution:
   ```bash
   ./calculator_test
   ```

2. Using CTest:
   ```bash
   ctest --output-on-failure
   ```

3. For verbose test output:
   ```bash
   ./calculator_test --gtest_color=yes
   ```

## Test Coverage

The test suite covers:

- Basic arithmetic operations:
  - Addition
  - Subtraction
  - Multiplication
  - Division

- Edge cases:
  - Operations with zero
  - Negative numbers
  - Division by zero exception

## Development Container Features

The included development container provides:
- GCC/G++ compiler toolchain
- CMake build system
- Google Test framework
- Essential VS Code extensions for C++ development

## Troubleshooting

1. If the container fails to build:
   ```bash
   docker system prune -a
   ```
   Then try reopening in container again.

2. If CMake can't find GTest:
   ```bash
   sudo apt-get update
   sudo apt-get install libgtest-dev
   cd /usr/src/gtest
   sudo cmake CMakeLists.txt
   sudo make
   sudo cp lib/*.a /usr/lib
   ```

3. If build fails with permission errors:
   ```bash
   sudo chown -R $(whoami) build/
   ```

## Contributing

1. Create a new branch for your feature
2. Add or modify tests as needed
3. Ensure all tests pass
4. Submit a pull request

## License

This project is open source and available under the MIT License.

## Contact

For questions or support, please open an issue in the repository.

