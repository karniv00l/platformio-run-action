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
      - uses: karniv00l/platformio-run-action@0.1.0
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
