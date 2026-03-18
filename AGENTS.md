# AGENTS.md - MESA Robotic Arm Project Guidelines

## Project Overview
PlatformIO project for ESP32-S3 (Seeed Xiao ESP32S3) using Arduino framework.

## Build/Lint/Test Commands
- **Build:** `pio run` or `platformio run`
- **Upload:** `pio upload` or `platformio upload`
- **Monitor Serial:** `pio monitor` or `platformio monitor`
- **Clean:** `pio clean` or `platformio clean`
- **Unit Tests:** `pio test` or `platformio test`
- **Run Single Test:** `pio test -e seeed_xiao_esp32s3 -t test_<test_name>`
  - Example: `pio test -e seeed_xiao_esp32s3 -t test_myFunction`
- **Test with verbose output:** `pio test -v`

## Code Style Guidelines

### Imports & Includes
- Use Arduino framework includes: `#include <Arduino.h>`
- Project headers in double quotes: `#include "header.h"`
- Place all includes at the top of files
- Group system includes first, then project headers

### Formatting
- Indent with 2 spaces
- Brace style: K&R (open brace on same line as function declaration)
- Maximum line length: 100 characters
- One statement per line unless logically related
- Add blank lines between logical sections

### Naming Conventions
- Functions: `camelCase` (e.g., `myFunction`, `setupLED`)
- Variables: `camelCase` for locals, `snake_case` for globals/constants
- Constants: `UPPER_SNAKE_CASE` (e.g., `MAX_PIN_VALUE`)
- Files: `snake_case.cpp` or `PascalCase.h`
- Classes: `PascalCase`

### Type Usage
- Use explicit types: `int`, `uint8_t`, `bool`, etc.
- Avoid implicit type conversion
- Use `const` for immutable values
- Prefer `void` over null pointers for function parameters

### Error Handling
- Check return values from critical operations
- Use assertions for debug builds: `assert(condition)`
- Return error codes from functions when appropriate
- Log errors using `Serial.println()` with descriptive messages
- Handle edge cases explicitly in public APIs

### Directory Structure
```
src/          - Main source files (main.cpp)
include/      - Public header files
lib/          - Private libraries
test/         - Unit tests
pio-build/    - Build output (auto-generated)
```

### PlatformIO Specifics
- Board configuration in `platformio.ini` under `[env:seeed_xiao_esp32s3]`
- Framework: Arduino
- Platform: espressif32
- Use `pio lib install <library>` for dependencies
- Store library dependencies in platformio.ini `[lib_deps]` section

### Git Workflow
- Repository: https://github.com/Teku-Guy/MESA-Robotic-Arm-Project.git
- Branch naming: `feature/description`, `bugfix/description`
- Commit messages: Present tense, concise, descriptive
- Before commit: Run `pio run` to ensure build passes
