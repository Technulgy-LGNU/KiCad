# Technulgy KiCad Resources

This repository is the shared home for our reusable KiCad resources:

- component libraries containing symbols, footprints, and 3D models;
- design blocks for reusable schematic sections; and
- the reference project used to maintain our design rules.

We use these resources instead of copying parts between projects. This keeps symbols,
footprints, 3D models, proven circuits, and design constraints consistent across
our hardware designs.

## Repository structure

| Path | Contents |
| --- | --- |
| `KiCad - Libraries/` | Company libraries containing component sublibraries (symbols, footprints, and 3D models) |
| `KiCad - Design Blocks/` | Reusable schematic design blocks grouped by function |
| `KiCad - Design Rules/` | Reference KiCad project for shared board and schematic rules |
| `SETUP.md` | Instructions for connecting these resources to KiCad |

## Setup

Follow [SETUP.md](SETUP.md) to define `TECHNULGY_KICAD` and add the symbol,
footprint, and design-block library tables to KiCad.

## Status legend

Mark the checkboxes in the inventory tables as work progresses:

- **WIP** — actively being created or changed; not ready for general use.
- **Finished** — reviewed against the datasheet and ready to use in a design.
- **Tested** — verified in a manufactured assembly or equivalent hardware test.

Normally, mark only **WIP** while an item is being developed. Clear **WIP** and
mark **Finished** when the review is complete. **Tested** may then be marked after
physical verification. Add a short note when a status needs context.

## Component libraries

The top-level library is the company or existing library group. Each component
inside it is listed as a sublibrary. The availability columns describe the files
currently present in the repository; they are not quality or verification
results.

| Company library | Sublibrary / component | Symbol | Footprint | 3D model | WIP | Finished | Tested | Notes |
| --- | --- | :---: | :---: | :---: | :---: | :---: | :---: | --- |
| `AnalogDevices` | `LT3751EFE` | Yes | Yes | Yes | [x] | [ ] | [ ] | Footprint is named `SOP65P640X120-21N` |
| `AnalogDevices` | `LT8638S` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `BNO055` | `BNO055` | Yes | Yes | Yes | [ ] | [x] | [x] | |
| `DiodesIncorperated` | `AP22653W6` | Yes | No | No | [ ] | [x] | [ ] | Linked with generic footprint and 3D model; symbol is currently named `AP2553W6` |
| `E-Switch` | `500SSP1S4M6QEA` | Yes | Yes | Yes | [x] | [ ] | [ ] | Symbol is named `500ssp2`; footprint is not assigned in the symbol; 3D-model path is relative |
| `InfineonTechnologies` | `IFX9201SG` | Yes | Yes | Yes | [x] | [ ] | [ ] | Footprint is named `PG-DSO-12-17` |
| `MagJack-A70-112-331N126` | `MagJack-A70-112-331N126` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `Maxon` | `MAXON_ESCON24/2` | Yes | Yes | Yes | [ ] | [x] | [x] | Includes models with and without headers |
| `Molex` | `203560-0503` | Yes | Yes | Yes | [ ] | [x] | [x] | |
| `Molex` | `52745-1496` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `Molex` | `73251-2121` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `Onsemi` | `FDD86367-F085` | Yes | Yes | Yes | [x] | [ ] | [ ] | Footprint is named `TO-252-3` |
| `PJRC` | `Teensy_4.0` | Yes | Yes | Yes | [ ] | [x] | [ ] | Footprint is named `TEENSY_4.0`; 3D model includes headers |
| `PJRC` | `TEENSY_4.1` | Yes | Yes | Yes | [ ] | [x] | [x] | Updated symbol and footprint; 3D model includes headers and is now named `Teensy_4.1_(With Headers).stp` |
| `Qorvo` | `ACT88329` | Yes | Yes | Yes | [x] | [ ] | [ ] | |
| `Qorvo` | `QM35825` | Yes | Yes | Yes | [x] | [ ] | [ ] | |
| `RaspberryPi_CM5` | `CM5_J1`, `CM5_J2` | Yes | Yes | Yes | [ ] | [ ] | [ ] | Two CM5 connector symbols and footprints |
| `RaspberryPi_CM5` | `503398-1892` | No | Yes | No | [x] | [ ] | [ ] | Additional Molex connector footprint |
| `RCJ Communication Module` | `RCJ-COM-2024` | Yes | Yes | Yes | [ ] | [x] | [x] | Includes models with and without headers |
| `RT9742GGJ5` | `RT9742GGJ5` | Yes | Yes | Yes | [ ] | [x] | [ ] | Linked with a generic footprint |
| `STMicroelectronics` | `LIS2MDLTR` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `STMicroelectronics` | `LSM6DSV320XTR` | Yes | Yes | Yes | [ ] | [x] | [ ] | Footprint is named `LSM6DSV16BXTR` |
| `TDK` | `DEA167240BT-2380B1` | Yes | Yes | Yes | [ ] | [x] | [ ] | 3D model is embedded in the footprint && Generic one, because no official one published  |
| `TexasInstruments` | `TXU0304BQAR` | Yes | Yes | Yes | [ ] | [x] | [ ] | |

## Design blocks

| Category | Design block | WIP | Finished | Tested | Notes |
| --- | --- | :---: | :---: | :---: | --- |
| Communication | `QM-RF-Connector` | [x] | [ ] | [ ] | |
| Communication | `QM35825` | [x] | [ ] | [ ] | Includes the ACT88329 voltage regulator |
| IC | `RP CM5` | [ ] | [x] | [ ] | |
| IC | `STM32G431RB` | [ ] | [x] | [ ] | |
| Power | `+3V3 LDO 1A` | [ ] | [x] | [ ] | |
| Power | `+5V Buck 10A` | [ ] | [x] | [ ] | |
| Power | `ACT88329` | [x] | [ ] | [ ] | For the Qorvo QM35825 |

The `Misc` design-block library is configured but does not currently contain
tracked design blocks.

## Design rules

| Resource | WIP | Finished | Tested | Notes |
| --- | :---: | :---: | :---: | --- |
| `KiCad - Design Rules` | [x] | [ ] | [ ] | reference project |

## Maintaining the repository

- Group components by company under `KiCad - Libraries/`, using company-named
  symbol, footprint, and 3D-model libraries.
- Prefer current KiCad formats: `.kicad_sym`, `.kicad_mod`, and `.step`/`.stp`.
- Store footprints in a `.pretty` directory and 3D models in a `.3dshapes`
  directory.
- Use `${TECHNULGY_KICAD}` in library-table paths so the repository works on
  every developer's machine.
- Update the relevant inventory row whenever an item is added, renamed, reviewed,
  or tested.
