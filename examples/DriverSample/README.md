# DriverSample Build Instructions

This sample can now be built with either **Visual Micro** in Visual Studio or **PlatformIO** in Visual Studio Code.

## Visual Micro (Visual Studio)

1. Open `DriverSample.sln` in Visual Studio.
2. Ensure the Visual Micro extension is installed and configured for your M5Stack board package.
3. Build, upload and monitor the sketch using the Visual Micro tool windows as before. The existing project structure has not changed, so no additional configuration is required.

## Visual Studio Code (PlatformIO)

1. Install the [PlatformIO extension](https://platformio.org/install/ide?install=vscode) for Visual Studio Code (the repository now recommends it automatically).
2. Open the repository folder in VS Code. The `examples/DriverSample/platformio.ini` file configures PlatformIO to build the sketch for the **M5Stack AtomS3**.
3. Use one of the provided tasks (`Terminal` → `Run Task…`) or the PlatformIO sidebar buttons to:
   - **Build**: `PIO Build (DriverSample)`
   - **Upload**: `PIO Upload (DriverSample)`
   - **Monitor**: `PIO Monitor (DriverSample)`
4. All project-specific libraries are pulled from the local `Libraries` directory through `lib_extra_dirs`, so no additional package installation is necessary.

### Command-line usage

PlatformIO can also be invoked directly from a terminal:

```sh
platformio run --project-dir examples/DriverSample          # Build
platformio run --target upload --project-dir examples/DriverSample  # Upload
platformio device monitor --project-dir examples/DriverSample       # Serial monitor
```

## Notes

- The sketch source continues to live in `DriverSample.ino` so Visual Micro compatibility is preserved.
- When using PlatformIO, any build artifacts will be placed in `examples/DriverSample/.pio` (ignored by Git).
- If you target a different board, adjust the `board` value inside `platformio.ini` accordingly.
