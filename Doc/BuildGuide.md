#Parts & Preparation
- [Sourcing Components](#sourcing-components)
- [PCB](#pcb)
  - [Uniform PCB](#uniform-pcb)
  - [Required PCB Components](#required-pcb-components)
  - [Optional PCB Components](#optional-pcb-components)
- [Plate](#plate)
- [Case](#case)
- [Keyboard Components](#keyboard-components)
---
##Sourcing Components
Uniform deliberately makes use of components that are generally widely available to make sourcing as easy as possible. The links provided are for the distributors I've personally sourced parts from, however these components may not always be in stock. Components like capacitors, resistors, and diodes *can easily be substituted for virtually any identical variant from another manufacturer* and will generally fit in their through-hole footprints on the PCB. Components with specific footprints like the MCU, Logic Level Shifter, Status LEDs, USB-C Connector, and Power / Reset Switches *require the exact component* to fit correctly on the PCB.

---
##PCB
###Uniform PCB
Personally I use [JLPCB](https://jlcpcb.com/) when ordering PCBs. Most manufacturers will ask you to upload gerber files. In the case of JLPCB, you can simply upload the **UniformGBR.zip** file, which contains all the zipped gerbers. The Uniform PCB gerber files are provided in the **PCB/Uniform/GBR/** section of the repository.
###Required PCB Components
| Component | Mfr. # | Quantity | Est. Price |
|-|-|-|-|
|MCU|[STM32L072KZT6](https://www.mouser.com/ProductDetail/STMicroelectronics/STM32L072KZT6?qs=mwoc%252BQmZlGJ4eN3sEity4A%3D%3D)|1|$7.65|
|Logic Level Shifter|[SN74AHCT1G125DBVR](https://www.mouser.com/ProductDetail/595-SNAHCT1G125DBVR)|1|$0.40|
|Diodes|[1N4148](https://www.mouser.com/ProductDetail/512-1N4148)|68|$5.64|
|NeoPixel Status Led|[5mm Through-Hole 5 Pack](https://www.mouser.com/ProductDetail/YAGEO/MFR-25FRF52-330R?qs=oAGoVhmvjhxv5KjCXy24Qg%3D%3D)|1|$4.95|
|USB-C Connector|[USB4085-GF-A](https://www.digikey.com/en/products/detail/gct/USB4085-GF-A/9859662)|1|$0.94|
|Power / Reset Switch|[OS102011MS2QN1](https://www.digikey.com/en/products/detail/c-k/OS102011MS2QN1/411602)|2|$1.18|
|10µF Capacitor|[FG16X7R1E106KRT06](https://www.digikey.com/en/products/detail/tdk-corporation/FG16X7R1E106KRT06/5802770)|2|$1.34|
|1µF Capacitor|[RDER71H105K2M1H03A](https://www.digikey.com/en/products/detail/murata-electronics/RDER71H105K2M1H03A/4771301)|1|$0.59|
|0.1µF Capacitor|[A104K15X7RF5TAA](https://www.digikey.com/en/products/detail/vishay-beyschlag-draloric-bc-components/A104K15X7RF5TAA/146011)|3|$0.75|
|10 kOhm Resistor|[CFR16J10K](https://www.digikey.com/en/products/detail/te-connectivity-passive-product/CFR16J10K/3317912)|2|$0.20|
|5.1 kOhm Resistor|[RNMF14FTC5K10](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RNMF14FTC5K10/2617363)|2|$0.20|
|330 Ohm Resistor|[MFR-25FRF52-330R](https://www.mouser.com/ProductDetail/YAGEO/MFR-25FRF52-330R?qs=oAGoVhmvjhxv5KjCXy24Qg%3D%3D)|1|$0.10|

###Optional PCB Components
| Component | Mfr. # | Quantity | Est. Price | Note |
|-|-|-|-|-|
|Hot-Swap Sockets|[7305-0-15-15-47-27-10-0](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/7305-0-15-15-47-27-10-0/1765737)|136|$47.16| other [Mill-Max Options](https://divinikey.com/products/mill-max-hotswap-sockets) or [Kailh](https://divinikey.com/products/kailh-hot-swap-sockets) are good alternatives |
|SWD Header|[826629-5](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/826629-5/2276109)|1|$0.71|MCU debug pinout header for debugging and easier flashing|
|330 Ohm Resistor|[MFR-25FRF52-330R](https://www.mouser.com/ProductDetail/YAGEO/MFR-25FRF52-330R?qs=oAGoVhmvjhxv5KjCXy24Qg%3D%3D)|1|$0.10|Necessary if the on-board external LED header will be used|

---
##Plate
A plate provides stability and alignment for your keyboard's switches and is *highly recommended*, especially when using hot-swap sockets. The .svg file for Uniform's plate is provided in the **Ref** directory of the repository, called **uniform_plate.svg**. 
![Uniform Plate](uniform_plate.svg)
There are many options for having plates cut and shipped to you. I've personally used [Ponoko](https://www.ponoko.com/) and have been happy with their quality. Popular plate materials are aluminum and brass, however I've also found acrylic to look and feel quite nice. The thickness of the plate is determined by the type of switches you intend to use. Most switches (including MX style switches) fit best with a **1.5mm** thick plate.

---
##Case
Uniform does not have its own case (yet!). 

The mounting holes provided on the PCB fit **M2.5** screws.

The PCB is designed to fit into a [TOFU65](https://kbdfans.com/collections/tofu65), however the mounting holes *do not line up* due to the ortholiner positioning of the keys blocking the TOFU's original standoffs. I've personally had success removing the original standoffs on the TOFU with a dremel, 3D printing some standoffs with heatset 2.5M inserts, then fixing the attached standoffs to the case with doublesided foam tape so the PCB can be mounted to them. The USB-C port position *does* align on the TOFU65.

Alternatively, [M2.5 standoffs](https://www.amazon.com/gp/product/B01L06CUJG/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) can be had for cheap, and can be used to prop the PCB up off the desk for an exposed-PCB look. I've typed many *many* hours with Uniform keyboard prototypes set up this way.

---
##Keyboard Components
Uniform has an unconventional layout which requires a special set of keycaps. 

![Uniform Layout](keyboard-layout.PNG)

**This layout requires:**
- **68x** Switches
- **11x** 1.5u keycaps
- **57x** 1u keycaps

I find DSA and XDA keycap profiles to be easiest to work with because the keycap shape doesn't change based on the row, making sourcing a complete set for an unconventional layout easier.

![Keycap Profiles](keycap-profiles.png)

These keycap profiles are less popular when compared to Cherry, so finding sets you like can be challenging. If you're a fan of blank keycaps, a great option is to order blank sets from sellers on [Aliexpress](https://www.aliexpress.com/). Many of these distributors will make you custom batches with exactly the number of keycaps of each size that you need, and some will even make them in custom colors. I've found the easiest way to put together a complete set of keycaps for this keyboard is to combine an existing DSA or XDA set with blank 1.5u keycaps from Aliexpress.

Finally, **Don't forget to order a USB-C Cable!**

---

#Assembly
- [PCB Assembly](#pcb-assembly)
- [Switch & Plate](#switch-&-plate )
- [Case Assembly & Mounting](#case-assembly-&-mounting)
##PCB Assembly
##Switch & Plate
##Case Assembly & Mounting

