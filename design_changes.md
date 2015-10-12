This is an incomplete list of what we're considering for Model 01 design changes, as well as the current status of those changes.

Tasks are specific engineering actions to take. They have action verbs
Tasks make design changes happen.

Design Changes describe intended outcomes. Every design change will use a key word as described below:

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
RFC 2119.



# Mechanical

## Enclosure 






- [ ] We MUST replace the interhand connection mechanism. The current interhand connectors are hard to align with the keyboard. The current interhand connectors require very tight tolerances to fit snugly without fitting too snugly. Because the wood can sligntly warp the metal plates (and because the PEM hardware is seated on the plates, not integral with it), the connector bars are sometimes too tight and sometimes too loose. The replacement solution SHOULD be able to be aligned by the user without looking or flipping the keyboard upside down. The replacement solution should not easily slide apart when the keyboard is picked up with one hand by the user. The replacment solution SHOULD be designed to make it as easy as possible for a hobbyist to create replacement center bars at other tent angles or separation distances at home. The replacement solution SHOULD have some sort of locking mechanism, such as retaining pins + magnet or spring-mounted bearing. If we end up with a rail-based solution, something compatible with a standard T-Slot system SHOULD be used to enable hobbyists to do clever things (http://go.rockler.com/tech/RTD10000592AA.pdf is an example of something like this.) The slotted side of the rail would be built into the center-bar. The Sliding cross-section (what would be the T-bolt) would be the rail attached to the bottom of the enclosure. Kurt Mottweiler has suggested that if we keep the current key-hole design, we move to a ramped cutout inside the keyholes for a better fit and that we might consider a positioning-pin + neomagnet system as an alternative.  If we stick with a keyhole-based system, the keyholes for the two sides of the keyboard should be cut in opposite (back-to-front) directions so the user can push the two halves together to connect them or pull them apart. The current design requires pulling both halves of the keyboard relative to the keyplate, which is difficult to do.

- [ ] To the extent possible, the center-bars SHOULD NOT mar the underside of the keyboard. The current center-bars slide along a large area of the surface of the keyboard when attached and have a tendency to scrape the underside of the keyboard. If our design makes this unavoidable, we SHOULD consider the colors and finishes of the bottom plate of the keyboard and the center bars to minimize the visual impact.

- [ ] The center-bars we ship SHOULD have some sort of coating, edging or bumper so that they don't clatter when dropped. The current center bars make a very loud noise when they fall from a table or slip out of a user's hands.



- [ ] We MAY switch the shape of the bottom plate to more exactly match the shape of the keyplate. This change has reprecussions for how we seat the feet on the enclsoure, how we mount the center bar on the enclosure and on how we mill out the enclosure. It also appears to be in direct contradiction to the possible design change which would make the bottom plate larger than the enclosure shape.

- [ ] We MAY want to switch to a steel bottom plate or a different thickness of aluminum bottom plate



# Internal mechanical

- [ ] We SHOULD devise a new scheme for PCB-to-keyplate mounting. The current scheme using PEM standoffs and screws can damage PCBs if screws overtightened. Retaining clips may be an option. A bent-metal key plate that acts as its own standoff and assembly locating system is another.

- [ ] We MUST use correctly sized cutouts for the Matias ALPS keyswitches. The Kickstarter design had slightly oversized holes, which led to switches being wobbly or flexing during keycap replacement

- [ ] The key plate MUST be 1.1mm +/- 0.1 mm thick to properly anchor the keyswitches. Right now, the specs say the wrong thing.

# Electronics changes


## Electrical Design

- [ ] We SHOULD upgrade the fuse on the USB connection to allow power draw of maybe 2 amps of power. The LEDs can draw a bunch more, but there's a limit to what's sane.

- [ ] We MUST switch to a new IO Expander with a key matrix scanning engine, since the SX1509 used in the Kickstarter prototypes doesn't support key-up events.

- [ ] The new IO Expander SHOULD operate on a 5V voltage supply.

~~* We SHOULD switch to ISSI 31IO7326 IO Expanders with key scanning engines that support both down-stroke and up-stroke events.~~

- [ ] We SHOULD switch from RS2812B LEDs to APA102C LEDs. They're easier to drive and look nicer. (Issue: using a PCB-mount LED means that if a fault is detected after keyswitches are soldered on, rework is incredibly difficult.)

- [ ] We SHOULD switch from MicroUSB connectors on the keyboard to new USB-C connectors. (Current issues include cost, sourcing and what, if any, electrical changes would be required)

- [ ] We MUST combine the keyswitches and LEDs for each hand onto a single PCB.

- [ ] We MUST remove the 3v support circuitry on the boards once we no longer need it

- [ ] We SHOULD add a hardware interlock to give the boards a "can't be flashed over USB" mode for our more security-conscious users.

- [ ] We MUST reevaluate the USB support circuitry (right now U1 prevents the ATMega from dropping the USB connection to flip from application code to bootloader or vice-versa. On the prototype run, we had to cut pin 1.)

- [ ] We SHOULD look at what we might do to make the board more robust in the face of hobbyists doing dumb things.

- [ ] We SHOULD swap out 0402 components for larger components to make test and repair easier

- [ ] We MUST have sufficient interconnect wires to control both LEDs and key matrix.
    * TODO: see if we can drive the APA102C LEDs with the i2c clock 

## PCB Layout

- [ ] The USB connector SHOULD move to a position closer to the 'outside' of the left half of the keyboard. Right now, it comes out at a funny angle, which only works well with right-angle USB cables and is inconvenient from a cable management perspective.

- [ ] We SHOULD add test points and pins for hobbyists to have their way with the boards. This includes adding headers (populated or not) for the Arduino pins.

- [ ] We MUST change the angle and position of the interconnect (currently RJ12) jacks. They're very difficult to connect as currently located. 
    * TODO: specify angle and position of the jacks once new enclosure shape is decided

- [ ] We MAY have to switch from RJ12 to RJ45 if we need a 7th pin.

- [ ] We MUST change to PCB-mount interconnect jacks. The cost of hand-assembled friction-fit or panel-mount jacks is just insanely high. We'll need to consider available orientations and the height of the jacks inside the enclosure. Right now, we use a sideways mounted jack. A correctly mounted jack may be taller (and may not be). Because of the stresses on the jacks, they MUST include additional retaining clips.

- [ ] We MUST move the palm key switches out from the thumb arcs by approximately 2cm to more correctly position them underneath the fleshy parts of typists thumbs. 

- [ ] We SHOULD make the placement angle of the palm keyswitch on the PCB exactly half way between the angles of cmd/del or alt/space.

- [ ] We SHOULD the microcontroller and support circuitry to the underside of the PCB. Because of the plate that fixes the keyswitches in position on top of the PCB, it's very difficult to access or repair any of the electronics on the Kickstarter model. Downside: this could result in the support circuitry being exposed to damage if the keyboard is disassembled and could increase the height of the PCB stackup by 1-2mm. 

- [ ] We SHOULD place the LEDs off-center from the centers of the keyswitches. Right now, the LED shines into the middle of the spring/slider core, dimming the LEDs considerably.

- [ ] We SHOULD optimize our PCB geometry for mass production.

# Enclosure changes

- [ ] We MUST reshape the keycap outline to mitigate a wood thickness issue: PgUp and - are the widest points of the key outline. They're also the narrowest points on the enclosure. 

- [ ] We MUST reshape the key outline to mitigate a wood thickness issue: The space between Esc/Butterfly and their respective thumb clusters are small, relatively fragile tongues of wood. We should grow the escape and butterfly keys to eliminate the tonuges and make it easier to hit those two keys with the thumbs.  Will impact keycap outline.

- [ ] We MUST alter the cutouts on the inside of the enclosure to have much more rounded angles. the sharp right angles and small cutouts significantly increase milling time and cost.

- [ ] We SHOULD increase the enclosure thickness around the edges by 2mm - this was requested by a CNC vendor. We SHOULD do this by shrinking the size of the bottom plate and the enclosure cutout, rather than by increasing the size of the enclosure

- [ ] We MAY resculpt the butterfly of the enclosure for aesthetic (and practical) purposes. The current design lacks a geometric symmetry that might be desirable. Also, a slight reshaping may help improve the physical strength of the material. May impact keycap outline.




- [ ] We SHOULD make the cutout for the palm key on the wooden enclosure back-to-front symmetrical so that users could reverse the sculpted keycap to change the placement of the 'bump' on the keycap to better fit their hand sizes (keycaps)


- [ ] We SHOULD investigate whether we can use a more aggressive fillet on the edge of the enclosure. It'd feel nice under the palms for folks with larger hands (without requring more expensive 3D milling)

- [ ] We SHOULD investigate whether using wood that's slightly thicker (and raises the palms slightly higher relative to the keyswitches) will result in simpler milling due to it being a standard thickness) or whether it will result in increased user comfort.

- [ ] The enclosure design SHOULD be optimized to require as little CNC milling time as possible. When optimizing the design, user comfort is more important than robustness, but robustness is more important than aesthetics. Aesthetics are (for the most part) more important than cost or milling time. (If the design isn't comfortable, it's not worth using. After that, it's important that the keyboard be built to last and that it look nice. While cost is a factor, we're optimizing for quality and looks over cost.)

- [ ] The enclosure MUST be redesigned to anticipate drops and other stresses on the wood. The current screw cutouts on the inside of the wooden enclosure appear to have been a factor in a drop test failure. The wood flexed and it looks like a pan-head screw slammed into the wood as it flexed, contributing to the enclosure cracking. Possible solutions include thickening all the thinner parts of the side walls of the wood and changing the direction of the wood grain used. Another possible solution is extending the bottom plate of the keyboard to run 1/8" past the edge of the wood enclosure, acting as a bumper. We'd need to switch to a rounded edge on the metal bottom plate so it's not sharp. Right now the metal plate is entirely hidden by a wooden lip on the enclosure. Switching to a larger metal plate would also eliminate a relatively fine detail of the wood enclosure, which, we belive, is especially prone to chipping and cracking.

- [ ] The cutout for the USB connector MUST be thickened, It is currently the thinnest part of the keyboard wall and has been especially prone to cracking. 

- [ ] We SHOULD investigate how to improve the seating of the aluminum plate on the wooden enclosure. The brass screw bosses are somewhat prone to misalignment as the wood of the keyboard naturally changes shape due to airborne moisture content. Additionally, as the wood can deform slightly, it can make the aluminum plate slightly non-planar, which throws off the current attachment mechanism.


- [ ] We SHOULD modify the cutout on the underside of the enclosure to ease milling. This means replacing right angle cuts on the interior with large radius curves and reducing fine detail on the interior where possible. 


# Software changes

- [ ] We MUST rewrite our software and firmware from scratch. No, seriously The existing firmware was all proof of concept.

# Adjustability changes

- [ ] We MUST design feet for the keyboard.

- [ ] When the two halves of the keyboard are not connected by a center bar, the feet MUST allow the user to adjust the position and angle of each half of the keyboard independently.

- [ ] When the two halves of the keyboard are connected by a center bar, the feet MUST allow the user to keep the keyboard flat on the surface the keyboard is placed on or to tilt the keyboard at an XXXX degree negative tilt or a YYYY degree positive tilt. An ideal solution SHOULD let the user tilt the keyboard at a ZZZZ degree negative tilt or a WWWWW degree positive tilt. (ZZZZ and WWWW are numbers smaller than XXXX and YYYY, respectively.) An ideal solution MAY allow the user to tilt the keyboard at an arbitrary angle.

- [ ] When using the two halves of the keyboard without a center bar, the feet MUST allow the user to use the keyboard flat on the surface it is placed on or to tent one or both halves of the keyboard at a 15 degree angle relative to that surface. The feet SHOULD allow the user to tent either or both halves of the keyboard to 30 degrees relative to the surface the keyboard is placed on. An ideal solution MAY allow the user to tent one or both halves of the keyboard at an arbitrary angle. Going further than 30 degrees would be ideal, but given the choice between an additional tenting angle of 45 degrees and user-customizable tent angles, we'd rather let users pick their tenting angles.

- [ ] When using the feet in a supported configuration, the keyboard's center of gravity MUST be low enough that a typist resting their palms on it can't destabilize the keyboard.

- [ ] The feet MUST have a non-skid, non-marking coating on any surface where they might touch a surface the keyboard is placed on

- [ ] Users SHOULD be able to place the keyboard on top of a macbook's keyboard and use it.

- [ ] All specifications and parts for the keyboard MUST be metric. Nothing should be specified in inches, feet, pounds, or ounces. The Kickstarter prototypes used a mix of metric and imperial screws.

# Keycap changes

- [ ] We MUST correct the design of the keystems to seat into Matias ALPS switches comfortably and securely without being so tight that we can crack keyswitches. The correct answer may be a nice gentle draft angle. (keycaps)

- [ ] We MUST increase the draft angle on the keycaps to add space between keytops. This should reduce typographical errors and make it easier for users to get acclimated to the keyboard. (keycaps)

- [ ] We MAY reshape the thumb keycaps, making them convex, rather than concave. This will make it more comfortable to strike the new, rnarrower thumb keys. 

- [ ] Additionally, we MAY sculpt the thumb keycaps to make it comfortable to chord a pair of adjacent thumb keys.

- [ ] We MUST resculpt the swoop on 10qp to be no more severe than on other keys. (keycaps)


- [ ] We SHOULD increase the negative tilt on the  zxcvbm,./- row to remove the 'cliff' when pulling back fingers to hit them (keycaps)

- [ ] We MAY move 5tgb and 6yhn down approximately 4mm to make them easier to reach. As the typist's index fingers arc out from home row, those two columns are just slightly harder to reach than the home-row columns adjacent to them. (keycaps)

- [ ] We MAY move the pinkie columns up approximately 4mm to decrease the keyboard's learning curve. This has the downside of making 0 and 1 even harder to reach. (impacts keycaps, key switch placement)

- [ ] We MAY decrease the back-to-front keyspacing by 1-2mm to make the number-key row significantly easier to reach. (impacts keycaps, key switch placement)

- [ ] We MAY resculpt the outer corners of the Ctrl keycaps to remove the tongues of wood, as describe above for esc/butterfly

- [ ] We MUST compress the four-key thumb keycap arcs toward the centers of the arcs to make them easier for typists with limited ranges of thumb motion to strike them.

- [ ] We SHOULD resculpt the esc and butterfly keycaps to take advantage of the additional space available to them from the change to the outline above.

- [ ] We SHOULD relocate the centers of the esc and butterfly key switches and keycaps based on their new positions when they're resculpted as outlined above

- [ ] We SHOULD investigate moving the tab/ret key switches and keycaps, as well as rec/any to be more reachable as we make the changes to esc/butterfly above

- [ ] We MAY relocate the keys currently labeled for pgdn and - to outside the keys currently labeled pgup and ' 
