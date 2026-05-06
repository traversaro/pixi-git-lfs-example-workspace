# pixi-git-lfs-example-workspace

A test workspace for reproducing struggles of using git dependencies that use Git LFS, both via pypi and pixi-build, related issues:

* https://github.com/prefix-dev/pixi/issues/2000

## Overview

This workspace tests whether Pixi correctly handles Git LFS files when installing a sample package (see https://github.com/traversaro/pixi-git-lfs-example-package) using two different methods, either via PyPI or pixi-build

## Quick Start

Install the dependencies and run the checks:

```bash
# Test 1: Install via pip (pypi-dependencies)
pixi run -e pypi check-stl-is-not-git-lfs-pointer

# Test 2: Install via Pixi build system (dependencies)
pixi run -e pixi-build check-stl-is-not-git-lfs-pointer
```

## Expected Results

- **Exit code 0**: ✓ File is correct binary content (no issue)
- **Exit code 1** or **Exit code 2**: ✗ File is a Git LFS pointer or does not exist (issue reproduced)
