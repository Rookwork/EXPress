# EXPress

![The EXPress Controller](/readme_assets/EXPress.jpeg)

The EXPress (pronounced ee-ex-press, like EX moves) is a leverless DIY arcade controller with a focus on self expression.

**Features**
- Space for custom art on both the front and back
- Extra keys use MX switches with a slightly wider spacing to accommodate thicker artisan keycaps
- Main keys use Choc switches for faster inputs
- All switches are fully hot swappable
- Runs open-source GP2040-CE firmware for extremely low latency and fully remappable buttons 
- Includes an OLED screen to display layout and current mode

![Custom art](/readme_assets/custom-art.jpg)

Please note that I am providing these files free of charge with no promise of warranty or support. I try to explain the assembly process thoroughly, but it does still require some basic soldering skills and it is possible to mess up. Please take things slow, be careful, and try to enjoy the act of making something. :) 

I suggest reading through the entire guide at least once before deciding to order anything to make sure you understand each step and have the necessary tools. 

## Assembly guide

To assemble an EXPress, first we will need to order some parts. I will show the process using the exact vendors and process that I used, but there are many alternatives if you would like to shop around. The total cost of an EXPress should be around $150, give or take depending on how you get the parts made. 

Throughout this guide you will see expandable sections like this: 
<details>
<summary>"Click me to read more"</summary>
More information!
</details>

This guide is long, so various steps are hidden for readability. If you would like more detailed explanations of each step, just click the arrow to expand it and there will be more text and pictures.

### Ordering parts

We will need to order a few off the shelf parts:
- MCU: [Waveshare RP2040-Zero](RP2040-Zero) | [Amazon link](https://www.amazon.com/RP2040-Zero-High-Performance-Microcontroller-Castellated-Applications/dp/B09KZPCNPL)
- OLED Screen: [SSD1306 128x64px OLED Display](https://hosyond.com/#:~:text=0.96%20inch%20IIC%20OLED%20Module) | [Amazon link](https://www.amazon.com/gp/product/B09T6SJBV5/) | Note that there are lots of similar displays, but I can't guarantee they will fit. Many of these displays have similar measurements, but the tolerances are tight for this part, so I would try to get this exact screen if possible just to be on the safe side.
- 12 Choc v1 switches (whichever kind you want). I suggest a linear switch like Choc Reds, or an even lighter option like Pro Reds or Purpz. 
- 4 MX switches (whichever kind you want, but a 5-pin, PCB mount switch will be slightly more secure). Don't be afraid to try a fun switch you might not otherwise use — You don't hit these keys that often. I used Kailh Box White switches, for example. 
- 12 Choc v1 circular keycaps. I used ones from Junkfood Arcades, but you can also 3D print some, like those from [jfedor](https://github.com/jfedor2/flatbox/tree/master/3d-printed-buttoncaps) whose Flatbox design was a great inspiration to me. 
- 4 MX keycaps (whichever kind you want)
- 4 M5 15mm long Chicago screws | [Amazon link](https://www.amazon.com/gp/product/B09TT3TNPP) (set of several lengths)
- 10-16 M2 screws, 6-8mm long, and nuts | [Amazon link](https://www.amazon.com/gp/product/B0BD2CXW7D) (set of several lengths)

We will also need to get the following parts made:
- Three PCBs: the main body Choc switches mount, the MCU (microcontroller) mount, and the MX switches mount. These are three separate PCBs due to the different heights of these various parts. 
- The body of the case. We'll get this 3D printed. If you have your own 3D printer, you can probably make this yourself and save quite a bit of money.
- The top and bottom plates. We'll get these laser cut from acrylic. 
- Your own custom art

#### Ordering PCBs
<details>
<summary>"Ordering PCBs from JLPCB"</summary>
I used JLPCB for this. Upload each of the PCB zip files (one at a time). The only option you **must** change is the PCB thickness. This should be set to 1mm for each PCB. Do not forget!

![PCB ordering](/readme_assets/JLPCB.png)

You can also change the color if you want, but these will be covered by art, so it's not really necessary.
</details>

#### Ordering body
<details>
<summary>"Ordering body from Shapeways"</summary>
I used Shapeways for this. Upload the body .stl file and double check the dimensions. It should be 199mm x 145mm. Then choose your material. I recommend SLA12, the cheapest option.

![Material](/readme_assets/Shapeways.png)

You can also change the color and finishing, but I have always used the default finishing option and have never had a complaint. The texture of the print will only be on the side of the case, you won't feel it, so it's not that important for it to be smooth.

![Color and finish](/readme_assets/Shapeways2.png)
</details>

#### Ordering plates
<details>
<summary>"Ordering plates from Ponoko"</summary>
I used Ponoko for this. Upload the art plates .svg file. You may need to change the dimensions. 

![Ordering through Ponoko](/readme_assets/Ponoko1.png)

Double-check that the width is 199mm specifically. Also, make sure the lines are set to "Cutting". 

![Ordering through Ponoko](/readme_assets/Ponoko2.png)

Then, select your material. We want plain old clear acrylic. 

![Ordering through Ponoko](/readme_assets/Ponoko3.png)

Thenk select the thickness. **This is important.** Choose 2mm. 

![Ordering through Ponoko](/readme_assets/Ponoko4.png)
You can also choose how you want the parts delivered. I like to leave it on "As cut". That means you'll get a big sheet in the mail and you pop the pieces out yourself. You can also choose "Papered" if you want a smaller package. I would not choose "Naked". It is far more expensive and not ideal for our purposes. We want the acrylic protected by the paper until we're ready to install it to avoid unnecessary smudges and scratches. 
</details>

#### Ordering custom art
<details>
<summary>"Ordering custom art through FedEx Office"</summary>
The art plates are designed to be printed on an A4 sheet of paper, but this is fairly hard to find in the US, so printing on an 11"x17" sheet with more whitespace around the design is also an option.

You can use the same .svg to help lay out your design. Note that the back plate screw holes are offset purposely — don't change them. This is necessary for the art to print correctly. 

I just used FedEx Kinko's copy service. If ordering online, choose "Copies" and a thicker paper for durability. 60lbs or 80lbs are both fine. Also, make sure you choose 11x17.

![Ordering art](/readme_assets/FedEx.png)

If you upload your file and FedEx asks you to resize it, stop, something is wrong. You should upload a file that is exactly 11x17 and FedEx shouldn't have any feedback about it. Resizing art through FedEx's tool makes this far more complicated. 

You could also check if a local print shop would do the job, but their willingness to do this will vary. This is an extremely small job for most shops, so it may not be worth the time to set it up. 
</details>

### Soldering and assembly

Before you begin soldering, there are a few other supplies you'll need
- Soldering iron and solder
- Some small gauge wire. I like 28 or 30 AWG. 

By the time you're reading this, I may have made some minor changes to the design of the PCBs, but the idea behind this process will be the same. If there are any major changes, I will note them. 

The overall idea here is we will complete the individual PCBS, put them in place, then connect them together. 

#### Test the MCU
![Test the MCU](/readme_assets/test-mcu.jpeg)

<details>
<summary>"Testing the MCU"</summary>
Before you start anything else, it's a good idea to make sure your RP2040-Zero can flash the firmware. To do this, hold down the Boot button while plugging the board in. You should see it show up like a USB drive. Drag the firmware file into it and wait for it to disconnect. 

If you want to test the contacts of the MCU itself, you can bridge the ground pin to other contacts. You'll see buttons pressed on a tester like this: [https://hardwaretester.com/gamepad](https://hardwaretester.com/gamepad). You don't have to do this at this stage, though. As long as you can flash, things are probably on track.
</details>

#### OLED screen

![OLED screen](/readme_assets/screen-parts.jpeg)

<details>
<summary>"Prepping the OLED screen"</summary>
There's not much we need to do with the screen besides trimming the existing pins if they come pre-soldered. You can leave the underside pins if you want, but you much trim the top pins down so the screen will fit flush. 

![Screen pins trimmed](/readme_assets/screen-pins-flush.jpeg)

Also, note the order of the pins and tin them.
![Screen pins tinned](/readme_assets/screen-pins-tinned.jpeg) 
</details>

#### MCU mount PCB

![MCU mount parts](/readme_assets/mcu-parts.jpeg)

<details>
<summary>"Preparing the MCU (microcontroller) mount"</summary>
To mount the RP2040-Zero, we need to attach it to the mounting PCB first. This will also make connecting the boards together a little more straightforward. 

![Pins](/readme_assets/pins.jpeg)

There are a variety of ways you can mount the MCU. I recommend using a line of pins like this (it's okay if the line has too many pins — you can cut it to the right number), taping it to the back of the mount, and soldering the corners first so it stays in place. 

![Pins taped on](/readme_assets/pins-taped.jpeg)

It doesn't have to neat because we'll be trimming this in a moment. Finish soldering the line of pins. 

![MCU plate soldered](/readme_assets/mcu-plate-soldered.jpeg)

Then, work some snippers underneath the rubber sheathing and snip. Do this for all the pins so they are more or less flush (a little excess is okay.)

![Removing the sheathe from pins](/readme_assets/removing-pin-sheathe.jpeg)

![Trimming the pins](/readme_assets/trimming-pins.jpeg)

Once the MCU is soldered on, it's also a good time to tin the other contacts with little mounds of solder on each one. 

![MCU mount trimmed flush](/readme_assets/mcu-mount-flush.jpeg)
</details>

#### MX switch PCBs

![Preparing MX parts](/readme_assets/mx-parts.jpeg)

<details>
<summary>"Preparing MX switch PCBs"</summary>
The MX plates are very straightforward. We just need to solder the hotswap sockets and tin the contacts. 

To solder the hotswap sockets, just hold the socket down and add solder to one side. Continue holding it for a second while the solder hardens to make sure it's flush. 
 
![One half of MX switch soldered](/readme_assets/mx-half-soldered.jpeg)

Then solder the other side and tin the contacts. 

![MX switch mount soldered](/readme_assets/mx-full-soldered.jpeg)
</details>

#### Choc switch PCB

![Choc switch parts](/readme_assets/choc-parts.jpeg)

<details>
<summary>"Preparing the Choc switch PCB"</summary>
The Choc PCB is exactly the same as the MX ones. There are just more switches to solder. 

**Note the current Choc PCB is different from the one pictured. The process is still the same.**

Solder one side, then solder the other and repeat. Also, tin the contacts.

![Choc switches soldered](/readme_assets/choc-soldered.jpeg)

And tin the contacts above.
</details>

#### Installing the PCBs

![Parts for final assembly](/readme_assets/final-assembly-parts.jpeg)

<details>
<summary>"Installing the PCBs in the body"</summary>
The OLED screen and the MCU mount will be held in with M2 screws. The MX and Choc PCBs are secure enough just from clipping the switches into them, but the Choc PCB includes optional M2 screw holes as well. You won't see them in the images below, but they are included in the latest versions of the body and PCB. 

![Screws flush](/readme_assets/screws-flush.jpeg)

Screw in the OLED screen and MCU mount. The MCU screws are meant to sit flush in the body to be covered by the art. The OLED screw holes are a little tricky. Try to hold the nuts in place with tweezers and screw from the top. 

![All parts mounted](/readme_assets/parts-mounted.jpeg)

To install the switch mounts, clip the corner switches into the case first, then clip the PCBs onto the switches. When installing switches, **make sure to support the hotswap sockets from the back**. If you don't support the sockets, they may snap off. This is fixable, but it's annoying. 
</details>

#### Connecting them all together

![Preparing the wiring](/readme_assets/preparing-wires.jpeg)

<details>
<summary>"PCB wiring guide"</summary>
Once everything is in position, it's time to break out the wire. Everything is in order. 

| Hardware pin | Switch # | GP2040 Button | Xbox Button |
| ------------ | -------- | ------------- | ----------- |
| GP29         | -        | -             | -           |
| GP28         | -        | -             | -           |
| GP27         | -        | OLED SCL      | -           |
| GP26         | -        | OLED SDA      | -           |
| GP15         | 12       | L2            | LT          |
| GP14         | 11       | L1            | LB          |
| GP13         | 10       | R2            | RT          |
| GP12         | 09       | R1            | RB          |
| GP11         | 08       | B2            | B           |
| GP10         | 07       | B4            | Y           |
| GP09         | 06       | B1            | A           |
| GP08         | 05       | B3            | X           |
| GP07         | 04       | DPAD_Up       | Up          |
| GP06         | 03       | DPAD_Right    | Right       |
| GP05         | 02       | DPAD_Down     | Down        |
| GP04         | 01       | DPAD_Left     | Left        |
| GP03         | L_01     | L3            | LS          |
| GP02         | R_02     | R3            | RS          |
| GP01         | L_01     | S1            | Back        |
| GP00         | L_02     | S2            | Start       |

Simply heat up one contact, insert one end of the wire, and hold for a second. Then, repeat on the other side. 

![Wiring complete](/readme_assets/wiring-complete.jpeg)
</details>

### Adding custom art
Please see [Cutting a Circle for Arcade Buttons](/cutting_arcade_stick_art/readme.md).

![Artwork cut out](/readme_assets/gundam-art-cut.jpeg)

The manga panels used for one set of art panels are from Boku No Hero Academia by Kōhei Horikoshi.
The Gundam art used for the other set of art panels are from [Chris Bourassa](https://twitter.com/bourassaart?lang=en). 

I made these art files for my personal use and will not be distributing them. 

### Flashing the firmware
If you flashed the firmware for testing earlier, the controller should now be working. If not, flash it now. 

To change any of the settings or pin mappings, you can use the great GP2040-CE web configurator: [https://gp2040-ce.info/web-configurator/](https://gp2040-ce.info/web-configurator/)

### Final assembly
With everything working, all that's left to do is remove the paper from the acrylic plates, put the art down, put the plates down, and screw everything together. While you do this, try to be careful not to touch the underside of the acrylic (the side that will touch the art). That way, any smudges that develop will be on the top faces and easy to clean. 

![Two assembled EXPress controllers](/readme_assets/assembled.jpeg)

Enjoy your EXPress! 

---

If you found this guide helpful, tips are always appreciated but never required.

<a href="https://www.buymeacoffee.com/rookwork" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
