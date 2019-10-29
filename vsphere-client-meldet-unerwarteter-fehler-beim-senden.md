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
