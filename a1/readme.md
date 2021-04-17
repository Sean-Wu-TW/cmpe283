## Steps to replicate assignment 1:

Set up gcp vm instance

```shell
$ uname -mrs 
# Linux 4.19.0-14-cloud-amd64 x86_64

$ sudo apt-get update  

$ sudo apt-get upgrade

$ sudo apt-get install build-essential libncurses-dev bison flex libssl-dev libelf-dev git

$ git clone https://github.com/torvalds/linux.git

$ cd linux
$ cp -v /boot/config-$(uname -r) .config    # load pre-exist config file into new VM
# change .config file field CONFIG_SYSTEM_TRUSTED_KEYS = ""

$ make menuconfig # configure new vm
# or
$ make xconfig 
# or
$ make gconfig



$ make -j 4 # use 4 cores to compile faster
            # press enter all the way


$ apt-get bc # if receive --> /bin/sh: 1: bc: not found

$ sudo make modules_install 

$ sudo make install       

# reboot, on GCP reset

$ uname -mrs 
# Linux 5.12.0-rc6+ x86_64

# put 'cmpe283-1.c' and 'Makefile' into whichever folder, then cd into it

$ make              # compile module, some .ko/.o files generated

$ insmod cmpe283.ko # load module

$ dmesg             # see output

$ rmmod cmpe283.ko  # unload module

```





















##### Notes for myself:

https://cloud.google.com/compute/docs/instances/enable-nested-virtualization-vm-instances

Set `gcloud` project to `cmpe283`, then type: `gcloud compute ssh my-vm`

Config kernel: https://www.cyberciti.biz/tips/compiling-linux-kernel-26.html

Getting: `No rule to make target 'debian/certs/test-signing-certs.pem', needed by 'certs/x509_certificate_list'.  Stop. `: https://wiki.debian.org/BuildADebianKernelPackage

### Using your current Debian kernel configuration as a starting point

Alternatively, you can use the configuration from a Debian-built kernel that you already have installed by copying the `/boot/config-*` file to `.config` and then running `make oldconfig` to only answer new questions.

If you do this, ensure that you modify the configuration to set:

```
CONFIG_SYSTEM_TRUSTED_KEYS = ""
```

