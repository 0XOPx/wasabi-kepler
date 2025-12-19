<h1>⚠️ IMPORTANT (For Users of NVIDIA Kepler Graphics Cards) 
This fork has been created specifically for NVIDIA Kepler graphics cards (GT 6xx or GT 7xx). 
<br>
<br>
⚠️ This repository will not be able to follow any changes to Nvidia Kepler graphics cards from an upstream source. If you are using a Nvidia Kepler graphics card, do not perform an in-application upgrade or switch to regular Wasabi builds.
<br>
<br>
Wasabi from upstream can potentially cause crashes on Nvidia Kepler graphics cards since these cards attempt to use a Vulkan present mode not supported by the hardware (using either the PRESENT_MODE_IMMEDIATE or PRESENT_MODE_MAILBOX). The only present mode guaranteed to be supported by Nvidia Kepler graphics cards is FIFO present mode.
<br>
<br>
The fork adds fallback support to FIFO compliant with Vulkan specifications, allowing Wasabi to operate properly on Nvidia Kepler graphics cards. This issue does not affect newer graphics card models.</h1>
<br>
<br>
Credits to:

- [Arudano](https://github.com/arduano)
- [MBMS (MyBlackMIDIScore)](https://github.com/MyBlackMIDIScore)
- [Kaydax (Ay shoutout to him, he made Chikara!)](https://github.com/Kaydax)
- [StratusFearMe21](https://github.com/StratusFearMe21)
- [PatoFlamejanteTV](https://github.com/PatoFlamejanteTV)
- [People-11](https://github.com/People-11)
- [Zwatotem](https://github.com/Zwatotem)
<p align="center">--- Now the actual README. ---</p>
<h1 align="center">Wasabi (For Kepler)</h1>
<p align="center"><img src="/assets/logo.svg" width="128"/></p>
<p align="center">Wasabi is a modern and fast real-time MIDI player written in Rust.</p>
<p align="center">
<img alt="GitHub License" src="https://img.shields.io/github/license/BlackMIDIDevs/wasabi">
<img alt="GitHub Release" src="https://img.shields.io/github/v/release/BlackMIDIDevs/wasabi">
<img alt="GitHub Downloads (all assets, all releases)" src="https://img.shields.io/github/downloads/BlackMIDIDevs/wasabi/total">
</p>

## Features

- Extremely fast and optimized rendering using Vulkan
- Easy to use and configurable
- Integrated MIDI synthesizer (XSynth), alongside with KDMAPI and MIDI device support
- Partial support for Zenith color palettes

## Installation

Wasabi is a portable application and does not require an installation.
Your system must support Vulkan.

### Option A *(recommended)*

You can download and run a pre-built binary of Wasabi from the [releases page.](https://github.com/BlackMIDIDevs/wasabi/releases)

### Option B *(advanced)*

You can build Wasabi yourself by following these steps:

- Clone the repository using `git clone https://github.com/BlackMIDIDevs/wasabi.git` (or [download as a ZIP from GitHub](https://github.com/BlackMIDIDevs/wasabi/archive/refs/heads/master.zip))
- Required tools:
    - [Rust toolchain](https://rustup.rs/)
    - [Vulkan SDK](https://vulkan.lunarg.com/)
    - [CMake **3.X**](https://cmake.org/)
    - [Ninja](https://ninja-build.org/)
    - (C++ build tools for-)[Visual Studio 17+](https://visualstudio.microsoft.com/) (Windows only)
- Inside the project directory run the following command to build Wasabi: `cargo build --release`
    - Optionally you can add `RUSTFLAGS="-C target-cpu=native"` to your environment before compiling to optimize XSynth for your specific CPU
- After the compilation is finished, you will find the binary under `./target/release`

## Usage

- Before you can play a MIDI, you need to add soundfonts to the synthesizer by going to `Menu -> Settings -> SoundFonts`
- To open a MIDI, click the folder icon on the top left, or press `Ctrl+O` on your keyboard
- To find out about other keyboard shortcuts, head to `Menu -> Shortcuts`

## Screenshot

<p align="center"><img src="/assets/screenshot.png"/></p>

## License
Wasabi is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html#license-text).
