# NOAA GOES Reception Notes

### Objective

Receive full disk images from the [NOAA GOES Network](https://www.nasa.gov/content/goes-overview/index.html).

From my location in [Seattle, WA, USA](https://www.openstreetmap.org/#map=11/47.6500/-122.3000) I'm specifically trying to catch signals from GOES-15 and GOES-17.

### Current Hardware

- [Nooelec SAWBird+ Filter/LNA](https://www.nooelec.com/store/sawbird-plus-goes.html)
- [50-4000MHz LNA](https://www.amazon.com/gp/product/B076ZQTY8S/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1) (2x available)
- [Altelix 2.4GHz Antenna](https://www.amazon.com/gp/product/B06ZYSRDJT/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1). **NOTE:** The antenna has been modified to extend the forward reflector as [noted in this reddit post](https://www.reddit.com/r/RTLSDR/comments/9ahdzc/modification_of_wifi_grid_antenna_to_make_it_work/).
- [NooElec SMArTee XTR SDR](https://www.amazon.com/gp/product/B06Y1D7P48/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)
- Raspberry Pi 3

### Software

- [SDR Sharp](https://airspy.com/download/): Used for inspection of waterfall on windows.
- [GOESTools from pietrn](https://github.com/pietern/goestools): A suite of software for receive and processing of GOES signals.

### Existing Tutorials/References

- [A minimal LRIT/HRIT reciever](https://pietern.github.io/goestools/guides/minimal_receiver.html) - From the `goestools` project page.
- [2.4GHz Antenna Mod](https://www.reddit.com/r/RTLSDR/comments/9ahdzc/modification_of_wifi_grid_antenna_to_make_it_work/)
- See [README.md](README.md) for additional links.

## Project Log

### April 21, 2019

My general hardware setup is as follows:

`Antenna --> SawBIRD+ Filter/LNA --> LNA --> SMAarTee XTR SRD`

I had first attempted to connect the SDR directly to the RaspberryPi for processing using `goesrecv` (part of the `goestools` suite).

However, from my location in [Seattle, Washington, USA](https://www.openstreetmap.org/#map=11/47.6500/-122.3000), I was consistently getting Viterbi values of ~2000, which indicates no signal according to the `goestools` [tutorial](https://pietern.github.io/goestools/guides/minimal_receiver.html#software).

In an attempt to simplify my problem space, I removed `goestools` and the Pi from my setup, and directly connected the SDR to my laptop. From there I could visualize the signal waterfall using SDR#.

My understanding from the [GOES Documentation](https://www.goes-r.gov/users/hrit-links.html) is that the following frequencies are used to broadcast data from the GOES network:

- LRIT: 1691.0 MHz
- HRIT: 1694.1 MHz
- EMWIN (GOES-15): 1692.7 MHz

Using the waterfall display, I scanned each of these frequencies while positioning the antenna towards GOES-15 and GOES-17. I also re-oriented the antenna for horizontal/vertical polarization.

I was unable to see any discernible signal for the LRIT and HRIT data (which was backed up by the ~2000 Viterbi values using `goesrecv`).

However, I was able to detect what I assume is the EMWIN signal for GOES-15 at 1692.7 MHz (See Image Below).

![EMWIN Signal](./images/emwin_goes15.PNG)

**Outstanding Questions:**

- Is the signal I am seeing in the SRD Sharp waterfall actually the GOES-15 EMWIN signal?
- Is my high Viterbi value when using `goesrecv` caused by poor signal strength?
  - If so, what can be done to increase signal strength?
  - If not, why am I receiving what I believe to be an EMWIN signal from GOES 15?

Additionally, I've tried a few different combinations of connectors. The antenna has a Type-N connector, and all of the other hardware uses SMA connectors. I originally was connecting the connecting the antenna to the SawBIRD+ using a BNC cable, with a Type-N adapter on one end, and an SMA adapter on the other.

In this experiment, I used the above BNC cable, and also tried attaching a Type-N to SMA adaptor directly to the antenna, which allowed me to use SMA jumper cable to connect all hardware. Both configurations yielded the same results.