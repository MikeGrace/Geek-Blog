---
title: Install Configure Epson ET-2800 Printer on Arch Linux
layout: post
categories:
  - Linux
  - Arch
  - How-to
---

I first tried the GNOME printer setting panel to add the network printer but that failed with a "Failed to add new printer." message. 

![screenshot of "Failed to add new printer." error message](/assets/2024/08/2024-08-03-failed-to-add-printer.png)

The following is how I got everything installed to be able to print from my Arch linux to Epson ET-2800.

## 1. Install Cups

```
sudo pacman -S cups
```

You can find details at [https://archlinux.org/packages/extra/x86_64/cups/](https://archlinux.org/packages/extra/x86_64/cups/)

Then enable and start the cups service.

```
sudo systemctl enable cups.service
sudo systemctl start cups.service
```

## 2. Install Epson Printer Drivers

```
yay -S epson-inkjet-printer-escpr epson-inkjet-printer-escpr2
```

AUR package details at [https://aur.archlinux.org/packages/epson-inkjet-printer-escpr](https://aur.archlinux.org/packages/epson-inkjet-printer-escpr) and [https://aur.archlinux.org/packages/epson-inkjet-printer-escpr2](https://aur.archlinux.org/packages/epson-inkjet-printer-escpr2)

## 3. Add Printer Via Cups Web Interface

1. Load browser to [http://localhost:631/](http://localhost:631/)

2. Click 'Administration' link that should take you to [http://localhost:631/admin](http://localhost:631/admin)

![cups printer admin screenshot](/assets/2024/08/2024-08-03-cups-admin.png)

3. Click 'Add Printer'

4. Select the printer under the 'Discovered Network Printers'

5. Input the connection URI of your printer. Mine was `lpd://192.168.1.199/queue`
   
   1. I got the IP address of the printer by noting the address when adding usingprinter settings in the GNOME settings app failed.

   ![ip address of printer in settings screenshot](/assets/2024/08/2024-08-03-printer-ip-address.png)

6. Fill in details, give name, select model on the next few screens.

![add printer screenshot](/assets/2024/08/2024-08-03-cups-add-printer-selection.png)

7. Confirm it is working with a print test page by selecting 'Print Test Page' on the 'Maintenance' dropdown on the printer detail page.

![print test page screenshot](/assets/2024/08/2024-08-03-print-test-page.png)



## 4. Print!

Now you can print all the things!

The printer should also show up in the Settings -> Printers panel as well.

![printer in settings screenshot](/assets/2024/08/2024-08-03-printer-in-settings.png)


