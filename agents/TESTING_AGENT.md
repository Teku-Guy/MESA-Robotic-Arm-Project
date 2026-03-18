# Testing Agent Tasks

## Test Creation
- Place unit tests in `test/` directory
- Follow naming: `test_<function_name>.cpp`
- Reference functions from `src/` for testing

## Test Execution
- Run all tests: `pio test` or `platformio test`
- Run single test: `pio test -e seeed_xiao_esp32s3 -t test_<test_name>`
- Verbose output: `pio test -v`

## Test Coverage
- Test edge cases and error conditions
- Verify function return values
- Check boundary conditions

## Debug Testing
- Use assertions for debug builds: `assert(condition)`
- Log test results with descriptive messages