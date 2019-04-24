# NOAA GOES Reception Notes

## Objective

Receive full disk images from the [NOAA GOES Network](https://www.nasa.gov/content/goes-overview/index.html).

From my location in Seattle, WA, I'm specifically trying to catch signals from GOES-15 and GOES-17.

## Current Hardware

- [Nooelec SAWBird+ Filter/LNA](https://www.nooelec.com/store/sawbird-plus-goes.html)
- [50-4000MHz LNA](https://www.amazon.com/gp/product/B076ZQTY8S/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)
- [Altelix 2.4GHz Antenna](https://www.amazon.com/gp/product/B06ZYSRDJT/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1). **NOTE:** The antenna has been modified to extend the forward reflector as [noted in this reddit post](https://www.reddit.com/r/RTLSDR/comments/9ahdzc/modification_of_wifi_grid_antenna_to_make_it_work/).
- [NooElec SMArTee XTR SDR](https://www.amazon.com/gp/product/B06Y1D7P48/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)

## Software

- [SDR Sharp](https://airspy.com/download/): Used for inspection of waterfall on windows.
- [GOESTools from pietrn](https://github.com/pietern/goestools): A suite of software for receive and processing of GOES signals.

## Existing Tutorials/References

- [A minimal LRIT/HRIT reciever](https://pietern.github.io/goestools/guides/minimal_receiver.html) - From the `goestools` project page.

# Project Notes

## April 21, 2019

![EMWIN Signal](./images/emwin_goes15.PNG)