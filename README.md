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
| `KiCad - Libraries/` | KiCad symbol libraries, footprint libraries, and 3D models |
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

The availability columns describe the files currently present in the repository;
they are not quality or verification results.

| Library | Symbol | Footprint | 3D model | WIP | Finished | Tested | Notes |
| --- | :---: | :---: | :---: | :---: | :---: | :---: | --- |
| `AP22653W6` | Yes | No | No | [ ] | [x] | [ ] | Linked with generic Footprint  & 3D Modell |
| `BNO055` | Yes | Yes | Yes | [ ] | [x] | [x] | |
| `LIS2MDLTR` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `LSM6DSV320XTR` | Yes | Yes | Yes | [ ] | [x] | [ ] | Footprint is named `LSM6DSV16BXTR` |
| `LT8638S` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `MagJack-A70-112-331N126` | Yes | Yes | Yes | [ ] | [x] | [ ] | |
| `Maxon ESCON 24 2` | Yes | Yes | Yes | [ ] | [x] | [x] | Includes models with and without headers |
| `Molex_203560-0503` | Yes | Yes | Yes | [ ] | [x] | [x] | |
| `QM35825` | Yes | Yes | Yes | [x] | [ ] | [ ] | |
| `RaspberryPi_CM5` | Yes | Yes | Yes | [ ] | [ ] | [ ] | Two connector footprints |
| `RCJ Communication Module` | Yes | Yes | Yes | [ ] | [x] | [x] | Includes models with and without headers |
| `RT9742GGJ5` | Yes | Yes | Yes | [ ] | [ ] | [ ] | |
| `Teensy 4.1` | Yes | Yes | Yes | [ ] | [x] | [x] | 3D model includes headers |

## Design blocks

| Category | Design block | WIP | Finished | Tested | Notes |
| --- | --- | :---: | :---: | :---: | --- |
| IC | `RP CM5` | [ ] | [x] | [ ] | |
| IC | `STM32G431RB` | [ ] | [x] | [ ] | |
| Power | `+3V3 LDO 1A` | [ ] | [x] | [ ] | |
| Power | `+5V Buck 10A` | [ ] | [x] | [ ] | |

The `Communication` and `Misc` design-block libraries are configured but do not
currently contain tracked design blocks.

## Design rules

| Resource | WIP | Finished | Tested | Notes |
| --- | :---: | :---: | :---: | --- |
| `KiCad - Design Rules` | [x] | [ ] | [ ] | reference project |

## Maintaining the repository

- Keep each component in its own directory under `KiCad - Libraries/`.
- Prefer current KiCad formats: `.kicad_sym`, `.kicad_mod`, and `.step`/`.stp`.
- Store footprints in a `.pretty` directory and 3D models in a `.3dshapes`
  directory.
- Use `${TECHNULGY_KICAD}` in library-table paths so the repository works on
  every developer's machine.
- Update the relevant inventory row whenever an item is added, renamed, reviewed,
  or tested.
