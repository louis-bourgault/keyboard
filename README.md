# keyboard
*my project for hack club blueprint*

My design for a lily58 inspired split wireless keyboard using ergogen and kicad. It uses the NRF52840 chipset, and 3d printed parts mostly

One of my friends has significant wrist pain because his laptop keyboard is terrible. A few months ago we were planning to make a keyboard together and made things in Ergogen but never got that much further than that. Now, I have put things into kicad and done a bit more work in preparing things to be actually manufactured.
This is designed to be pretty much as cheap a keyboard as it is possible to manufacture, aiming for about AU$50 per keyboard (I am making two of these, so more like $100 total). This comes out to about $30 USD per keyboard, $60 total.

## Design
### PCB
- Ergogen for PCB design and layout drafting. It is a very simple, user friendly and powerful program. You define layouts for rows and columns, and nets to connect them
  - Note: In my Ergogen file there is a single net that was not correct, and I had to route manually in KiCad. This is the upper thumb cluster key.
- KiCad for routing the pcb. Ergogen creates the nets, so I only have to route it -- as such, there is no kicad schematic file, just a pcb file that I edited to design
- PCB: AllPcb. They had a cheap offer which let me get everything for a $2, including delivery.

### Case Design:
I use Fusion 360 in school, and am quite used to the program, so that is what I will use. As of November 1 2025, I haven't fully decided on the design -- but what I am thinking is that i will use a clean looking white coloured case, with an oiled plywood or even Jarrah laser cut bottom plate that fits in. My school has a good 3d printer (bambu p1s) and a laser cutter, so I can get everything designed there.
Ergogen outputs a DXF file for the bottom shape of the case, which is defined through the ```outlines``` section of ergogen.yml. This is the shape that I use for the outline of my PCB, so I will need to make an offset line around and use that as the case outline.
Also, since I will be taking this keyboard to and from school, I will make a hinging case to place the two halves in with foam padding for safety.

### Software
I will probably just go with zmk for this. One thing that is important to me is for the keyboard to run both wired and wireless - eg I plug one half with a usb C to A port into a school computer, and then that half talks to the other half and I can use it on computers without Bluetooth support; but I believe that QMK has this function so I will just use that. Potentially, if I have extra time, then I could code something custom in C, but I am not sure whether this is feasible at this point and with exams coming up.

Note: this software is in a seperate repo because of the way that ZMK works. The repo is [louis-bourgault/zmk-config](https://github.com/louis-bourgault/zmk-config)

# Images
![Initial Ergogen Design](./img/ergogen.png)
![Kicad PCB, ready to be ordered](./img/kicadDesign.png)
![Allpcb Order](./img/allpcbOrder.png)
![Screenshot of case design in Fusion 360](./img/caseScreenshot.png)

# Bill of Materials

| **Component Type** | **Item Link** | **Quantity needed** | **Relevant Specifications** | **Tax % (if not included)** | **Price each (AUD)** | **Total Cost (AUD)** | **Total Cost (USD) (using 1 AUD = 0.65 USD)** | Running Cost (AUD | Running Cost (USD) | **Note** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Battery * 2 | https://www.ebay.com.au/itm/336259992666?_skw=ps3+wireless+controller+battery&itmmeta=01K8ZTCM719EJ21ZXZGJHHPQJR&hash=item4e4aa84c5a:g:SJ0AAeSwVplo5ynG&itmprp=enc%3AAQAKAAAA4FkggFvd1GGDu0w3yXCmi1dzvTN3qpMFF4QZvvcKRJ4kGSEDp5SODjOtDfXZZOOhebLqIGLXRCt56QoZTRzodsUe5IMSCJ0sdz4Yj3zl%2FI%2B%2Bs04axe26pL56zRkyskJOokE7wjZnXUuk5sPMCygTtr7rSwoApzQf%2FY%2FZIcBncTgdoZU%2BB38F4gxoSGYWCLQ363qgeGGiIYszXG5av1qBie0C1E93ns0c7BEOxN20eGrtT841iVek%2F2lxzTXYzI3QsEOaO3P0k2ueESQk6h5mwTA5s1OAxlVCh5iRG7P7G0Df%7Ctkp%3ABlBMUNTDsvrHZg) | 2 | 3.7v, 400mAh, 53x36x6mm, JSTPH | 0.00% | $11.22 | $22.44 | $14.59 | $22.44 | $14.59 |  |
| NRF52840 | https://www.aliexpress.com/item/1005006035267231.html?afTraceInfo=1005006035267231__pc__c_ppc_item_bridge_pc_main__3EUczl2__1762002951010 | 4 |  | 10.00% | $5.65 | $24.86 | $16.16 | $47.30 | $30.75 |  |
| Keyboard Switch * 110 | https://www.aliexpress.com/item/1005006376024657.html?mp=1 | 1 | Gateron Brown * 110 | 10.00% | $18.33 | $20.16 | $13.11 | $67.46 | $43.85 | This is using my Welcome Deal on Aliexpress |
| Keyboard Switch * 10 | https://www.aliexpress.com/item/1005006376024657.html?mp=1 | 1 | Gateron Yellow * 10 | 10.00% | $4.70 | $5.17 | $3.36 | $72.63 | $47.21 | Supplemental Switches, not on welcome deal so substantially more expensive. Will use different type of switch (linear instead of tactile) for modifier keys |
| Diodes * 200 | https://www.aliexpress.com/item/1005009896621714.html | 1 | Basic 1n4148 diodes | 10.00% | $5.94 | $6.53 | $4.25 | $79.17 | $51.46 |  |
| PCB * 5 | AllPCB | 1 | Custom designed PCB for the system | 0.00% | $2.14 | $2.14 | $1.39 | $81.31 | $52.85 | already purchased |
| Keycaps | https://www.alibaba.com/product-detail/Multi-color-1U-DSA-Blank-Customized_1600930061454.html?spm=a27aq.29918103.4207392620.85.2ffa50df59KEER | 116 | Simple keycaps in variety of colours | 10.00% | $0.23 | $29.90 | $19.43 | $111.20 | $72.28 | Free shipping up to $30 with new Alibaba account |
