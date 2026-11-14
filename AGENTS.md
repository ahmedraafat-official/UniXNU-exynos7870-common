# Agent instructions

This repository owns shared Exynos 7870 resources: CPU topology, PSCI, GIC-400,
the 26 MHz architectural timer and ordered XNU patches. Board memory, reserved
regions, display, input, power and partition policy stay in the device repository.

Read these UniXNU pages before editing:

1. [Porting](https://unixnu.com/porting/)
2. [SoC support](https://unixnu.com/porting/soc-support)
3. [Device trees](https://unixnu.com/porting/device-tree)
4. [Driver matching](https://unixnu.com/drivers/device-tree-matching)

Hardware values must be traceable to the stock SM-T585 boot DTB or the
linux-exynos7870 source pinned in `soc.toml`. Do not copy Exynos 8890 or 9810
register values. Select components by interface, hardware revision and OS ABI.

Run builds from the UniXNU checkout:

```sh
./unixnu defconfig gtaxllte_defconfig -D ../UniXNU-gtaxllte
./unixnu status --json -D ../UniXNU-gtaxllte
./unixnu tree -D ../UniXNU-gtaxllte
```

Report commands, results, required local inputs and hardware checkpoints.
Write concise English describing current behavior.
