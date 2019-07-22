![alt tag](https://avatars0.githubusercontent.com/u/13870012?v=3&s=200)

This software is Copyright 2014-2017 Bright Plaza Inc. <drivetrust@drivetrust.com>

This file is part of sedutil.

sedutil is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

sedutil is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with sedutil.  If not, see <http://www.gnu.org/licenses/>.


sedutil - The Drive Trust Alliance Self Encrypting Drive Utility

This program and it's accompanying Pre-Boot Authorization image allow
you to enable the locking in SED's that comply with the TCG OPAL 2.00
standard on bios machines.   

You must be administrator/root to run the host managment program

In Linux libata.allow_tpm must be set to 1. Either via adding libata.allow_tpm=1 to the kernel flags at boot time 
or changing the contents of /sys/module/libata/parameters/allow_tpm from a "0" to a "1" on a running system.

***** sleep (S3) is not supported.

Source code is available on GitHub at https://github.com/Drive-Trust-Alliance/sedutil 

Linux and Windows executables are available at https://github.com/Drive-Trust-Alliance/sedutil/wiki/Executable-Distributions

If you are looking for the PSID revert function see linux/PSIDRevert_LINUX.txt or win32/PSIDRevert_WINDOWS.txt

PLEASE SEE CONTRIBUTING if you would like to make a code contribution.




### Build on Oracle Linux ###
```yum reinstall oracle-softwarecollection-release-el7 numactl-devel
yum-config-manager --enable ol7_latest,ol7_UEKR5
yum install kernel-uek-devel-`uname -r` kernel-headers kernel-devel kernel-uek-devel

wget https://yum.oracle.com/repo/OracleLinux/OL7/optional/latest/x86_64/getPackage/xorg-x11-util-macros-1.19.0-3.el7.noarch.rpm
rpm -i xorg-x11-util-macros-1.19.0-3.el7.noarch.rpm

yum groupinstall "X Window System" "Desktop" "Desktop Platform" “Development Tools”
yum install xutils-dev

git clone https://github.com/rcvalle/libpciaccess.git
git clone https://github.com/hgst/libnvme.git
git clone https://github.com/amotin/sedutil.git 
mod sedutil as in : https://github.com/Drive-Trust-Alliance/sedutil/pull/174/files
update spelling error on LinuxPBA/UnlockSEDs.cpp:83:21: error: expected type-specifier before ‘DtaDevPurite1’
             d = new DtaDevPurite1(devref);

is Pyrite1 with a y

cd libpciaccess
sh autogen.sh ; ./configure; make; make install
cd ../libnvme/
sh autogen.sh ; ./configure; make; make install
cd ../sedutil/
sh autoreconf -i ; ./configure; make; make install```
