# VirtualBox Disk Resizing Guide

## Moving Kali Linux Virtual Disk to Secondary Drive
1. **Shutdown VM**: Ensure the Kali Linux virtual machine is completely shut down.
2. **Copy Virtual Disk**: Manually copy the `KaliLinux.vdi` file from `C:/Users/tomco/VirtualBox VMs/KaliLinux/` to `D:/Users/tomco/<new kali folder here>/`.
3. **Re-Attach to VM**: In VirtualBox, go to Settings -> Storage, remove the old VDI, and then attach the new VDI from the secondary drive location.

## Resizing the Virtual Disk
1. **Open Command Prompt as Administrator**: Open your command prompt with administrative privileges.
   
2. **Navigate to VirtualBox Directory**: 
    ```bash
    cd "C:\Program Files\Oracle\VirtualBox"
    ```
   
3. **Resize Disk**: Run the following command to resize the virtual disk.
    ```bash
    VBoxManage modifyhd "D:/Users/tomco/<new kali folder here>/KaliLinux.vdi" --resize 153600
    ```
   This will resize the disk to 150GB (150 * 1024 = 153600MB).

4. **Expand Filesystem in VM**: After resizing, you'll need to expand the filesystem within Kali Linux. This is usually done using tools like `gparted`.

5. **Verify the Changes**: Boot up the Kali Linux VM and verify that the disk has been resized.

