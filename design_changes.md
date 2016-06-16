This is an incomplete list of what we're considering for Model 01 design changes, as well as the current status of those changes.

Tasks are specific engineering actions to take. They have action verbs
Tasks make design changes happen.

Design Changes describe intended outcomes. Every design change will use a key word as described below:

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
RFC 2119.



# Mechanical

## Specification and design

- [ ] All specifications and parts for the keyboard MUST be metric. Nothing should be specified in inches, feet, pounds, or ounces. The Kickstarter prototypes used a mix of metric and imperial screws.

## Bottom plate


## Keyplate

- [ ] We SHOULD devise a new scheme for PCB-to-keyplate mounting. The current scheme using PEM standoffs and screws can damage PCBs if screws overtightened. Retaining clips may be an option. A bent-metal key plate that acts as its own standoff and assembly locating system is another.

# Enclosure changes

- [ ] The enclosure MUST be redesigned to anticipate drops and other stresses on the wood. The current screw cutouts on the inside of the wooden enclosure appear to have been a factor in a drop test failure. The wood flexed and it looks like a pan-head screw slammed into the wood as it flexed, contributing to the enclosure cracking. Possible solutions include thickening all the thinner parts of the side walls of the wood and changing the direction of the wood grain used. Another possible solution is extending the bottom plate of the keyboard to run 1/8" past the edge of the wood enclosure, acting as a bumper. We'd need to switch to a rounded edge on the metal bottom plate so it's not sharp. Right now the metal plate is entirely hidden by a wooden lip on the enclosure. Switching to a larger metal plate would also eliminate a relatively fine detail of the wood enclosure, which, we belive, is especially prone to chipping and cracking.


- [ ] Bottom plate screw mountings should allow a looser tolerance when aligning wooden enclosure to bottom plate



## Feet

- [ ] We MUST design feet for the keyboard.

- [ ] When the two halves of the keyboard are not connected by a center bar, the feet MUST allow the user to adjust the position and angle of each half of the keyboard independently.

- [ ] When the two halves of the keyboard are connected by a center bar, the feet MUST allow the user to keep the keyboard flat on the surface the keyboard is placed on or to tilt the keyboard at an XXXX degree negative tilt or a YYYY degree positive tilt. An ideal solution SHOULD let the user tilt the keyboard at a ZZZZ degree negative tilt or a WWWWW degree positive tilt. (ZZZZ and WWWW are numbers smaller than XXXX and YYYY, respectively.) An ideal solution MAY allow the user to tilt the keyboard at an arbitrary angle.

- [ ] When using the two halves of the keyboard without a center bar, the feet MUST allow the user to use the keyboard flat on the surface it is placed on or to tent one or both halves of the keyboard at a 15 degree angle relative to that surface. The feet SHOULD allow the user to tent either or both halves of the keyboard to 30 degrees relative to the surface the keyboard is placed on. An ideal solution MAY allow the user to tent one or both halves of the keyboard at an arbitrary angle. Going further than 30 degrees would be ideal, but given the choice between an additional tenting angle of 45 degrees and user-customizable tent angles, we'd rather let users pick their tenting angles.

- [ ] When using the feet in a supported configuration, the keyboard's center of gravity MUST be low enough that a typist resting their palms on it can't destabilize the keyboard.

- [ ] The feet MUST have a non-skid, non-marking coating on any surface where they might touch a surface the keyboard is placed on



## Interconnect mechanism

- [ ] The replacement solution SHOULD be able to be aligned by the user without looking or flipping the keyboard upside down. 
- [ ] The replacement solution should not easily slide apart when the keyboard is picked up with one hand by the user.
- [ ] The replacment solution SHOULD be designed to make it as easy as possible for a hobbyist to create replacement center bars at other tent angles or separation distances at home. 
- [ ] The replacement solution SHOULD have some sort of locking mechanism, such as retaining pins + magnet or spring-mounted bearing. 
    
- [ ] The center-bars we ship SHOULD have some sort of coating, edging or bumper so that they don't clatter when dropped. The current center bars make a very loud noise when they fall from a table or slip out of a user's hands.

# Keycap changes

# Electronics changes

## Electrical Design

## PCB Layout

- [ ] We SHOULD optimize our PCB geometry for mass production.

# Software changes

- [ ] We MUST rewrite our software and firmware from scratch. No, seriously The existing firmware was all proof of concept.

