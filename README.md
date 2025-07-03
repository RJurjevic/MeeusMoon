# MeeusMoon

A Windows application to visualize and compute Moon phases, eclipses, and astronomical events using algorithms from Jean Meeus' classic book *Astronomical Formulae for Calculators*.

## 🌕 Overview

This repository archives the development and executables of a C++ MFC-based program that:

- Draws the current phase of the Moon in a resizable window.
- Computes solar and lunar events such as rise/set times, twilight, eclipses, and seasonal markers.
- Updates detailed logs in text files for real-time astronomical insights.
- Includes a command-line utility for advanced Moon calculations (`MMoon.exe`).

All astronomical computations are based on formulas from Jean Meeus' book (*astronomical-formulae.pdf*, included), with expected accuracy within 2–3 minutes.

---

## 📦 Release Contents

Download the release `v4.1` and extract `Astronomy.zip`. It contains:

```

Astronomy.zip
├── Astronomy/
│   ├── Projects/                          # Latest full source code
│   ├── Projects/CC++/Astronomy/build.txt  # How to build using Visual Studio 2022
│   ├── astronomical-formulae.pdf          # Jean Meeus' book (formulas used)
│   ├── Meeus.zip                          # Older version of the source code
│   ├── MeeusMoon.zip                      # Old Windows executables (legacy)
├── MeeusMoon.zip                          # Latest Windows executables (2023)

```

> 🔧 **Note:** `MeeusMoon.zip` is in the **root** of `Astronomy.zip`, not inside the `Astronomy/` folder.  
> To run the latest version, extract it separately into a folder like `C:\Astronomy\MeeusMoon\`.

---

## 🚀 Getting Started

### Run the Application

1. Extract `MeeusMoon.zip` (from the root of the archive) into a folder like `C:\Astronomy\MeeusMoon\`.
2. Run `MoonPhase.exe`.
3. Resize or minimize the window — the display updates Moon phases in real time.

**Features shown in the window:**

- Current Moon phase and illumination.
- Apparent Moon size compared to the Sun.
- Eclipse possibility indicators:
  - Blue dotted lines: min/max Moon sizes
  - Grey dotted line: average Moon size
  - Yellow line: Sun's size
- Real-time logs written to:
  - `actual.txt`: Daily info (rise/set times, eclipses, solstices, etc.)
  - `daily.txt`: Daily logs
  - `yearly.txt`: Annual summaries

**Customize your location and time zone** in `place.txt` (only the first line is used; Burgess Hill is set by default).

**Extra info:**  
Click the top-left corner → **About Moon Phase** to view:
- Fraction illuminated (0.00 = New Moon, 1.00 = Full Moon)
- Bright limb angle
- Apparent diameters:
  - Moon
  - Sun
  - Difference
  - Comparison to min/max Moon size

---

### Command-Line Utility: `MMoon.exe`

Use `MMoon.exe` from the console to compute Moon data programmatically.

**Usage:**

```

MMoon.exe \[-d] \[-k] \[-S] \[-P] < inputfile > outputfile

```

Great for scripting, automation, and scientific calculations.

---

## 🔧 Building from Source

To build the full project, use **Microsoft Visual Studio 2022**.

### Step-by-step:

1. Build the static library:
```

Projects\CC++\Astronomy\Meeus\Meeus.sln

```

2. Build both executables:
```

Projects\CC++\Astronomy\MMoon\MMoon.sln
Projects\CC++\Astronomy\MoonPhase\MoonPhase.sln

```

**Output folders:**
- `Meeus.lib` → in `x64\Release\`
- `MMoon.exe` → in `x64\Release\`
- `MoonPhase.exe` → in `x64\Release\`

---

## 🌌 Extending the Software

The software is modular. You can extend it with other celestial objects (e.g. stars, planets) via a C++ abstract base class.

### To add a new celestial object:

1. Inherit from the abstract celestial class.
2. Implement two pure virtual methods:
- One to compute the object's position.
- One to compute its apparent semi-diameter.

Once implemented, your object will automatically support:
- Rise and set time calculations
- Horizon detection
- Size comparisons

**Example:**  
- The star **Pollux** is included as a simple reference.
- Planets can be added by following the same model as the Moon, using formulas from the Meeus book.

---

## 📜 License and Attribution

- **Author:** Robert Jurjevic, M&R Research Team  
- **Years:** 1995–2023  
- **Formulas:** Based on Jean Meeus' *Astronomical Formulae for Calculators* (PDF included)

This project is licensed under the **MIT License** — see the `LICENSE` file for terms.

---

## 🛰️ Notes on Accuracy

The software is based on Meeus' algorithms, offering high-quality approximations suitable for educational and enthusiast use.

- **Typical accuracy:** ±2–3 minutes
- **Covered calculations:**
- Moon phases and eclipses
- Solstices and equinoxes
- Rise and set times
- Twilight intervals

For professional-grade precision, compare with datasets such as `ais110.pdf`.

---

Enjoy exploring the Moon and the sky above!
