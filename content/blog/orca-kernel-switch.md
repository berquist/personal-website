---
title: "ORCA Kernel Switch"
date: 2018-06-20T21:21:20-04:00
draft: false
---

If you run Arch Linux and the [ORCA](https://orcaforum.cec.mpg.de/) quantum chemistry package, and you're getting segmentation faults before any output is produced, there's a reason,

From [this thread](https://orcaforum.cec.mpg.de/viewtopic.php?f=9&t=3870&sid=74a1339ac1e7c80f6e0ac41cb3c58e2c) (password protected), older versions of ORCA compiled with static libraries no longer work on the latest versions of Arch Linux:

> It turns out that linux kernel 4.11 disabled vsyscall by default for security reasons. Applications compiled with older versions of glibc will break. A workaround is to edit the grub configuration to (in my system in /etc/default/grub)

    GRUB_CMDLINE_LINUX_DEFAULT="vsyscall=emulate"
    
> Then rebuild grub files and reboot:

    grub-mkconfig -o /boot/grub/grub.cfg
    
However, without having added this line, I've tested that the shared library version of ORCA 4.0.1.2 (the latest one provided, `orca_4_0_1_2_linux_x86-64_shared_openmpi202.tar.zst`) runs without issues.
