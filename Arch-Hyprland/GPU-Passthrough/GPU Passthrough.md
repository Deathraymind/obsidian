- ---
  
  #KVM
- ```bash
  lspci -nn
  ```
- ```bash
  sudo nano /etc/default/grub
  ```
  
  Add `intel_iommu=on` to the `GRUB_CMDLINE_LINUX_DEFAULT` line:
  
  ```bash
  GRUB_CMDLINE_LINUX_DEFAULT="intel_iommu=on vfio-pci.ids=1002:699f,1002:aae0 rd.driver.pre=vfio-pci video=efifb:off loglevel=3"
  GRUB_CMDLINE_LINUX="intel_iommu=on"
  ```
  
  Now, apply the changes to GRUB:
  
  ```bash
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
  
  ```bash
  sudo nano /etc/modprobe.d/vfio.conf
  ```
  
  Add the following lines:
  
  ```bash
  options vfio-pci ids=1002:699f,1002:aae0
  ```
  
  ```bash
  sudo mkinitcpio -p linux
  ```
  
  ```bash
  sudo nano /etc/mkinitcpio.conf
  ```
  
  Add the following lines:
  
  ```bash
  MODULES=(vfio_pci vfio vfio_iommu_type1)
  ```
  
  Make sure `modconf` is added to `HOOKS`.
  
  ```bash
  sudo mkinitcpio -p linux
  ```
  
  Reboot your system.
  
  After the reboot, run:
  
  ```bash
  sudo dmesg | grep -i vfio
  ```
  
  You should see these lines:
  
  ```bash
  sudo dmesg | grep -i vfio
  [    3.990018] VFIO - User Level meta-driver version: 0.3
  [    4.001594] vfio-pci 0000:09:00.0: vgaarb: VGA decodes changed: olddecodes=io+mem,decodes=io+mem:owns=none
  [    4.001836] vfio_pci: add [1002:699f[ffffffff:ffffffff]] class 0x000000/00000000
  [    4.048435] vfio_pci: add [1002:aae0[ffffffff:ffffffff]] class 0x000000/00000000
  ```
  
  These lines indicate that the PCI device has been added to `vfio_pci` instead of `amdgpu` or `noveau` (if you're on Nvidia). If you encounter any errors like `-22`, it means that GRUB is not working correctly. To fix this, run the following commands:
  
  ```bash
  sudo grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
  ```
  
  If it says the disk is not found or an EFI system, then unmount and mount it again and rerun the command.
  
  In the Virtual Machine Manager:
  
  1. Go to XML editing.
  2. Add the following lines:
  
  ```xml
  <hyperv mode="custom">
    <relaxed state="on"/>
    <vapic state="on"/>
    <spinlocks state="on" retries="8191"/>
    <vendor_id state="on" value="1234567890ab"/>
  </hyperv>
  ```
  
  Right below, add:
  
  ```xml
  <hyperv mode="custom">
    <relaxed state="on"/>
    <vapic state="on"/>
    <spinlocks state="on" retries="8191"/>
    <vendor_id state="on" value="1234567890ab"/>
  </hyperv>
  </kvm>
  <hidden state="on"/>
  </kvm>
  ```
  
  To make Windows think it's running bare metal, add:
  
  ```xml
  <kvm>
    <hidden state="on"/>
  </kvm>
  ```
  
  Then, run:
  
  ```bash
  sudo virsh net-start default
  ```
  
  Now, apply GRUB again:
  
  ```bash
  sudo grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
  ```
  
  To integrate Looking Glass:
  
  ```xml
  <shmem name='looking-glass'>
    <model type='ivshmem-plain'/>
    <size unit='M'>32</size>
  </shmem>
  ```
  
  ```bash
  sudo nano /etc/tmpfiles.d/10-looking-glass.conf
  ```
  
  Add:
  
  ```bash
  f /dev/shm/looking-glass 0660 bowyn kvm -
  ```
  
  Make sure to run:
  
  ```bash
  sudo pacman -S qemu-full
  ```
  
  and enable the Spice server in KVM.
  
  If you need to install Looking Glass on the host, keep VNC and plug your GPU into an actual monitor, then boot the VM. Go to [Looking Glass](https://looking-glass.io/downloads), scroll the release candidates, and install the top one. Launch Looking Glass Host on the Windows machine and set it to start upon boot. 
  
  On your host machine:
  
  ```bash
  yay -S looking-glass
  ```
  
  Keep the default settings.
  
  Shut down the VM, switch it to Spice, boot it up, and in the terminal of your Linux system, run `looking-class-client`.
  
  Voila! You've done it. Also note, at the top, I have an Intel i7 8th Gen with an RX 6700XT as my main GPU and an RX 550 as the passthrough. Additionally, I'm on Hyprland Wayland Arch Linux.