# Interactive GCC (igcc)

## Overview
Interactive GCC is a read-eval-print loop (REPL) for C/C++. It works by manipulating a base source file with user commands, compiles the source after each modification using g++, then executes the resulting binary and collects its stdout & stderr.

## Project Architecture
- **Language**: Python 3.11
- **Build System**: setuptools (via pyproject.toml)
- **Package Manager**: pip
- **System Dependency**: gcc/g++ (C++ compiler)
- **Entry Point**: `igcc` command (defined in `igcc/run.py:repl`)

### Directory Structure
- `igcc/` - Main package
  - `run.py` - REPL loop and Runner class
  - `utils.py` - Utility functions (arg parsing, compiler command building)
  - `assets/` - Static assets
    - `boilerplate.h` - Default C++ header included in all compilations
    - `config.yaml` - Compiler and prompt configuration
- `tests/` - Test scripts
- `pyproject.toml` - Project metadata and dependencies
- `Makefile` - Development tasks (lint, format, test)

### Key Dependencies
- PyYAML - Config file parsing
- rich - Terminal output formatting
- jinja2 - Source code templating
- g++ - C++ compiler (system dependency)

## Running
The `igcc` command starts the interactive C/C++ REPL in the console.

## Recent Changes
- 2026-02-24: Added `.n` dot command to toggle line numbers for `.l` and `.L` listings
- 2026-02-22: Initial Replit setup - installed Python 3.11, gcc, and project dependencies
