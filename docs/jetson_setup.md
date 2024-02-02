> Adapted from [UCSD MAE/ECE148 Robocar Setup](https://docs.google.com/document/d/1mXgN9DcAj30HAsbfrHNCP-YEYqKWPTbcUssRI1Xab1A/edit#heading=h.qfnzubgcn5p6)

## Equipments

What you need:

- Jetson Xavier NX
    - Jetson itself
    - 19V Power Cable
- Jumper Wire
- Computer with Ubuntu 22.04 (Tested)
- Computer Peripherals
  - Keyboard
  - Mouse
  - HDMI Cable
  - Micro-USB to USB-A cable
  - Computer Monitor

## Let it into Force Recovery Mode

- Ensure the following:
  - Device powered off.
  - Power adapter disconnected.
- Place a jumper wire cable across the Force Recovery Mode pins. 
  - Pins 9 [GND] and 10 [FC REC] of the Button Header [J14].
- Connect your host computer to the device's USB Micro-B connector.
- Connect the power adapter to the Power Jack [J16].
- The device will automatically power on in Force Recovery Mode.
- Execute on your host PC's terminal lsusb command. You will see the following output to confirm that the Jetson is in recovery mode:
  - `Bus 001 Device 010: ID 0955:7e19 NVidia Corp.`

- Take off the jumper wire cable

## Flash the Jetson

```bash
git clone https://github.com/jetsonhacks/bootFromExternalStorage.git
cd bootFromExternalStorage
chmod u+x get_jetson_files.sh
chmod u+x flash_jetson_external_storage.sh
source get_jetson_files.sh
```

```bash
cd R35.1/Linux_for_Tegra/nvsdkmanager_flash.sh
```

- In vim, type 
`:%s/flash_l4t_t194_nvme.xml/flash_l4t_external.xml/g<enter>`
- Then, type in `:wq<enter>`. This will replace all occurrences of `flash_l4t_t194_nvme.xml` to `flash_l4t_external.xml`

```bash
cd ../..
source flash_jetson_external_storage.sh
# Will take some time.
# Should reboot JNX after the script is complete. 
# Otherwise, power cycle it
```

## Set up Jetson via GUI

- Connect the JNX to a monitor, keyboard, mouse, and ethernet for internet access and  finish the OEM installation

```
User: jetson
Machine name: ucsdrobocar-color
Password: jetsonucsd 
```

- Use the APP partition size to the max of the storage SSD (the default option…)
- Change the power mode to `20W 6 cores`

## Connect to the Jetson

Two ways:

1. Connect to the same network (presumably UCSDRobocar), run `ssh jetson@ucsdrobocar-color`

2. Connect via USB cable to the jetson. In the terminal, run `ssh jetson@191.168.55.1`

## Install Jetpack

On Jetson, run `df -h`. We should have something like this:

```bash
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p1  458G  5.8G  434G   2% /
none            3.4G     0  3.4G   0% /dev
tmpfs           3.4G     0  3.4G   0% /dev/shm
tmpfs           685M   19M  667M   3% /run
tmpfs           5.0M  4.0K  5.0M   1% /run/lock
tmpfs           3.4G     0  3.4G   0% /sys/fs/cgroup
tmpfs           685M   16K  685M   1% /run/user/124
tmpfs           685M  8.0K  685M   1% /run/user/1000
sudo apt update
sudo apt upgrade
sudo apt install nvidia-jetpack
```
