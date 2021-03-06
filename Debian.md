Offical ZFS on Linux [DKMS][dkms] style packages are available from the [Debian GNU/Linux repository](https://tracker.debian.org/pkg/zfs-linux) for the following configurations.  The packages previously hosted at archive.zfsonlinux.org will not be updated and are not recommended for new installations.

**Debian Releases:** Jessie and newer (testing, sid)  
**Architectures:** amd64  

## Installation
For Debian Stretch, ZFS packages are included in [contrib repository](https://packages.debian.org/source/stretch/zfs-linux).

For Debian Jessie, ZFS packages are provided by [backports](https://backports.debian.org/Instructions/).

Install kernel headers:

	# apt install linux-headers-$(uname -r)

Install zfs packages:

	# apt-get install zfs-dkms zfsutils-linux

If you want to boot from ZFS, you'll need `zfs-initramfs` package too:

	# apt-get install zfs-initramfs

[dkms]: https://en.wikipedia.org/wiki/Dynamic_Kernel_Module_Support
[debian-announce]: https://lists.debian.org/debian-devel-announce/2015/04/msg00006.html
[debian-itp]: https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=686447

* [[Debian GNU Linux initrd documentation]]  
* [[Debian Stretch Root on ZFS]]
* [[Dual booting OS X and Debian Jessie with ZFS root, cross mounting and full disk encryption]]
