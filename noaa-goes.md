# NOAA GOES

## Objective

Receive full disk images from the NOAA GOES System.

## Experiment Phases

1) Assemble Receiver Box
2) Assemble Antenna
3) Raspberry Pi Configuration
4) Signal Check A GOES Satellite
5) Receive and Process Images

### Assemble Receiver Box

TODO

### Assemble Antenna

TODO

### Raspberry Pi Configuration

One objective is to connect to the Pi over SSH from multiple host computers
via direct ethernet connection. For example, in the field, I'd like to connect
to the Pi using either my Dell XPS 13 or Lenovo laptops with a direct ethernet
connection.

Here is a good resource: https://www.raspberrypi.org/documentation/remote-access/ip-address.md

Specifically, note the tip that you can `SSH` through a connected ethernet
cable over the address `raspberrypi.local` e.g. `ssh pi@rasbperrypi.local`.

Note that this doesn't appear to work when simply hooking the Pi onto an
ethernet connection attached to a switch going into my router.

### Signal Check A GOES Satellite

TODO

### Receive and Process Images

TODO

## Log

### 20181029

Successful signal check 1692.7 MHz.

Had that classic Plateau look to it.

Bandwidth less then 28 kHz wide.

I think that this signal is from the [NOAA EMWIN](http://www.nws.noaa.gov/emwin/EMWINFAQ.htm) system.

NOTE regarding LNAs: The LNAs I currently have do not appear to be helping. I could only see the EMWIN
signal after disconnecting both LNAs in between the antenna and the GOES Sawbird Chip as well as between
the sawbird and the SDR.

Antenna --> LNA --> Sawbird --> LNA --> SDR == No Signal.

Antenna --> LNA --> Sawbird --> SDR == No signal.

Antenna --> Sawbird --> LNA --> SDR couldn't be tested as I couldn't get power to the sawbird while it was
connected directly to the antenna (obstructed usb mini port for power).

Was **unable** to see signal at expected LRIT frequency of 1691.0 MHz.