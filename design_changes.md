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



* The enclosure design SHOULD be optimized to require as little CNC milling time as possible. When optimizing the design, user comfort is more important than robustness, but robustness is more important than aesthetics. Aesthetics are (for the most part) more important than cost or milling time. (If the design isn't comfortable, it's not worth using. After that, it's important that the keyboard be built to last and that it look nice. While cost is a factor, we're optimizing for quality and looks over cost.)

* The enclosure MUST be redesigned to anticipate drops and other stresses on the wood. The current screw cutouts on the inside of the wooden enclosure appear to have been a factor in a drop test failure. The wood flexed and it looks like a pan-head screw slammed into the wood as it flexed, contributing to the enclosure cracking. Possible solutions include thickening all the thinner parts of the side walls of the wood and changing the direction of the wood grain used. Another possible solution is extending the bottom plate of the keyboard to run 1/8" past the edge of the wood enclosure, acting as a bumper. We'd need to switch to a rounded edge on the metal bottom plate so it's not sharp. Right now the metal plate is entirely hidden by a wooden lip on the enclosure. Switching to a larger metal plate would also eliminate a relatively fine detail of the wood enclosure, which, we belive, is especially prone to chipping and cracking.

* The cutout for the USB connector MUST be thickened, It is currently the thinnest part of the keyboard wall and has been especially prone to cracking. 

* The USB connector SHOULD move to a position closer to the 'outside' of the left half of the keyboard. Right now, it comes out at a funny angle, which only works well with right-angle USB cables and is inconvenient from a cable management perspective.

* We SHOULD investigate how to improve the seating of the aluminum plate on the wooden enclosure. The brass screw bosses are somewhat prone to misalignment as the wood of the keyboard naturally changes shape due to airborne moisture content. Additionally, as the wood can deform slightly, it can make the aluminum plate slightly non-planar, which throws off the current attachment mechanism.

* We MUST reshape the key outline to mitigate a wood thickness issue: PgUp and - are the widest points of the key outline. They're also the narrowest points on the enclosure. 

* The key plate MUST be 1.1mm +/- 0.1 mm thick to properly anchor the keyswitches. Right now, the specs say the wrong thing.

* We MUST reshape the key outline to mitigate a wood thickness issue: The space between Esc/Butterfly and their respective thumb clusters are small, relatively fragile tongues of wood. We should grow the escape and butterfly keys to eliminate the tonuges and make it easier to hit those two keys with the thumbs. 

* We MAY resculpt the butterfly of the enclosure for aesthetic (and practical) purposes. The current design lacks a geometric symmetry that might be desirable. Also, a slight reshaping may help improve the physical strength of the material.

* We SHOULD resculpt the esc and butterfly keys to take advantage of the additional space available to them from the change to the outline above.

* We SHOULD relocate the centers of the esc and butterfly keys based on their new positions when they're resculpted as outlined above

* We SHOULD investigate moving the tab/ret keys, as well as rec/any to be more reachable as we make the changes to esc/butterfly above

* We MAY resculpt the outer corners of the Ctrl keys to remove the tongues of wood, as describe above for esc/butterfly

* We MUST compress the four-key thumb key arcs toward the centers of the arcs to make them easier for typists with limited ranges of thumb motion to strike them.

* We MUST move the palm keys out from the thumb arcs by approximately 2cm to more correctly position them underneath the fleshy parts of typists thumbs.

* We SHOULD make the placement angle of the palm keyswitch on the PCB exactly half way between the angles of cmd/del or alt/space.

* We SHOULD make the cutout for the palm key on the wooden enclosure back-to-front symmetrical so that users could reverse the sculpted keycap to change the placement of the 'bump' on the keycap to better fit their hand sizes

* We SHOULD investigate whether using wood that's slightly thicker (and raises the palms slightly higher relative to the keyswitches) will result in simpler milling due to it being a standard thickness) or whether it will result in increased user comfort.

* We MUST change the angle and position of the interconnect RJ12 jacks. They're very difficult to connect as currently located. 

* We MUST change to PCB-mount RJ12 jacks. The cost of hand-assembled friction-fit or panel-mount RJ12 jacks is just insanely high. We'll need to consider available orientations and the height of the jacks inside the enclosure. Right now, we use a sideways mounted jack. A correctly mounted jack may be taller (and may not be). Because of the stresses on the jacks, they MUST be through-hole mounted and include additional retaining clips.

* We SHOULD investigate whether we can use a more aggressive fillet on the edge of the enclosure. It'd feel nice under the palms for folks with larger hands (without requring more expensive 3D milling)

* We MUST replace the interhand connection mechanism. The current interhand connectors are hard to align with the keyboard. The current interhand connectors require very tight tolerances to fit snugly without fitting too snugly. Because the wood can sligntly warp the metal plates (and because the PEM hardware is seated on the plates, not integral with it), the connector bars are sometimes too tight and sometimes too loose. The replacement solution SHOULD be able to be aligned by the user without looking or flipping the keyboard upside down. The replacement solution should not easily slide apart when the keyboard is picked up with one hand by the user. The replacment solution SHOULD be designed to make it as easy as possible for a hobbyist to create replacement center bars at other tent angles or separation distances at home. The replacement solution SHOULD have some sort of locking mechanism, such as retaining pins + magnet or spring-mounted bearing. If we end up with a rail-based solution, something compatible with a standard T-Slot system SHOULD be used to enable hobbyists to do clever things (http://go.rockler.com/tech/RTD10000592AA.pdf is an example of something like this.) The slotted side of the rail would be built into the center-bar. The Sliding cross-section (what would be the T-bolt) would be the rail attached to the bottom of the enclosure. Kurt Mottweiler has suggested that if we keep the current key-hole design, we move to a ramped cutout inside the keyholes for a better fit and that we might consider a positioning-pin + neomagnet system as an alternative.  If we stick with a keyhole-based system, the keyholes for the two sides of the keyboard should be cut in opposite (back-to-front) directions so the user can push the two halves together to connect them or pull them apart. The current design requires pulling both halves of the keyboard relative to the keyplate, which is difficult to do.

* To the extent possible, the center-bars SHOULD NOT mar the underside of the keyboard. The current center-bars slide along a large area of the surface of the keyboard when attached and have a tendency to scrape the underside of the keyboard. If our design makes this unavoidable, we SHOULD consider the colors and finishes of the bottom plate of the keyboard and the center bars to minimize the visual impact.

* The center-bars we ship SHOULD have some sort of coating, edging or bumper so that they don't clatter when dropped. The current center bars make a very loud noise when they fall from a table or slip out of a user's hands.

* We MUST design feet for the keyboard.

* When the two halves of the keyboard are not connected by a center bar, the feet MUST allow the user to adjust the position and angle of each half of the keyboard independently.

* When the two halves of the keyboard are connected by a center bar, the feet MUST allow the user to keep the keyboard flat on the surface the keyboard is placed on or to tilt the keyboard at an XXXX degree negative tilt or a YYYY degree positive tilt. An ideal solution SHOULD let the user tilt the keyboard at a ZZZZ degree negative tilt or a WWWWW degree positive tilt. (ZZZZ and WWWW are numbers smaller than XXXX and YYYY, respectively.) An ideal solution MAY allow the user to tilt the keyboard at an arbitrary angle.

* When using the two halves of the keyboard without a center bar, the feet MUST allow the user to use the keyboard flat on the surface it is placed on or to tent one or both halves of the keyboard at a 15 degree angle relative to that surface. The feet SHOULD allow the user to tent either or both halves of the keyboard to 30 degrees relative to the surface the keyboard is placed on. An ideal solution MAY allow the user to tent one or both halves of the keyboard at an arbitrary angle. Going further than 30 degrees would be ideal, but given the choice between an additional tenting angle of 45 degrees and user-customizable tent angles, we'd rather let users pick their tenting angles.

* When using the feet in a supported configuration, the keyboard's center of gravity MUST be low enough that a typist resting their palms on it can't destabilize the keyboard.

* The feet MUST have a non-skid, non-marking coating on any surface where they might touch a surface the keyboard is placed on

* All specifications and parts for the keyboard MUST be metric. Nothing should be specified in inches, feet, pounds, or ounces. The Kickstarter prototypes used a mix of metric and imperial screws.

* We MUST use correctly sized cutouts for the Matias ALPS keyswitches. The Kickstarter design had slightly oversized holes, which led to switches being wobbly or flexing during keycap replacement

* We MAY switch the shape of the bottom plate to more exactly match the shape of the keyplate. This change has reprecussions for how we seat the feet on the enclsoure, how we mount the center bar on the enclosure and on how we mill out the enclosure. It also appears to be in direct contradiction to the possible design change which would make the bottom plate larger than the enclosure shape.

* We MAY want to switch to a steel bottom plate or a different thickness of aluminum bottom plate

* We MUST correct the design of the keystems to seat into Matias ALPS switches comfortably and securely without being so tight that we can crack keyswitches. The correct answer may be a nice gentle draft angle.

* We MUST increase the draft angle on the keycaps to add space between keytops. This should reduce typographical errors and make it easier for users to get acclimated to the keyboard.

* We MAY reshape the thumb keys, making them convex, rather than concave. This will make it more comfortable to strike the new, rnarrower thumb keys. Additionally, we MAY sculpt the thumb keys to make it comfortable to chord a pair of adjacent thumb keys.

* We MUST resculpt the swoop on 10qp to be no more severe than on other keys.


* We SHOULD increase the negative tilt on the  zxcvbm,./- row to remove the 'cliff' when pulling back fingers to hit them

* We MAY move 5tgb and 6yhn down approximately 4mm to make them easier to reach. As the typist's index fingers arc out from home row, those two columns are just slightly harder to reach than the home-row columns adjacent to them.

* We MAY move the pinkie columns up approximately 4mm to decrease the keyboard's learning curve. This has the downside of making 0 and 1 even harder to reach.

* We MAY decrease the back-to-front keyspacing by 1-2mm to make the number-key row significantly easier to reach. 

* We SHOULD switch to IO Expanders with key scanning engines that support both down-stroke and up-stroke events. The ISSI product we're investigating looks like it should fit the bill. The new IO Expander SHOULD operate on a 5V voltage supply.

* We SHOULD switch from RS2812B LEDs to APA102C LEDs. They're easier to drive and look nicer.

* We MAY switch from MicroUSB connectors on the keyboard to new USB-C connectors. (Current issues include cost, sourcing and what, if any, electrical changes would be required)

* If we don't switch to USB-C connectors, we SHOULD switch to MicroUSB connectors with through-hole electrical connections, in addition to the through-hole mechanical connections of the current design. (The only issue is that we're unsure they exist)

* We MUST combine the keyswitches and LEDs for each hand onto a single PCB.

* We SHOULD the microcontroller and support circuitry to the underside of the PCB. Because of the plate that fixes the keyswitches in position on top of the PCB, it's very difficult to access or repair any of the electronics on the Kickstarter model. Downside: this could result in the support circuitry being exposed to damage if the keyboard is disassembled and could increase the height of the PCB stackup by 1-2mm. 

* We SHOULD place the LEDs off-center from the centers of the keyswitches. Right now, the LED shines into the middle of the spring/slider core, dimming the LEDs considerably.

* We SHOULD optimize our PCB geometry for mass production.

* We SHOULD devise a new scheme for PCB-to-keyplate mounting. The current scheme using PEM standoffs and screws can damage PCBs if screws overtightened. Retaining clips may be an option. A bent-metal key plate that acts as its own standoff and assembly locating system is another.


* We SHOULD upgrade the fuse on the USB connection to allow power draw of maybe 2 amps of power. The LEDs can draw a bunch more, but there's a limit to what's sane.


* We MUST rewrite our software and firmware from scratch. No, seriously The existing firmware was all proof of concept.
