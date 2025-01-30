# Sources
- <https://wiki.archlinux.org/title/Installation_guide>
- <https://wiki.archlinux.org/title/Iwd#iwctl>
- <https://bbs.archlinux.org/viewtopic.php?id=287790>
- <https://www.youtube.com/watch?v=FFXRFTrZ2Lk>
- <https://www.youtube.com/watch?v=8Lp2EQMsmL4>

# Walkthrough
1. loadkeys -trq
1. setfont ter-124b
1. iwctl
    1. device list
    1. station *name* get-networks
    1. station *name* connect *SSID*
    1. exit
1. ping archlinux.org
1. timedatectl set-ntp true
1. timedatectl
1. lsblk
1. cfdisk /dev/*drive_name*
1. 512MiB for EFI partition and rest for the system
1. lsblk
1. mkfs.fat -F 32 /dev/*efi_system_partition*
1. mkfs.ext4 /dev/*root_partition*
1. lsblk
1. mount --mkdir /dev/*efi_system_partition* -o uid=0,gid=0,fmask=0077,dmask=0077 /mnt/boot
1. mount /dev/*root_partition* /mnt
1. pacstrap -K /mnt base linux-zen linux-zen-headers linux-firmware neovim 
