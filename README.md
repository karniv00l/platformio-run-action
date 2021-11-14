# PlatformIO Run

GitHub Action for PlatformIO Run.

## Usage

`.github/workflows/platformio-build.yml`

```yml
name: PlatformIO

on: pull_request

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: PlatformIO Run
        uses: karniv00l/platformio-run-action@0.1.0
        with:
          environments: "teensy35,teensy36,teensy41"
          targets: "teensy35,teensy36,teensy41"
          project-dir: "./some_dir"
          project-conf: "./some_dir/custom.ini"
          jobs: 6
          silent: false
          verbose: true
          disable-auto-clean: false
```

## Inputs

```yml
environments:
  description: Process specified environments (comma separated).
  required: false
targets:
  description: Process specified targets (comma separated).
  required: false
project-dir:
  description: Specify the path to project directory. By default, project-dir is equal to current working directory (CWD).
  required: false
project-conf:
  description: Process project with a custom platformio.ini
  required: false
jobs:
  description: Control a number of parallel build jobs. Default is a number of CPUs in a system.
  required: false
silent:
  description: Suppress progress reporting.
  required: false
verbose:
  description: Shows detailed information when processing environments.
  required: false
disable-auto-clean:
  description: Disable auto-clean of build_dir when platformio.ini or src_dir (project structure) have been modified.
  required: false
```
