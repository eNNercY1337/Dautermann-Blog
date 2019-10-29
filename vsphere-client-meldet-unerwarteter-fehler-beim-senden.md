# Installation von VMWare Tools auf Ubuntu/Debian

Zuerst müssen wir die “build-essential” und die dazu benötigen Kernel Pakete installieren, dies machen wir wie folgt.

```sh
sudo apt-get install build-essential
sudo apt-get install linux-headers-$(uname -r)
```

Danach können wir schon mit der Installation von den VMWare Tools selbst starten, dazu legen wir die VMWare-Tools CD in das virtuelle Laufwerk ein und beginnen wie folgt mit der Installation.

### Falls die open-vm-tools installiert sind diese vorher löschen! (ab Ubuntu 16 vorinstalliert)

```sh
sudo apt-get remove --purge open-vm* -y
sudo apt-get autoremove -y
```

### Mounten des VMWare-Tools CD Image

```
sudo mkdir -p /media/cdrom
sudo mount /dev/cdrom /media/cdrom
```

### Kopieren des komprimierten VMWare-Tools Archives nach /tmp

```
cp /media/cdrom/VM*.tar.gz /tmp
sudo umount /media/cdrom
cd /tmp
```

### Entpacken des VMWare-Tools Archives sowie Beginn der Installation

```
tar xzvf VM*.tar.gz
cd vmware-tools-distrib
sudo ./vmware-install.pl
```

Der Installer wird ein paar mal nach Bestätigen fragen welche wir jeweils mit Enter bestätigen müssen.

Sobald die Installation abgeschlossen ist können wir den Server neustarten und er sollte uns im vSphere Client als “Wird ausgeführt (Aktuell)” angezeigt werden.
