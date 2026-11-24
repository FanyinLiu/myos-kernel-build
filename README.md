# MyOS kernel for Honor 20 (YAL-AL00 / kirin980)

Source of truth for the MyOS kernel build. The Huawei source tarball is
**not** committed here — CI downloads it from Huawei's open-source site at
build time, then applies the patches in `patches/`.

- Base: `Yale-AL00A-TL00-L21-AL10PIE` (EMUI 9.1.0 / Android 9 / Linux 4.9.148)
- Toolchain: `aarch64-linux-gnu-` (GCC from Ubuntu runner)
- Config: `merge_kirin980_defconfig`
- Output: `Image.gz` + device trees

## Patches

`0001-yale-touchscreen-real-dts.patch` — turns the FPGA touchscreen stub into a
real device node: `status="ok"`, i2c bus 7, synaptics @0x70, 1080x2340, and
gives `ts_kit` its `compatible` so `huawei_ts_kit_core` can bind.
