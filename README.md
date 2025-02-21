# action-autobuild

Build and package an autobuild project.

Example:
```yaml
name: Build

on:
  pull_request:
  tag:
    branches: [main]
    tags: [v*]

jobs:
  build:
    strategy:
      matrix:
        os: [windows-2022, macos-15, ubuntu-22.04]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: secondlife/action-autobuild@v5
        with:
          autobuild-version: 3.9.0 # PyPI version or git ref
```

For a full list of available action inputs see [action.yaml](action.yaml).
