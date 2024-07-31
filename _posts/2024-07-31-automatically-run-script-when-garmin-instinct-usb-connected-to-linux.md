---
title: Automatically Run Script When Garmin Instinct USB Device is Connected on Linux
layout: post
categories:
  - Linux
  - Automation
---

If you've ever wanted to automatically run a script when your Garmin Instinct USB device is connected to your Linux system, you can using `udev` rules. 

Steps involved:

1. Identify USB device to be able to lookup details
2. Lookup device details
3. Create udev rule
4. Create script
5. Reload udev rule
6. Test

## Prerequisites

- Basic understanding of using the terminal
- Ability to run `sudo` commands
- Familiarity with basic text editors like `nano` or `vim`

## Notes

- Don't run sudo commands, or any other random commands for that matter, that you don't know what they will do.

- If you see something in angle brackets like `<yourusername>`, replace with actual value relevant to your system.

## 1. Identify Your USB Device

First, connect your USB device and identify its device node using `lsblk`. This command lists all block devices and their mount points.

Look for the device node corresponding to your USB device. For me it was `sdb`.

## 2. Gather Device Information

Use `udevadm` to gather detailed information about your USB device.

```bash
sudo udevadm info --query=all --name=/dev/sdb
```

Replace `/dev/sdb` with the actual device node identified in the previous step. You will see output similar to this:

```
P: /devices/pci0000:00/0000:00:14.0/usb1/1-1/1-1.2/1-1.2:1.0/host6/target6:0:0/6:0:0:0/block/sdb/sdb1
N: sdb1
S: disk/by-id/usb-Garmin_USB_Flash_Drive_0123456789ABCDEF-0:0-part1
S: disk/by-label/GARMIN
E: DEVNAME=/dev/sdb1
E: DEVTYPE=partition
E: ID_BUS=usb
E: ID_FS_LABEL=GARMIN
E: ID_FS_LABEL_ENC=GARMIN
E: ID_FS_TYPE=vfat
E: ID_MODEL=USB_Flash_Drive
E: ID_MODEL_ENC=USB\x20Flash\x20Drive
E: ID_VENDOR=Garmin
E: ID_VENDOR_ENC=Garmin
...
```

We are looking specifically for the ID_FS_LABEL. If you are also using a Garmin Instinct watch it should be GARMIN. This may run into issues if you have more than 1 Garmin device that you connect.

## 3. Create a udev Rule

Create a new udev rule file in the `/etc/udev/rules.d` directory. You can name it `99-usb.rules`.

```bash
sudo nano /etc/udev/rules.d/99-usb.rules
```

Add the following rule to the file, making sure to replace the attributes with those specific to your device. :

```plaintext
SUBSYSTEM=="block", KERNEL=="sd*", ENV{ID_FS_LABEL}=="GARMIN", ACTION=="add", RUN+="/home/<yourusername>/scripts/usb_connected.sh"
```

## 4. Create the Script

Create the script that you want to run when the USB device is connected. For example:

```bash
nano /home/<yourusername>/scripts/usb_connected.sh
```

Add the following content to the script:

```bash
#!/bin/bash
echo "GARMIN USB device connected" >> /home/<yourusername>/logs/usb.log
```

Make the script executable:

```bash
chmod +x /home/<yourusername>/scripts/usb_connected.sh
```

## 5. Reload udev Rules

Reload the udev rules to apply your changes:

```bash
sudo udevadm control --reload-rules
sudo udevadm trigger
```

## 6. Test the Setup

Disconnect and reconnect your USB device. The script should run automatically and append a message to the log file.

## Troubleshooting

If the script doesn't run as expected, follow these steps:

1. **Check udev Rule File Permissions:**
   
   ```bash
   sudo chmod 644 /etc/udev/rules.d/99-usb.rules
   ```

2. **Monitor udev Events:**
   Use `udevadm monitor` to see if the rule is being triggered:
   
   ```bash
   sudo udevadm monitor --environment --udev
   ```

   Note that when you run this and first connect your Garmin to USB, you will see a flury of activity from this monitor but your script will not yet be triggered. It isn't until the USB drive is mounted that it should be triggered. So just be patient. If you don't see it mounted in the files like a external drive, then it shouldn't be triggered yet.

3. **Check System Logs:**
   Check the system logs for any relevant messages:
   
   ```bash
   journalctl -xe | grep udev
   ```


