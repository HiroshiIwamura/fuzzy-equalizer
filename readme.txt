# Fuzzy Audio Equalizer

Reference MATLAB implementation of a fuzzy-controlled audio equalizer.

[日本語版 README](README.md)

[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=HiroshiIwamura/fuzzy-equalizer&file=FEQU_v2.mlapp)

* A free MathWorks account is required to use MATLAB Online.
* MATLAB Online allows you to explore the fuzzy inference process and graphical visualization.
* Real-time audio playback requires the desktop version of MATLAB and Audio Toolbox.

---

## Overview

This repository provides a MATLAB implementation of a fuzzy inference based audio equalizer.

The original concept was developed and patented in Japan in 1989. This implementation is provided by the original inventor as a reference implementation.

For a detailed technical explanation, please refer to:

* https://note.com/leftbank/n/n2b16648c9b39

### Demo Videos

* https://www.youtube.com/watch?v=ImQW7U3SLto
* https://www.youtube.com/watch?v=WyPJTxr6pvw

---

## Features

* Audio equalization based on fuzzy inference
* No training data required
* Real-time operation
* Low computational cost
* Real-time visualization of the inference process
* Graph display can be enabled or disabled
* Separation of inference engine and knowledge base
* Can be explored directly in MATLAB Online

Unlike modern machine-learning approaches, this system is entirely rule-based and requires no training process.

Its low computational complexity makes it suitable for real-time processing, embedded systems, and DSP implementations.

---

## Technical Background

This project applies fuzzy inference techniques to audio equalization.

In many conventional DSP systems, significant changes in behavior often require modifications to the processing algorithm itself.

In contrast, fuzzy systems allow relatively independent design of:

* Inference mechanism
* Membership functions
* IF-THEN rules

This separation makes it possible to improve and refine the knowledge base without redesigning the inference engine itself.

---

## Current Status

The MATLAB implementation included in this repository is fully capable of real-time operation.

The inventor has also developed a JUCE/C++ audio plug-in implementation based on the same concept.

However, the JUCE implementation is not included in this repository.

While the system is functional, there remains room for further refinement of the fuzzy rules and membership functions from an audio engineering perspective.

One of the key advantages of fuzzy inference is that the rule set and knowledge base can continue to evolve without requiring changes to the inference engine itself.

For this reason, this repository is provided as a reference implementation intended for research, experimentation, and further development.

---

## MATLAB Online

This project can be opened and explored using MATLAB Online.

Requirements:

* Free MathWorks account
* No local MATLAB installation required

Available in MATLAB Online:

* Fuzzy inference processing
* Visualization of inference results
* Graph display
* Parameter experimentation

Not available in MATLAB Online:

* Real-time audio playback
* Audio device output

This limitation exists because `audioDeviceWriter` is not supported in MATLAB Online.

To experience the actual audio processing, the desktop version of MATLAB and Audio Toolbox are required.

---

## Performance Notes

The application can perform real-time audio playback and real-time visualization simultaneously.

Graph display can be enabled or disabled.

### Graph ON

* Real-time visualization of inference activity
* Higher CPU usage
* Audio dropouts may occur depending on system performance

### Graph OFF

* Visualization disabled
* Lower CPU usage
* More stable real-time operation

In the author's testing environment, newer MATLAB versions tend to handle real-time visualization more efficiently.

Examples:

* MATLAB R2024a: occasional audio dropouts may occur when graph visualization is enabled
* MATLAB R2026a: significantly improved performance under similar conditions

Actual performance depends on hardware, operating system, and audio device configuration.

---

## Screenshots

### MATLAB Implementation

<img width="1602" height="989" alt="MATLAB GUI" src="https://github.com/user-attachments/assets/a98d14e1-f9c2-4859-9c32-fda53640fe0d" />

<img width="840" height="900" alt="Fuzzy Inference Graph" src="https://github.com/user-attachments/assets/547a9884-1038-47ea-bddc-6958800bb886" />

### JUCE/C++ Plug-in Implementation (not included in this repository)

<img width="802" height="528" alt="FEQU VST" src="https://github.com/user-attachments/assets/13ac1c8a-b1a5-47dc-9fd9-5c2c474a59a9" />

---

## Requirements

* MATLAB R2023a or later
* Audio Toolbox (for real-time audio processing)

---

## Getting Started

1. Clone or download this repository.
2. Open the project in MATLAB.
3. Launch `FEQU_v2.mlapp`.
4. Load a stereo audio file.
5. Adjust parameters and observe both the audio response and inference behavior.

---

## Support

This repository is provided as a technical reference and research resource.

Bug fixes, feature additions, pull request reviews, and ongoing maintenance are not guaranteed.

---

## Contact

For technical discussions, collaboration opportunities, licensing inquiries, or commercial use:

AudiiSion Sound Lab.

https://www.audiision.com/

---

## License

MIT License

Copyright (c) 2026 Hiroshi Iwamura

See the LICENSE file for details.
