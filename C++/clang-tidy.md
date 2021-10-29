## How to set up in a project
```bash
clang-tidy --checks=cppcoreguidelines-*,clang-analyzer-*,readability-* -p ./bin/ --dump-config --format-style=google >.clang-tidy
```

## Usage
```bash
cmake -S . -B ./bin/ -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
clang-tidy -p ./bin/ <path-to-source-file>
```
