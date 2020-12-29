## yin-x86_64 <img alt="" align="right" src="https://badges.pufler.dev/visits/owl4ce/yin-x86_64?style=flat-square&label=&color=success&logo=GitHub&logoColor=white&labelColor=373e4d"/>

<p align="center">
  <img alt="info" align="center" src="./info.png"/>
</p>

## [usr_src_linux](./usr_src_linux)
<img alt="logo" align="right" width="300px" src="./logo.png"/>

- [LZ4](https://github.com/lz4/lz4) bzImage (vmlinuz)
- [Xanmod patchset with CacULE scheduler](https://gitlab.com/src_prepare/src_prepare-overlay/-/tree/master/sys-kernel/xanmod-sources)  
  *https://github.com/hamadmarri/cacule-cpu-scheduler*
- Disabled numa, debugging, etc. (kernel hacking)
- Enabled swap compressed block as default (LZ4)
- Android binder and ashmem support for Anbox
- AMD only (disabled most intel features)
- Governor performance as default
- BFQ I/O Scheduler as default
- Custom boot logo - [UwU](./usr_src_linux/drivers/video/logo/logo_linux_clut224.ppm)
- 1000Hz tick rate

## [home_username_.config](./home_username_.config)
- [Modprobed-db](https://github.com/graysky2/modprobed-db)  
*https://wiki.archlinux.org/index.php/Modprobed-db*

---

**~**
```bash
modprobed-db store
```

**/usr/src/linux** (root)
```bash
cp .config_yin .config
make -j`nproc` LSMOD=/home/<username>/.config/modprobed.db localmodconfig
make -j`nproc` modules_install
make -j`nproc` install
dracut --kver <version> /boot/initramfs-<version>.img --force
```

vmlinuz|modules
|--|--|
![](./vmlinuz.png)|![](./modules.png)

[backup_gentoo_config](https://github.com/owl4ce/hold-my-gentoo)
