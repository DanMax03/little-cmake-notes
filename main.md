# Notes
## target
The target is a file or files which will be created after executing cmake command
## cmake_minimum_required
Usage: `cmake_minimum_required(VERSION 3.1)`

Just specifying minimal version which is acceptable for building a target
## configure_file
Usage: `project(project_name VERSION 1.0.0)` and `configure_file(header.h.in header.h)`

In header.h.in we write `#define` commands with cmake macros:
```
#define project_name_VERSION_MAJOR @project_name_VERSION_MAJOR@
#define project_name_VERSION_MINOR @project_name_VERSION_MINOR@
```

Things inside of @@ are cmake macros. While building, it will be replaced with specified string (e.g. 1.0.0)
