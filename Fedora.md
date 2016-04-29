# Fedora

Only [DKMS][dkms] style packages can be provided for Fedora from the official zfsonlinux.org repository.  This is because Fedora is a fast moving distribution which does not provide a stable kABI. These packages track the official ZFS on Linux tags and are updated as new versions are released.  Packages are available for the following configurations:

**Fedora Releases:** 21, 22, 23  
**Architectures:** x86_64  

To simplify installation a zfs-release package is provided which includes a zfs.repo configuration file and the ZFS on Linux public signing key.  All official ZFS on Linux packages are signed using this key, and by default both yum and dnf will verify a package's signature before allowing it be to installed.  Users are strongly encouraged to verify the authenticity of the ZFS on Linux public key using the fingerprint listed here.

**Location:** /etc/pki/rpm-gpg/RPM-GPG-KEY-zfsonlinux  
**Fedora Package:** http://archive.zfsonlinux.org/fedora/zfs-release.fc21.noarch.rpm  
**Fedora Package:** http://archive.zfsonlinux.org/fedora/zfs-release.fc22.noarch.rpm  
**Fedora Package:** http://archive.zfsonlinux.org/fedora/zfs-release.fc23.noarch.rpm  
**Download from:** [pgp.mit.edu][pubkey]  
**Fingerprint:** C93A FFFD 9F3F 7B03 C310  CEB6 A9D5 A1C0 F14A B620

```
$ sudo yum localinstall --nogpgcheck http://archive.zfsonlinux.org/fedora/zfs-release$(rpm -E %dist).noarch.rpm
$ gpg --quiet --with-fingerprint /etc/pki/rpm-gpg/RPM-GPG-KEY-zfsonlinux
pub  2048R/F14AB620 2013-03-21 ZFS on Linux <zfs@zfsonlinux.org>
    Key fingerprint = C93A FFFD 9F3F 7B03 C310  CEB6 A9D5 A1C0 F14A B620
    sub  2048R/99685629 2013-03-21
```

The ZFS on Linux packages can now be installed with dnf on Fedora 22 and newer and yum on previous Fedora releases. Note that it is important to make sure that the matching *kernel-devel* package is installed for the running kernel since DKMS requires it to build ZFS.

Fedora 22 and newer:

```
$ sudo dnf install kernel-devel zfs
```

Fedora 21 and older:

```
$ sudo yum install kernel-devel zfs
```

## Testing Repositories

In addition to the primary *zfs* repository a *zfs-testing* repository is available. This repository, which is disabled by default, contains the latest version of ZFS on Linux which is under active development. These packages are made available in order to get feedback from users regarding the functionality and stability of upcoming releases. These packages **should not** be used on production systems. Packages from the testing repository can be installed as follows.

Fedora 22 and newer:

```
$ sudo dnf --enablerepo=zfs-testing install kernel-devel zfs 
```


Fedora 21 and older:

```
$ sudo yum --enablerepo=zfs-testing install kernel-devel zfs 
```

[dkms]: https://en.wikipedia.org/wiki/Dynamic_Kernel_Module_Support
[pubkey]: http://pgp.mit.edu/pks/lookup?search=0xF14AB620&op=index&fingerprint=on