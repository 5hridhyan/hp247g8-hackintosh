# HP 247 G8 – macOS Monterey OpenCore EFI
OpenCore EFI configuration for **HP 247 G8 Notebook PC** running **macOS Monterey**.

## 🖥 Hardware

```
CPU: AMD Ryzen 5 3500U (Zen+)
iGPU: Radeon Vega 8 (Picasso)
Display: 1366x768 BOE Panel
Audio: AMD HD Audio + ACP Audio
Network:
  - Realtek RTL8111 Ethernet
  - Realtek RTL8822CE WiFi + Bluetooth (Unsupported)
Storage: NVMe SSD
RAM: 6GB
```

---

## ✅ Working

* ✔ Touchpad
* ✔ Keyboard
* ✔ Audio (including media keys)
* ✔ GPU Hardware Acceleration
* ✔ Battery Status
* ✔ Brightness Control
* ✔ Volume Control
* ✔ USB Teathering
  
---

## ❌ Not Working

* ✘ WiFi (Realtek RTL8822CE)
* ✘ Bluetooth (Realtek RTL8822CE)
* ✘ Suspend / Resume

---

## ⚠ Important Notes

* Disable **NootedRed** during first boot setup if you experience boot issues.
* This EFI is specifically tuned for HP 247 G8 BIOS F.68 firmware.
* Some macOS features depending on unsupported hardware may remain broken.

---

## 📌 System Details

From `inxi`:

* Kernel: 6.18.13 (Arch Linux host)
* Display Server: Wayland + Hyprland
* Boot Type: UEFI
* Storage Layout: Btrfs + LUKS2 + Swapfile + Zswap enabled

---

## 🚀 Credits / Tools

* OpenCore Bootloader
* AMD Hackintosh community resources
* Dortania guides

---

##  Known Limitations

* Sleep/wake stability is not guaranteed.
* Wireless networking requires a supported replacement card.

---



<details>
<summary>Click to expand my full system specs</summary>

```text
System:
  Kernel: 6.18.13-arch1-1 arch: x86_64 bits: 64 compiler: gcc v: 15.2.1
    clocksource: tsc avail: hpet,acpi_pm parameters: BOOT_IMAGE=/vmlinuz-linux
    root=UUID=c0ae4a73-5088-4f7e-b497-ca1a4baa4dbe rw rootflags=subvol=@
    cryptdevice=UUID=63984f23-816d-48d8-9493-119bf15c9a26:root
    zswap.enabled=1 rootfstype=btrfs loglevel=3
    lsm=landlock,lockdown,yama,apparmor,bpf apparmor=1 security=apparmor
    resume=UUID=c0ae4a73-5088-4f7e-b497-ca1a4baa4dbe resume_offset=17423426
  Desktop: Hyprland v: 0.54.0 with: waybar tools: hypridle avail: hyprlock
    vt: 1 dm: SDDM Distro: Aranya Marjara rolling
Machine:
  Type: Laptop System: Hewlett-Packard product: HP 247 G8 Notebook PC v: N/A
    serial: <superuser required> Chassis: type: 10 serial: <superuser required>
  Mobo: Hewlett-Packard model: 85E0 v: 84.51 serial: <superuser required>
    part-nu: 7J423PA#ACJ uuid: <superuser required> Firmware: UEFI vendor: AMI
    v: F.68 date: 11/09/2022
Battery:
  ID-1: BAT0 charge: 20.2 Wh (73.7%) condition: 27.5/27.5 Wh (100%)
    volts: 11.88 min: 11.34 model: Hewlett-Packard Primary type: Li-ion
    serial: <filter> charging: status: discharging cycles: N/A
CPU:
  Info: model: AMD Ryzen 5 3500U with Radeon Vega Mobile Gfx bits: 64
    type: MT MCP arch: Zen/Zen+ note: check gen: 1 level: v3 note: check
    built: 2019 process: GF 12nm family: 0x17 (23) model-id: 0x18 (24)
    stepping: 1 microcode: 0x8108109
  Topology: cpus: 1x dies: 1 clusters: 1 cores: 4 threads: 8 tpc: 2
    smt: enabled cache: L1: 384 KiB desc: d-4x32 KiB; i-4x64 KiB L2: 2 MiB
    desc: 4x512 KiB L3: 4 MiB desc: 1x4 MiB
  Speed (MHz): avg: 1397 min/max: 1400/2100 boost: disabled scaling:
    driver: acpi-cpufreq governor: powersave cores: 1: 1397 2: 1397 3: 1397
    4: 1397 5: 1397 6: 1397 7: 1397 8: 1397 bogomips: 33538
  Flags-basic: avx avx2 ht lm nx pae sse sse2 sse3 sse4_1 sse4_2 sse4a
    ssse3 svm
  Vulnerabilities:
  Type: gather_data_sampling status: Not affected
  Type: ghostwrite status: Not affected
  Type: indirect_target_selection status: Not affected
  Type: itlb_multihit status: Not affected
  Type: l1tf status: Not affected
  Type: mds status: Not affected
  Type: meltdown status: Not affected
  Type: mmio_stale_data status: Not affected
  Type: old_microcode status: Not affected
  Type: reg_file_data_sampling status: Not affected
  Type: retbleed mitigation: untrained return thunk; SMT vulnerable
  Type: spec_rstack_overflow mitigation: Safe RET
  Type: spec_store_bypass mitigation: Speculative Store Bypass disabled via
    prctl
  Type: spectre_v1 mitigation: usercopy/swapgs barriers and __user pointer
    sanitization
  Type: spectre_v2 mitigation: Retpolines; IBPB: conditional; STIBP:
    disabled; RSB filling; PBRSB-eIBRS: Not affected; BHI: Not affected
  Type: srbds status: Not affected
  Type: tsa status: Not affected
  Type: tsx_async_abort status: Not affected
  Type: vmscape mitigation: IBPB before exit to userspace
Graphics:
  Device-1: Advanced Micro Devices [AMD/ATI] Picasso/Raven 2 [Radeon Vega
    Series / Radeon Mobile Series] vendor: Hewlett-Packard driver: amdgpu
    v: kernel arch: GCN-5 code: Vega process: GF 14nm built: 2017-20 pcie:
    gen: 3 speed: 8 GT/s lanes: 16 ports: active: eDP-1 empty: DP-1,HDMI-A-1
    bus-ID: 04:00.0 chip-ID: 1002:15d8 class-ID: 0300 temp: 46.0 C
  Display: wayland server: X.org v: 1.21.1.21 with: Xwayland v: 24.1.9
    compositor: Hyprland v: 0.54.0 driver: X: loaded: modesetting
    alternate: fbdev,vesa dri: radeonsi gpu: amdgpu display-ID: 1
  Monitor-1: eDP-1 model: BOE Display 0x092c built: 2020 res: mode: 1366x768
    hz: 60 scale: 100% (1) dpi: 112 gamma: 1.2 size: 310x170mm (12.17x6.85")
    diag: 355mm (14") ratio: 16:9 modes: max: 1366x768 min: 640x480
  API: EGL v: 1.5 hw: drv: amd radeonsi platforms: device: 0 drv: radeonsi
    device: 1 drv: swrast gbm: drv: kms_swrast surfaceless: drv: radeonsi
    wayland: drv: radeonsi x11: drv: radeonsi
  API: OpenGL v: 4.6 compat-v: 4.5 vendor: amd mesa v: 26.0.1-arch1.1
    glx-v: 1.4 direct-render: yes renderer: AMD Radeon Vega 8 Graphics
    (radeonsi raven ACO DRM 3.64 6.18.13-arch1-1) device-ID: 1002:15d8
    memory: 1.95 GiB unified: no
  API: Vulkan v: 1.4.341 layers: 9 device: 0 type: integrated-gpu name: AMD
    Radeon Vega 8 Graphics (RADV RAVEN) driver: mesa radv v: 26.0.1-arch1.1
    device-ID: 1002:15d8 surfaces: N/A
  Info: Tools: api: clinfo, eglinfo, glxinfo, vulkaninfo
    de: kscreen-console,kscreen-doctor gpu: nvidia-smi,radeontop
    wl: nwg-displays,wayland-info x11: xdpyinfo, xprop, xrandr
Audio:
  Device-1: Advanced Micro Devices [AMD/ATI] Raven/Raven2/Fenghuang HDMI/DP
    Audio vendor: Hewlett-Packard driver: snd_hda_intel v: kernel pcie: gen: 3
    speed: 8 GT/s lanes: 16 bus-ID: 04:00.1 chip-ID: 1002:15de class-ID: 0403
  Device-2: Advanced Micro Devices [AMD] Audio Coprocessor
    vendor: Hewlett-Packard driver: snd_pci_acp3x v: kernel
    alternate: snd_rn_pci_acp3x, snd_pci_acp5x, snd_pci_acp6x, snd_acp_pci,
    snd_rpl_pci_acp6x, snd_pci_ps, snd_sof_amd_renoir, snd_sof_amd_rembrandt,
    snd_sof_amd_vangogh, snd_sof_amd_acp63, snd_sof_amd_acp70 pcie: gen: 3
    speed: 8 GT/s lanes: 16 bus-ID: 04:00.5 chip-ID: 1022:15e2 class-ID: 0480
  Device-3: Advanced Micro Devices [AMD] Ryzen HD Audio
    vendor: Hewlett-Packard driver: snd_hda_intel v: kernel pcie: gen: 3
    speed: 8 GT/s lanes: 16 bus-ID: 04:00.6 chip-ID: 1022:15e3 class-ID: 0403
  API: ALSA v: k6.18.13-arch1-1 status: kernel-api
    tools: alsactl,alsamixer,amixer
  Server-1: sndiod v: N/A status: off tools: aucat,midicat,sndioctl
  Server-2: PipeWire v: 1.4.10 status: active with: 1: pipewire-pulse
    status: active 2: wireplumber status: active 3: pipewire-alsa type: plugin
    4: pw-jack type: plugin tools: pactl,pw-cat,pw-cli,wpctl
Network:
  Device-1: Realtek RTL8111/8168/8211/8411 PCI Express Gigabit Ethernet
    vendor: Hewlett-Packard driver: r8169 v: kernel pcie: gen: 1 speed: 2.5 GT/s
    lanes: 1 port: f000 bus-ID: 02:00.0 chip-ID: 10ec:8168 class-ID: 0200
  IF: eno1 state: down mac: <filter>
  Device-2: Realtek RTL8822CE 802.11ac PCIe Wireless Network Adapter
    vendor: Hewlett-Packard driver: rtw88_8822ce v: kernel pcie: gen: 1
    speed: 2.5 GT/s lanes: 1 port: e000 bus-ID: 03:00.0 chip-ID: 10ec:c822
    class-ID: 0280
  IF: wlp3s0 state: up mac: <filter>
  Info: services: NetworkManager, systemd-timesyncd, wpa_supplicant
Bluetooth:
  Device-1: Realtek Bluetooth Radio driver: btusb v: 0.8 type: USB rev: 1.0
    speed: 12 Mb/s lanes: 1 mode: 1.1 bus-ID: 3-1:2 chip-ID: 0bda:b00c
    class-ID: e001 serial: <filter>
  Report: btmgmt ID: hci0 rfk-id: 2 state: down bt-service: enabled,running
    rfk-block: hardware: no software: yes address: N/A
Drives:
  Local Storage: total: 476.94 GiB used: 139.99 GiB (29.4%)
  SMART Message: Unable to run smartctl. Root privileges required.
  ID-1: /dev/nvme0n1 maj-min: 259:0 model: ABSSDNVMe512GB size: 476.94 GiB
    block-size: physical: 512 B logical: 512 B speed: 31.6 Gb/s lanes: 4
    tech: SSD serial: <filter> fw-rev: EDFB00.7 temp: 37.9 C scheme: GPT
Partition:
  ID-1: / raw-size: 280.85 GiB size: 280.85 GiB (100.00%)
    used: 137.91 GiB (49.1%) fs: btrfs dev: /dev/dm-0 maj-min: 253:0
    mapped: root
  ID-2: /boot raw-size: 1024 MiB size: 1022 MiB (99.80%)
    used: 188.4 MiB (18.4%) fs: vfat dev: /dev/nvme0n1p1 maj-min: 259:1
  ID-3: /home raw-size: 280.85 GiB size: 280.85 GiB (100.00%)
    used: 137.91 GiB (49.1%) fs: btrfs dev: /dev/dm-0 maj-min: 253:0
    mapped: root
  ID-4: /var/log raw-size: 280.85 GiB size: 280.85 GiB (100.00%)
    used: 137.91 GiB (49.1%) fs: btrfs dev: /dev/dm-0 maj-min: 253:0
    mapped: root
Swap:
  Kernel: swappiness: 100 (default 60) cache-pressure: 100 (default)
    zswap: yes compressor: zstd max-pool: 20%
  ID-1: swap-1 type: file size: 16 GiB used: 0 KiB (0.0%) priority: -2
    file: /swap/swapfile
  ID-2: swap-2 type: zram size: 2.85 GiB used: 24 KiB (0.0%) priority: 100
    comp: zstd avail: lzo-rle,lzo,lz4,lz4hc,deflate,842 dev: /dev/zram0
Sensors:
  System Temperatures: cpu: 47.6 C mobo: N/A gpu: amdgpu temp: 47.0 C
  Fan Speeds (rpm): N/A
Info:
  Memory: total: 6 GiB note: est. available: 5.69 GiB used: 3.26 GiB (57.3%)
  Processes: 332 Power: uptime: 2h 5m states: freeze,mem,disk suspend: deep
    avail: s2idle wakeups: 1 hibernate: platform avail: shutdown, reboot,
    suspend, test_resume image: 0 KiB services: upowerd Init: systemd v: 259
    default: graphical tool: systemctl
  Packages: 1446 pm: nix-default pkgs: 0 pm: nix-sys pkgs: 0 pm: nix-usr
    pkgs: 74 libs: 17 pm: pacman pkgs: 1351 libs: 321 tools: yay pm: flatpak
    pkgs: 21 Compilers: clang: 21.1.8 gcc: 15.2.1 Shell: Zsh v: 5.9
    running-in: kitty inxi: 3.3.40
``````
