# keyboard
My design for a lily58 inspired split wireless keyboard using ergogen and kicad.
One of my friends has significant wrist pain because his laptop keyboard is terrible. A few months ago we were planning to make a keyboard together and made things in Ergogen but never got that much further than that. Now, I have put things into kicad and done a bit more work in preparing things to be actually manufactured.
This is designed to be pretty much as cheap a keyboard as it is possible to manufacture, aiming for about AU$50 per keyboard (I am making two of these, so more like $100 total). This comes out to about $30 USD per keyboard, $60 total.

## Design
### PCB
- Ergogen for PCB design and layout drafting. It is a very simple, user friendly and powerful program. You define layouts for rows and columns, and nets to connect them
  - Note: In my Ergogen file there is a single net that was not correct, and I had to route manually in KiCad
- KiCad for routing the pcb. Ergogen creates the nets, so I only have to route it -- as such, there is no kicad schematic file, just a pcb file that I edited to design
- PCB: AllPcb. They had a cheap offer which let me get everything for a $2, including delivery.

### Case Design:
I use Fusion 360 in school, and am quite used to the program, so that is what I will use. As of November 1 2025, I haven't fully decided on the design -- but what I am thinking is that i will use a clean looking white coloured case, with an oiled plywood or even Jarrah laser cut bottom plate that fits in. My school has a good 3d printer (bambu p1s) and a laser cutter, so I can get everything designed there.
Ergogen outputs a DXF file for the bottom shape of the case, which is defined through the ```outlines``` section of ergogen.yml. This is the shape that I use for the outline of my PCB, so I will need to make an offset line around and use that as the case outline.
Also, since I will be taking this keyboard to and from school, I will make a hinging case to place the two halves in with foam padding for safety.

### Software
I will probably just go with zmk for this. One thing that is important to me is for the keyboard to run both wired and wireless - eg I plug one half with a usb C to A port into a school computer, and then that half talks to the other half and I can use it on computers without Bluetooth support; but I believe that QMK has this function so I will just use that. Potentially, if I have extra time, then I could code something custom in C, but I am not sure whether this is feasible at this point and with exams coming up.

# Images
![Initial Ergogen Design](./img/ergogen.png)
![Kicad PCB, ready to be ordered](./img/kicadDesign.png)
![Allpcb Order](./img/allpcbOrder.png)
