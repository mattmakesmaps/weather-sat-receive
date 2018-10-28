# NOAA GOES

# Objective

Receive full disk images from the NOAA GOES System.

# Experiment Phases

1) Assemble Receiver Box
2) Assemble Antenna
3) Raspberry Pi Configuration
4) Signal Check A GOES Satellite
5) Receive and Process Images

## Assemble Receiver Box

## Assemble Antenna

## Raspberry Pi Configuration

One objective is to connect to the Pi over SSH from multiple host computers
via direct ethernet connection. For example, in the field, I'd like to connect
to the Pi using either my Dell XPS 13 or Lenovo laptops with a direct ethernet
connection.

Here is a good resource: https://www.raspberrypi.org/documentation/remote-access/ip-address.md

Specifically, note the tip that you can `SSH` through a connected ethernet
cable over the address `raspberrypi.local` e.g. `ssh pi@rasbperrypi.local`.

Note that this doesn't appear to work when simply hooking the Pi onto an
ethernet connection attached to a switch going into my router.

## Signal Check A GOES Satellite

## Receive and Process Images
