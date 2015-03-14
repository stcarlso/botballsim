While the built-in [KISS-C](http://www.botball.org/kiss) simulator allows basic Botball robot simulation, the lack of sensors and consistent physics make the testing of real programs difficult. This project seeks to create a new simulator which more closely follows real-world behavior and allows improved features and sensor usage.

For a quick start, download the latest release from the "Featured Downloads" section, or visit the QuickStart page.

Features include:
  * Sensors:
    * Starting light
    * Physical touch
    * IR distance (ET)
    * IR reflectance (top hat)
  * Realistic collision physics
  * Cross-platform architecture
  * Improved graphics
  * Loads mostly unmodified user C code, and pausing/stopping does not require ` kissSimEnablePause() `