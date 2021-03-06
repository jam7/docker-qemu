# QEMU/KVM on Docker

Fork from [ulexus/qemu](https://github.com/Ulexus/docker-qemu)

## Usage

Boot with ISO

```
docker run --privileged -v ${PWD}:/data \
    -e VM_DISK_IMAGE=/data/disk-image \
    -e ISO=http://releases.ubuntu.com/14.04.2/ubuntu-14.04.2-desktop-amd64.iso \
    -p 16080:6080 \
    -p 15900:5900 \
    dorowu/qemu-iso
```

Turn on machine with last image
```
docker run --privileged -v ${PWD}:/data \
    -e VM_DISK_IMAGE=/data/disk-image \
    -e ISO= \
    -p 16080:6080 \
    -p 15900:5900 \
    dorowu/qemu-iso
```

Then browse http://127.0.0.1:16080/

This image also provide *spicec* to access remote desktop if running by *docker run -e REMOTE_ACCESS=spice -p 16080:6080 ...*)
```
sudo apt-get install spice-client
spicec -h 127.0.0.1 -p 15900
```
