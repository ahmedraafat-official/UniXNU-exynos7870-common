# UniXNU exynos7870 common

Shared SoC support for the Samsung Exynos 7870 (S5E7870), used by the Galaxy
Tab A 10.1 (2016) port (`UniXNU-gtaxllte`).

## What is here

| Path | Contents |
| --- | --- |
| `soc.toml` | SoC identity, source pin and shared components |
| `configs/exynos7870.config` | PAN off (ARMv8.0 Cortex-A53) |
| `dts/exynos7870.dtsi` | CPUs, PSCI, GIC-400, 26 MHz timer |
| `patches/xnu/series` | SoC patches, empty for the first bring-up |

## Source of the values

The DTSI is derived from the mainline Exynos 7870 SoC DTSI and the
`gtaxlwifi/7.3` tree at the commit pinned in `soc.toml`. The board-specific
memory map, secure hole, framebuffer and peripheral wiring belong to the
device repository, not here.

## Status

No XNU build or hardware boot has used this SoC layer yet. The first target is
XNU entry with the boot CPU, GIC-400 and the architectural timer. The other
seven cores, storage, display, input and GPU are added in the milestones in
`UniXNU-gtaxllte/PORT-PLAN.md`.
