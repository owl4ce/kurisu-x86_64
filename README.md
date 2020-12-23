## violet-x86_64 <img alt="Visits" align="right" src="https://badges.pufler.dev/visits/owl4ce/violet-x86_64?style=flat-square&label=&color=success&logo=GitHub&logoColor=white&labelColor=373e4d"/>

<p align="center">
  <img alt="neofetch" align="center" src="./neofetch.png"/>
</p>

## [usr_src_linux](./usr_src_linux)
<img src="./logo.png" alt="logo" align="right" width="300px">

- bzImage: LZ4
- [Xanmod based patchset](https://gitlab.com/src_prepare/src_prepare-overlay/-/tree/master/sys-kernel/xanmod-sources)
- [Cachy CPU Scheduler](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/hamadmarri/cacule-cpu-scheduler/tree/master/patches/Cachy/v5.9) (cachy + idle balance)
- Disabled numa, debugging, etc. (kernel hacking)
- Enabled swap compressed block as default: LZ4
- AMD only (disabled most intel features)
- Governor performance as default
- BFQ I/O Scheduler as default
- Custom boot logo - [UwU](./usr_src_linux/drivers/video/logo/logo_linux_clut224.ppm)
- 1000Hz tick rate

## [home_username_.config](./home_username_.config)
- [Modprobed-db](https://github.com/graysky2/modprobed-db)  
*https://wiki.archlinux.org/index.php/Modprobed-db*

---
*~*
```bash
modprobed-db store
```

*/usr/src/linux*
```bash
cp .config_violet .config
patch -p1 < /path_extracted_cachy/cachy-5.9-r8.patch
patch -p1 < /path_extracted_cachy/02-idle_balance.patch
make -j`nproc` LSMOD=/home/username/.config/modprobed.db localmodconfig
make -j`nproc` modules_install
make -j`nproc` install
```

[backup_config](https://github.com/owl4ce/hold-my-gentoo)

<p align="center">
  <img alt="kernel-modules" align="center" src="./kernel-modules.png"/>
</p>
