## yin-x86_64 <img alt="" align="right" src="https://badges.pufler.dev/visits/owl4ce/kurisu-x86_64?style=flat-square&label=&color=fa74b2&logo=GitHub&logoColor=white&labelColor=373e4d"/>

<p align="center">🎀 Optimized for multitasking under high load 🎀</p>

## [Kernel Sources](./kernel.sources)
<img alt="logo" align="right" width="350px" src="https://i.ibb.co/TYdw4Md/kurisu.png"/>

- LZ4 compressed bzImage
- [Xanmod-CacULE patchset + Gentoo patches](https://gitlab.com/src_prepare/src_prepare-overlay/-/tree/master/sys-kernel/xanmod-sources)
- Enabled LZ4 swap compressed block as default
- Android binder and ashmem support for Anbox
- AMD SoC only, disabled most intel features
- Disabled numa, kexec, debugging, etc.
- Governor performance as default
- BFQ I/O Scheduler as default
- Kurisu Makise boot logo ([っ◔◡◔](./kurisu/drivers/video/logo/logo_linux_clut224.ppm))  
  > 1366x768
- 500Hz tick rate

---

### Kernel sources directory
- **Gentoo**: `/usr/src/linux`
  ```bash
  cp .config_kurisu .config
  make -j`nproc` menuconfig # If you want to adjust yourself again

  # Make sure this and so on down as root
  make -j`nproc` modules_install
  make -j`nproc` install
  ```

### Generate initramfs (if using)
- **Dracut**  
  Adjust <version> with the kernel version you compiled/use (as root)
  ```bash
  dracut --kver <version> /boot/initramfs-<version>.img --force
  ```
  
> In order for the logo to appear on boot, make sure to use `loglevel=4` in the [kernel parameters](https://wiki.archlinux.org/index.php/Kernel_parameters).

[backup_gentoo_config](https://github.com/owl4ce/hold-my-gentoo)
