# Uniform Build Guide
- [Parts and Preparation](#parts-and-preparation)
  - [Tools](#tools)
  - [PCB](#pcb)
  - [Plate](#plate)
  - [Keyboard Components](#keyboard-components)
  - [Case](#case)
- [Assembly](#assembly)
  - [PCB Assembly](#pcb-assembly)
    - [Main Components](#main-components)
    - [Diodes](#diodes)
    - [Hot-Swap Sockets](#hot-swap-sockets)
  - [Case Assembly](#case-assembly)
  - [Switches and Keycaps](#switches-and-keycaps)
- [Flashing Firmware](#flashing-firmware)


---
# Parts and Preparation
Before beginning assembly, it's a good idea to have a plan for each required component. The following subsections will explore these components in greater detail. **Here's a top-level rundown of everything you'll need to source yourself**, including hyperlinks to the corresponding subsections below.

- The [Uniform PCB](#pcb)
- All [Required PCB Components](#required-pcb-components)
- Any [Optional PCB Components](#optional-pcb-components)
- A [Plate](#plate), if desired (*strongly recommended*)
- A [Case](#case) (your choice may necessitate addititonal materials and tools)
- **(68x)** Switches of your choice
- **(11x)** 1.5u keycaps
- **(57x)** 1u keycaps
- A USB-C cable
- All required [Tools](#tools)

---
## Tools
|Tool|Purpose|Necessity|
|-|-|-|
| Soldering Iron & Solder | Soldering components onto the PCB | Required |
| Small Phillips Head Screwdriver | Case assembly and mount screws | Required |
| Tweasers | Hold small components in place while soldering | Recommended |
| Soldering Wick | Desoldering - fixing mistakes and removing excess solder | Recommended |
| Flux Paste | Help solder flow better for surface mount components | Recommended |
| Tape | keep odd-shaped components in place while soldering the first pin  | Recommended |

---
## PCB
**[Download the Uniform PCB gerber files here](https://github.com/patrickhirsh/Uniform-Keyboard/tree/main/PCB/Uniform/GBR)**

I don't sell or distribute PCBs myself, so you'll need to order your own through a PCB manufacturer of your choice. I usually use [JLPCB](https://jlcpcb.com/), but you may want to shop around to find the supplier that gets you the best deal. Most manufacturers will ask you to upload gerber files. In the case of JLPCB, you can simply upload the **UniformGBR.zip** file, which contains all the zipped gerbers.

Uniform makes use of components that are generally widely available to make ordering components as easy as possible. The links provided are for the distributors I've personally sourced parts from, however these components may not always be in stock. Components like capacitors, resistors, and diodes can easily be substituted for virtually any identical variant from another manufacturer and will generally fit in their through-hole footprints on the PCB. Components with specific footprints like the MCU, Logic Level Shifter, Status LEDs, USB-C Connector, and Power / Reset Switches *require the exact component* to fit correctly on the PCB.

### Required PCB Components
| Component | Mfr. # | Quantity | Est. Price |
|-|-|-|-|
|MCU|[STM32L072KZT6](https://www.mouser.com/ProductDetail/STMicroelectronics/STM32L072KZT6?qs=mwoc%252BQmZlGJ4eN3sEity4A%3D%3D)|1|$7.65|
|Voltage Regulator|[TLV1117-33IDCYG3](https://www.digikey.com/en/products/detail/texas-instruments/TLV1117-33IDCYG3/1677131)|1|$0.89|
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
|**Total**|||**$24.40**|

### Optional PCB Components
| Component | Mfr. # | Quantity | Est. Price | Note |
|-|-|-|-|-|
|Hot-Swap Sockets|[7305-0-15-15-47-27-10-0](https://www.digikey.com/en/products/detail/mill-max-manufacturing-corp/7305-0-15-15-47-27-10-0/1765737)|136|$47.16| other [Mill-Max Options](https://divinikey.com/products/mill-max-hotswap-sockets) or [Kailh](https://divinikey.com/products/kailh-hot-swap-sockets) are good alternatives |
|SWD Header|[826629-5](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/826629-5/2276109)|1|$0.71|MCU debug pinout header for debugging and easier flashing|
|330 Ohm Resistor|[MFR-25FRF52-330R](https://www.mouser.com/ProductDetail/YAGEO/MFR-25FRF52-330R?qs=oAGoVhmvjhxv5KjCXy24Qg%3D%3D)|1|$0.10|Necessary if the on-board external LED header will be used|
|**Total**|||**$47.97**||

---
## Plate
**[Download the Uniform plate .svg file here](https://github.com/patrickhirsh/Uniform-Keyboard/blob/main/Ref/uniform_plate.svg)**

There are many options for having plates cut and shipped to you. I've personally used [Ponoko](https://www.ponoko.com/) and have been happy with their quality. Popular plate materials are aluminum and brass, however I've also found acrylic to look and feel quite nice. The thickness of the plate is determined by the type of switches you intend to use. Most switches (including MX style switches) fit best with a **1.5mm-1.6mm** thick plate.

**Note:** the plate does *not* include holes drilled for mount screw access through the plate. This is because adding mount holes into the plate template results in cuts too dense for most laser cutting services. If mount screw access through the plate is important to you, the best option is to drill the holes yourself after receiving the plates. Be mindful of the plate material chosen if this is your plan. I've found Aluminium to be quite easy to drill through, but materials like acrylic to be far too brittle to drill into without cracking or shattering.

**Why doesn't the plate include cuts for mount screw access holes?** 
> Adding mount holes into the plate file results in a very small amount of plate material between the holes and the corner of the switch cutouts. These thin bits of material typically don't meet the spec of most laser cutting services. Fortunately it's pretty easy to drill holes into your plate yourself with a regular drill and drill bits. Be mindful of the plate material chosen if this is your plan. I've found Aluminium to be quite easy to drill through, but materials like acrylic to be far too brittle to drill into without cracking or shattering.

**Why should I drill mount screw access holes into the plate?** 
> Drilling holes into the plate above all the mount screw positions on the PCB allow you to unscrew the PCB from the case without taking out all the switches. If you don't have holes in the plate, the plate will cover the PCB mount screws, meaning the only way to get to them is to remove *all the switches and keycaps* so you can pop the plate off. If you've got hot-swap switches, this isn't a big deal (10 minutes tops to get the plate off). With soldered switches, mount screw access holes is *basically a requirement* unless you intend to desolder all your switches every time you need to remove your PCB from its case 😉.

---
## Keyboard Components
Uniform has an unconventional layout, which means a special set of keycaps is required. 

![Uniform Layout](Uniform_Layout.PNG)

**This layout requires:**
- **(68)** total switches
- **(11)** 1.5u keycaps
- **(57)** 1u keycaps

I find DSA and XDA keycap profiles to be easiest to work with. Many sellers on [Aliexpress](https://www.aliexpress.com/) can make custom batches of 1u and 1.5u blank keycaps, which makes it easier to build a complete keycap set. I like using blanks for all my keys, so I typically put in a single order for all the 1u and 1.5u keycaps from the same distributor so I can guarantee a perfect color match.

Finally, **Don't forget to order a USB-C Cable!**

---
## Case
Uniform does not have its own case (yet!). 

### Mounting Information

The 10 primary mounting holes provided on the PCB fit **M2.5** screws.

![Uniform PCB Wireframe Main Mounts](Uniform_PCB_Wireframe_Main_Mounts.png)

There are 2 additional **M2.5** mount holes on the left side of the board. These are designed to fit standoffs for an acrylic component shield.

![Uniform PCB Wireframe Acrlic Mounts](Uniform_PCB_Wireframe_Acrylic_Mounts.png)

### TOFU65
To get this project off the ground, the Uniform PCB was designed to fit into a [TOFU65](https://kbdfans.com/collections/tofu65). 

![Uniform Tofu65 Mounting](Uniform_Tofu65_Example.jpeg)

The USB-C Port lines up with the case cutout and the PCB dimensions match those of other compatible TOFU65 PCBs. **The only caveat is that the PCB mount holes *do not* line up with those in the TOFU65**. This is a limitation of the ortholinear layout Uniform utilizes - the mount points overlap with switch positions on Uniform's board, making it impossible to accomodate them. This means you will need to come up with your own mounting solution if you'd like to build this keyboard in a TOFU65 case. 

I've personally done this for the first three prototypes of this board by dremeling off the original standoffs and 3D printing my own using [M2.5 heatset inserts](https://www.amazon.com/gp/product/B08GWKW1K7/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) and [M2.5 screws](https://www.amazon.com/gp/product/B09WJ4WF9K/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1). The 3D printed parts are just cylinders which I've heatset the threaded inserts into, then used double-sided foam tape to fix into the bottom of the case. 

![Uniform Tofu65 Mounting](Uniform_Tofu65_Mounting.jpeg)

If you decide to go this route, it's easiest to screw the standoffs into the bottom of the PCB first, apply the adhesive, then press the entire board down into the bottom of the modified Tofu65 case. **Do this with switches and keycaps installed on all four corners of the board to ensure the keycaps have clearance!** 

### Caseless Build

Alternatively, [M2.5 standoffs](https://www.amazon.com/gp/product/B01L06CUJG/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) can be had for cheap, and can be used to prop the PCB up off your desk for an exposed-PCB look. I've typed many *many* hours with Uniform keyboard prototypes set up this way.

Simply screw an M2.5 screw through the top of the PCB into a standoff on the bottom side of the case. I like to put one in each corner, using two taller standoffs in the back for a sloped typing surface. It's worth putting rubber adhesive feet on the bottom of these standoffs to keep the keyboard from sliding around.

---
# Assembly
- [PCB Assembly](#pcb-assembly)
  - [Main Components](#main-components)
  - [Diodes](#diodes)
  - [Hot-Swap Sockets](#hot-swap-sockets)
- [Switches and Keycaps](#switches-and-keycaps)
- [Case Assembly and Mounting](#case-assembly-and-mounting)
- [Flashing Firmware](#flashing-firmware)
---
## PCB Assembly
![Complete Assembly](Uniform_Complete_Assembly.jpeg)
Total estimated time to completion: **3 hours** (**4.5 hours** with hot-swap)

### Main Components
Estimated time to completion: **1.5 hours**

---

1. Solder the **STM32L072KZT6** MCU component to the PCB at **U1**, taking care to align the dimpled corner on the chip with the white dot on the PCB.
&nbsp;
This is the most difficult component to solder to the board, so take your time and ensure none of the pins are left bridged together. A little flux paste applied to the surface of the pads before soldering makes the solder flow much easier. 
&nbsp;
I like to start by soldering a single pin from the MCU to the board. Then, while heating the pin with the soldering iron, I use tweasers to shift the MCU's position until its' feet are aligned with the rest of the pads on the board. Once heat is released from the pin, the chip is fixed in place. Apply the minimum amount of solder necessary to create a clean connection between the remaining pins and their pads.
&nbsp;
![MCU Closeup](Uniform_MCU_Closeup.jpeg)

---

2. Solder the **SN74AHCT1G125DBVR** Logic Level Shifter to the PCB at **U2**.
&nbsp;
![Logic Level Shifter](Uniform_Logic_Level_Shifter.png)

---

3. Solder the **TLV1117-33IDCYG3** Voltage Regulator to the PCB at **VREG1**.
&nbsp;
![Voltage Reg](Uniform_Voltage_Reg.png)

---

4. Solder the **USB4085-GF-A** USB-C Connector to the PCB at **USBC1**. Take care to not bridge any pin connections. Only the *bottom two fins* nearest the pins need to be soldered into the socket (as shown below). 
&nbsp;
![USBC Connector](Uniform_USBC_Connector.png)

---

5. Solder the two **10 µF capacitors** to the PCB at **C1** and **C2**. These capacitors are not polarized, so they can be soldered in either orientation. 
&nbsp;
It's easier to first seat the components flush to the board, then bend the legs to secure them in place *before* soldering.
&nbsp;
![Uniform 10u Back](Uniform_10u_Back.jpeg) 
&nbsp;
![Uniform 10u Cap](Uniform_10u_Cap.jpeg)
&nbsp;
Once soldered, clip the excess wire.

---

6. Solder the single **1 µF capacitor** to the PCB at **C6**. This capacitor is not polarized, so it can be soldered in either orientation.
&nbsp;
![Uniform 1u Cap](Uniform_1u_Cap.jpeg)

---

7. Solder the three **0.1 µF capacitors** to the PCB at **C3**, **C4**, and **C5**. These capacitors are not polarized, so they can be soldered in either orientation.
&nbsp;
![Uniform 0.1u Cap](Uniform_0.1u_Cap.png)

---

8. Solder the two **10 kOhm resistors** to the PCB at **R3** and **R4**. These resistors can be soldered in either orientation.
&nbsp;
![Uniform 10k Res](Uniform_10k_Res.png)

---

9. Solder the two **5.1 kOhm resistors** to the PCB at **R1** and **R2**. These resistors can be soldered in either orientation.
&nbsp;
![Uniform 5.1k Res](Uniform_5.1k_Res.png)

---

10. Solder the three **NeoPixel Status Leds** to the PCB at **L1**, **L2**, and **L3**. Orientation *does* matter. Take care to ensure the longer legs are seated on the right side of the footprint (the side with the rectangular pad).
&nbsp;
![Uniform LED Front](Uniform_LED_Front.jpeg)
&nbsp;
I like to start by only soldering one pin on each LED, that way I can heat the solder on one side and press the LED flush to the board with the other - ensuring it's seated right. Be extra careful when handling the top of the LED while heating its pins on the other side of the board. Don't burn yourself! 
&nbsp;
![Uniform LED Back](Uniform_LED_Back.png)
&nbsp;
Once the first pin is soldered and you're happy with how the LED is seated, solder the other pins in place.

---

11. Next are the **330 Ohm resistors**. Soldering one into **R5** is *required*, and is used to smooth the data signal to the status LEDs. **R6** is *only necessary if you intend to use the external LED pinout* at **L4**; it's used to smooth L4's data line.
&nbsp;
![Uniform 330 Res](Uniform_330_Res.png)

---

12. Solder the two **OS102011MS2QN1** Reset and Power switches into the PCB at **S1** and **S2**. 
&nbsp;
I like to tape the switches into place while I solder the first pin, then heat the solder from the bottom while seating the switch into place by pressing it down from the top with my other hand (same technique as used with the status LEDs). The switches are metal and *will get very hot* while applying heat to the pins, so be careful when doing this:
&nbsp;
![Uniform Toggle Front](Uniform_Toggle_Front.jpeg)
![Uniform Toggle Back](Uniform_Toggle_Back.png)
&nbsp;
Once the switches are seated and aligned to your liking, solder the remaining pins to fix the switches in place. You do not need to apply solder to the outer pegs, only the inner 3 pins.
&nbsp;
![Uniform Toggle Final](Uniform_Toggle_Final.jpeg)

---

13. **(Optional)** If you've purchased the **826629-5** 5-pin header for SWD debugging, solder it to the PCB at **SWD1**. 
&nbsp;
I used the same tape, single pin, heat and re-seat technique for this component as well. Take *extra care* here where handling the header while heating the pins as you'll be in contact with the *same metal pins that you're heating from the bottom*. Be sure not to touch the pin you're currently heating when reseating the header. 
&nbsp;
![Uniform SWD](Uniform_SWD.png)

---

**We're Halfway There!**

If you've made it this far, nice work! Give yourself a pat on the back. We've just finished soldering all the main components. Your board should look something like this:

![Uniform Main Components](Uniform_Main_Components.jpeg)

---

## Diodes
Estimated time to completion: **1.5 hours**

This part is a little tedious. We're going to be soldering all 68 **1N4148** diodes to their respective positions on the PCB - one per switch. 

You'll find their positions on the board adjacent to each switch, denoted **D_\<Row\>_\<Column\>**. Orientation **does matter**, so be sure that the diode is oriented such that current flows *down* from the switch to the row trace. on our 1N4148 diodes, this means the **black band on the diode should be on the *bottom***

![Uniform Diode Orientation](Uniform_Diode_Orientation.png)

The most time consuming part of this whole step is bending and fiddling with the legs of the diodes to get them to fit centered in their footprint on the board. In my experience, the fastest way to do this is to find a flat tool that can be used to reliably bend the diodes in the same place every time. 

Here I'm using a pair of tweasers. I've found the point on the tool where the width causes the diode to bend at the right points, and I'm keeping my pointer finger here as I bend each diode so they all come out the same. This dramatically speeds up the process as all the diodes fit perfectly without too much fiddling.

![Uniform Diode Bend](Uniform_Diode_Bend.jpeg)
![Uniform Diodes](Uniform_Diodes.jpeg)

I like to pre-bend all the diodes first, then fit and secure them in place by bending their legs on the back of the PCB before doing any soldering.

*This is a good time to double-check that all the diodes are oriented the correct way!* 

![Uniform Diodes Front](Uniform_Diodes_Front.jpeg)
![Uniform Diodes Back](Uniform_Diodes_Back.jpeg)

Finally, solder all the diodes in place and clip the excess wire. You should end up with something like this:

![Uniform Diodes Final](Uniform_Diodes_Final.jpeg)

---

## Hot-Swap Sockets
**(Optional)**

Estimated time to completion: **1-2 hours**

If you've purchased hot-swap sockets, now's the time to solder them to the PCB. Installing these can be *really* tedious... and they're also quite expensive. In my opinion, though, it's well worth it for the ability to hot-swap switches. 

Personally, I like the **Mill-Max 7305** sockets best. The tips in this section really only apply to Mill-Max style hot-swap sockets, but plenty of guides exist for other hot-swap options.

![Uniform HotSwap Sockets](Uniform_HotSwap_Sockets.jpeg)

**Mill-Max 7305** sockets fit into the switch sockets (two per switch) with the ridge sitting on the top side of the PCB as shown below. This means you'll need to solder **136** sockets in total.

![Uniform HotSwap Ridge](Uniform_HotSwap_Ridge.png)

To ensure the sockets are aligned such that the switches aren't crooked when inserted, fit all the sockets *without* soldering first. Snap the switches through the plate and insert them into the hot-swap sockets. Make sure each switch socket contains a hotswap socket before inserting the switch.

![Uniform HotSwap Switch Insert](Uniform_HotSwap_Switch_Insert.jpeg)

To save yourself from turning 1-2 hours of work into 3+ hours of anguish, *only insert a handful of sockets at a time and secure them in place with switches before inserting more*. This *does* mean you'll have to carefully insert the sockets with tweasers to reach between the swich plate, which *is* more difficult than putting them all in by hand first without the switch plate in the way, but *trust me*, it's far better this way. 

You'll inevitably pop a switch into the plate with a *little* too much force, and there's nothing more frustrating than watching all the sockets you carefully inserted into the switch sockets over the last hour pop out all at once. They're very light and tend to jump out of their sockets at even the slightest "pop". 

I can't tell you how many times I got greedy and had to re-learn this lesson...

![Uniform HotSwap Dry Fit](Uniform_HotSwap_Dry_Fit.jpeg)

Once all the sockets and switches have been inserted, carefuly flip the entire board over.

![Uniform HotSwap Dry Fit Back](Uniform_HotSwap_Dry_Fit_Back.jpeg)

On the back of the PCB, the hot-swap sockets should protrude slightly. we'll be applying a small amount of solder to the outside of the socket wall, fixing the socket in place. 

![Uniform HotSwap PreSolder](Uniform_HotSwap_PreSolder.png)

Apply slight pressure to the board as you solder each socket to ensure the socket and switch are sitting flush with the board as they're fixed in place. **Be careful not to get solder inside the socket!**

![Uniform HotSwap PostSolder](Uniform_HotSwap_PostSolder.png)

Once all the sockets have been soldered in place, pop the switches out to ensure none have been soldered into their sockets. 

![Uniform HotSwap Final](Uniform_HotSwap_Final.jpeg)

Patiently applying heat through a soldering wick is the best way to clean up a flooded socket if you've managed to get solder inside one. Eventually, you should be able to wiggle the switch free while applying heat to the pins.


---

## Case Assembly
Uniform does not have its own case (yet!). 

See the [Case](#case) section for more info on cases or other mounting options.

## Switches and Keycaps
Finally, it's time to add the switches and keycaps!

To install switches, you'll need to snap them through their openings in the plate (if you have one) and into the switch sockets on the PCB. Make sure the North side of the switch faces the top of the board. You can use the switch pins to orient them correctly. For most MX-style switches, the rounded protruding side is the North side of the switch. On the [NK Creams](https://novelkeys.com/products/nk-cream-series) shown here, you can see it's the side with the *Kailh* lettering.

![Uniform Switch Install](Uniform_Switch_Install.jpeg)

Take care to ensure the two switch pins enter the socket. It's easy to accidentally bend a pin flat against the switch when snapping the switches into place.

I find it easier to snap the four corner switches into the plate, then fit the whole plate on the PCB before installing the other switches. This helps stabilize the plate in the correct place above the board and makes it easier to snap the other switches in place.

![Uniform Switches Installed](Uniform_Switches_Installed.jpeg)

If you have hot-swap sockets installed, then all you need to do is pop on the keycaps and you're done! 

Otherwise, you'll need to flip the board over and [solder all the switch pins into place](https://thekeeblog.com/soldering-101-mechanical-keyboard-soldering-basics-and-useful-tips/) before installing keycaps.

# Flashing Firmware

**(Coming Soon)**

Uniform's QMK branch hasn't been integrated into QMK yet. For now, you'll have to clone the [fork](https://github.com/patrickhirsh/qmk_firmware/tree/uniform) and flash the firmware yourself using [QMK Toolbox](https://github.com/qmk/qmk_toolbox).

