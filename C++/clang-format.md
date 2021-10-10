# How to setup clang format in a project
```bash
clang-format -style=google -dump-config > .clang-format
```

## Apply rules
```bash
find ./src/ -iname *.h -o -iname *.cpp | xargs clang-format -i
```
