1. Make sure your system is up-to-date
```doas apt update &&doas apt upgrade``` 

2. Install package:
```doas apt install --no-install-recommends \
libvirt-daemon-system \
virt-manager \
qemu-kvm \
qemu-utils \
libvirt-clients \
virtinst \
bridge-utils \
dnsmasq \
ovmf \
qemu-system-x86 \
virt-viewer \
spice-client-gtk \
gir1.2-spiceclientgtk-3.0``` 
\
\
3. Add user to groups
doas adduser $(whoami) kvm
doas adduser $(whoami) libvirt
doas adduser $(whoami) libvirt-qemu
\
4. How to start
Enable virtlogd and libvirtd \
doas rc-service virtlogd start
doas rc-service libvirtd start \
\
*Don't forget about lo doas ip link set lo up \
*In case virsh net-list --all shows no NAT connection, then virsh net-define /usr/share/libvirt/networks/default.xml
