# Usb Linux

## Introduction

When we connect an usb device, we wait to see it on the screen and then start working with it. This is how computers works, but not always. What happens if we are using a system that does not take the required actions to mount the USB device? For example, with a Tiling Windows Manager.

We will have to run the commands to mount the device and, when we want to disconnect it, more commands to unmount and extract the usb are required. This is fine to learn how to work with an usb but doing all these steps every day is bad.

The objetive of this project is to automatice all the steps to connect and disconnect an usb in a Gnu/Linux system. First, we will see how to do it manually and then, how to automatice the process using some scripts that I developed.

## Work with an usb manually

Some of the following commands require the installation of additional software, see the automaticed sections to know how to install them.

### Mount an usb manually

A connected usb will appear in the path `/dev` starting with `sd`. The part to mount will have the same name ending in a number.

For example, before connect an usb, I have:

```bash
ls /dev/sd*
# /dev/sda  /dev/sda1  /dev/sda2  /dev/sda3  /dev/sda4  /dev/sda6  /dev/sda8  /dev/sdb
```

After connect an usb:

```bash
ls /dev/sd*
# /dev/sda  /dev/sda1  /dev/sda2  /dev/sda3  /dev/sda4  /dev/sda6  /dev/sda8  /dev/sdb  /dev/sdc  /dev/sdc1
```

In this example, the usb is `/dev/sdc` and the part with the data to mount is `/dev/sdc1`.

In order to access de usb data, I have to mount `/dev/sdc1`, I will do it in `/media/usb`:

```bash
sudo mount /dev/sdc1 /media/usb
```

Now I can work with the usb using the path `/media/usb`:

```bash
ls /media/usb/
# test.txt
```

### Disconnect an usb manually

To disconnect an usb, three steps are required:

- Unmount.
- Eject.
- Power off.

#### Unmount an usb manually

We can unmount the part with the usb data (`/dev/sdc1`) or the folder where the usb was mounted (`/media/usb`):

```bash
sudo umount /dev/sdc1
# sudo umount /media/usb # This is valid too.
```

If we check the `/dev` path, all the previous devices will appear:

```bash
ls /dev/sd*
# /dev/sda  /dev/sda1  /dev/sda2  /dev/sda3  /dev/sda4  /dev/sda6  /dev/sda8  /dev/sdb  /dev/sdc  /dev/sdc1
```

Despite that, the path `/media/usb/` won't show the usb data:

```bash
ls /media/usb/
```

Now the usb can be ejected.

#### Eject an usb manually

The path to eject is the usb raw device, in this example its value is `/dev/sdc`:

```bash
sudo eject /dev/sdc
```

At this point, the part with the data, `/dev/sdc1`, won't appear:

```bash
ls /dev/sd*
/dev/sda  /dev/sda1  /dev/sda2  /dev/sda3  /dev/sda4  /dev/sda6  /dev/sda8  /dev/sdb  /dev/sdc
```

Before disconnect the usb it must be powered off.

#### Power off an usb manually

The last point is to power off the usb in order to avoid damage it when it will be disconnected from the computer.

We run this command over the raw device:

```bash
udisksctl power-off -b /dev/sdc
```

No usb folder will remain in `/dev`:

```bash
ls /dev/sd*
# /dev/sda  /dev/sda1  /dev/sda2  /dev/sda3  /dev/sda4  /dev/sda6  /dev/sda8  /dev/sdb
```

If the usb has a light, it will be turned off.

## Automatice work with an usb

The USB mount and unmount process has been automaticed in the project [usb-linux](https://github.com/carlosamolina/usb-linux). Lets see how to configure it.

### Start and end working with an USB

First, install and configure the required software:

- [Rust](https://www.rust-lang.org/tools/install)
- [Dunst](https://wiki.archlinux.org/title/Dunst#Installation)
- [udisks2](https://wiki.archlinux.org/title/Udisks#Installation)

To configure Dunst, for example in [i3](https://i3wm.org/), add the following line to the `~/.config/i3/config` file (you can check my [dotfiles](https://github.com/CarlosAMolina/dotfiles/blob/main/dotfiles/config/i3/config)):

```bash
exec --no-startup-id dunst
```

Download the project, for example in `~/Software/usb-linux/` and build the Rust package:

```bash
cd ~/Software/usb-linux/src/usb/
cargo test # Check the tests pass.
cargo build
```

Add a symlink to the binary:

```bash
sudo ln -s $HOME/Software/usb-linux/src/usb/target/debug/usb /usr/local/bin/usb
```

Create the folder where the USB will be mounted:

```bash
sudo mkdir /media/usb
```

Now, the previous steps to start or end an USB can be done with these commands:

```bash
usb sdc1 on # Mount an USB.
usb sdc1 off # Unmount, eject and power-off an USB.
```

With this configuration, some manual steps are avoided but we still need the USB device's name. Lets configure a notification that will give us this value.

### Notify the USB device

In order to know the name given to the USB device, we will monitor the `/dev` path with `inotifywait`:

```bash
sudo apt-get install -y inotify-tools
```

In [i3](https://i3wm.org/), add the following line to the `~/.config/i3/config` file (you can check my [dotfiles](https://github.com/CarlosAMolina/dotfiles/blob/main/dotfiles/config/i3/config)):

```bash
exec --no-startup-id $HOME/Software/usb-linux/src/bash/monitor
```

The previous script will show a notification with the device`s name each time a new one is detected.

