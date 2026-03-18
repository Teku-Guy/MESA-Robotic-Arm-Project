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
- Include one header per line for clarity

### Formatting
- Indent with 2 spaces (no tabs)
- Brace style: K&R (open brace on same line as function declaration)
- Maximum line length: 100 characters
- One statement per line unless logically related
- Add blank lines between logical sections
- No trailing whitespace at end of lines

### Naming Conventions
- Functions: `camelCase` (e.g., `myFunction`, `setupLED`)
- Variables: `camelCase` for locals, `snake_case` for globals/constants
- Constants: `UPPER_SNAKE_CASE` (e.g., `MAX_PIN_VALUE`, `DEFAULT_SPEED`)
- Files: `snake_case.cpp` or `PascalCase.h`
- Classes: `PascalCase`
- Enumerations: `PascalCase`

### Type Usage
- Use explicit types: `int`, `uint8_t`, `bool`, etc.
- Avoid implicit type conversion
- Use `const` for immutable values
- Prefer `void` over null pointers for function parameters
- Use `size_t` for array indices and sizes
- Use `uint8_t` or `uint16_t` for pin numbers

### Error Handling
- Check return values from critical operations
- Use assertions for debug builds: `assert(condition)`
- Return error codes from functions when appropriate
- Log errors using `Serial.println()` with descriptive messages
- Handle edge cases explicitly in public APIs
- Validate input parameters at function entry

### Comments & Documentation
- Add comments for complex logic and algorithms
- Document public APIs with brief descriptions
- Use single-line comments for inline explanations
- Avoid redundant comments that just repeat code
- Include file headers at top of source files

## Directory Structure
```
src/          - Main source files (main.cpp)
include/      - Public header files
lib/          - Private libraries
test/         - Unit tests
pio-build/    - Build output (auto-generated)
```

### File Organization
- Keep `main.cpp` for Arduino setup() and loop() functions
- Split helper functions into separate source files
- Place shared headers in `include/` directory
- Store private libraries in `lib/` directory
- Add unit tests in `test/` directory matching source names

## PlatformIO Specifics
- Board configuration in `platformio.ini` under `[env:seeed_xiao_esp32s3]`
- Framework: Arduino
- Platform: espressif32
- Use `pio lib install <library>` for dependencies
- Store library dependencies in platformio.ini `[lib_deps]` section
- Configure upload speed and port in `[upload_options]` if needed

## Git Workflow
- Repository: https://github.com/Teku-Guy/MESA-Robotic-Arm-Project.git
- Branch naming: `feature/description`, `bugfix/description`
- Commit messages: Present tense, concise, descriptive
- Before commit: Run `pio run` to ensure build passes
- Keep commits small and focused on single changes

## Agent Task Files
- `CODING_AGENT.md` - File creation and code implementation tasks
- `TESTING_AGENT.md` - Unit test creation and execution tasks
- `GIT_AGENT.md` - Repository management and commit tasks
- `DOCUMENTATION_AGENT.md` - Documentation maintenance tasks
- `PROJECT_GUIDELINES.md` - Complete code style guidelines reference

## Best Practices
1. Always test code locally before committing
2. Write unit tests for new functionality
3. Keep functions small and focused on single responsibility
4. Use meaningful variable and function names
5. Avoid magic numbers; use named constants
6. Log important state changes during debugging
7. Handle errors gracefully without crashing
8. Document non-obvious implementation decisions

## Debugging Tips
- Use `Serial.println()` for outputting variable values
- Check return codes from critical operations
- Add assertions to verify assumptions
- Use PlatformIO debug tools when available
- Keep serial monitor open during testing