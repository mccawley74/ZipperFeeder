Non-Commercial license You are free to: Share --- copy and redistribute
the material in any medium or format freely. Adapt --- remix, transform,
and build upon the material for any purpose, except commercially.

Attribution Heavily modified from: \"MiniFeeder\" By GK-3D
https://www.thingiverse.com/thing:4361894

BACKGROUND
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
I made this feeder as I have a Pico Reef Tank (Two Gallon) with one
fish, my Gobi. Looking around for a small feeder was not successful,
most all were the size of my tanks lid blocked the light and held too
much food.

Since I had all these parts, I made the smallest feeder I could.

And if you are wondering why it is called Zipper Feeder, it is because I
have a Striped Goby that I named Zipper. You will see this name in the
OLED menu as well. I did make it so the name is a variable in code:
String fish_name = \"ZIPPER\"; Line 92 I believe, in
\"zipper_feeder.ino\"

Pros
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
 1. Small, very small 2. Simi programmable feed schedule with OLED
screen 3. Nano feed rate. Good for 1-3 small fish 4. DIY abd fun to
build, unless you have sausage fingers :( 5. Customizable if you do any
3D modeling and/or Arduino development.

Cons
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
 1. Does NOT have an RTC clock. I.e. no time keeping, uses time since
boot to track schedule. 2. Only programmable to feed every six hours, or
every three hours. With option to skip nights. 3. The amount of food it
dispenses is based on the Auger size. I included two: a.
auger_larger.stl Has larger spacing, allowing more food per rotation. b.
auger_smaller.stl Has smaller spacing, allowing less food per rotation.

You can print each individually or both with file \"auger_both.stl\" and
test each.

4. Hard to assemble due to small size. 5. Manual alignment of the Auger.
Only needs done once. Could be added to code (Have a go!) 6. Some manual
modifications needed. I.e OLED mounting, button location and hole, screw
choice.

7. No screw standard. I used what I had, what fit. The front cover is
pass-through (Nut bolt) The rear cover and motor cover/motor mounting is
self threading screws.

8. NOT battery powered, needs USB 5v

NO: It does not overheat in such a small space. It really doesn\'t do
anything until it feeds. The motor is external of the main chassis, runs
only every 3 hours minimum, etc\... There is however a vented front
cover \"front_cover_vented.stl\" if you are paranoid.

PARTS USED (BOM, kinda):
==============================================================================

Item Description Cost
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
Control Board: \| Arduino Pro Micro 5v \| \$6.50 Ea. Motor: \| 28BYJ-48
Stepper Motor \| \$2.50 Motor CTRL: \| ULN2003 Driver Board \| \$2.50
Button: \| Micro Momentary Tactile Push Button \| \$0.05 Wire: \| 30AWG
8-Color Tinned Copper Solid Cable \| \$0.10 Display: \| 0.91\" I2C OLED
Display SSD1306 128x32 3.3V/5V \| \$4.00 Housing: \| Overture PLA \|
\$1.00

\~ \$16.65

Per part prices are based off of Amazon and include the breakdown cost
used, I.e: - OLED screen comes as a two for \$8.00 - A spool of wire is
\$9.00 - The motor and motor control board come as a pair for \$5.00

If you search Amazon/AliExpress with the search term being the above
Description you should easily find the part(s)

Yes, you can buy a decent feeder for around \$20.00, but if you already
have some parts and you want a super tiny feeder, and love to make
stuff. Keep reading.

If you want the best automatic feeder I\'ve found to date, look at the
Petbank Store \"Automatic Fish Feeder\" It\'s is a round carousel style
USB re-chargeable feeder with LCD that lasts for weeks. Not affiliated,
just have two now for my larger tanks and they work great.

ASSEMBLY: Sorta, Don\'t hate me after this part.
==============================================================================
You will need thin wire to allow for the reduced space. I use 30AWG wire
in most all my Arduino projects. Specifically \"8-Color Electronic
Wire - 30 AWG Single Core, 250M Tinned Copper Solid Cable for Circuit
Boards & PCB\" You can find it on Amazon. Just search for the above
mentioned.

There is no schematic for this project. All connections are detailed in
the header comments of the Arduino code:
/Code/zipper_feeder/zipper_feeder.ino

The assembly takes the most time and patience. I did some tweaking of
the files after I assembled mine to make things a bit easier.

Things to note. There are two motor controller boards you will find on
Amazon/AliExpress, etc the first is a square type the other is a smaller
rectangle shape. (See motor-control-boards_x.png)

While the square type had better motor control when it came to the
smoothness of the movement at low speeds, the rectangle shaped board was
a lot easier to fit in the chassis. The Chassis was designed for the
square board so either will work. Your choice.

Both of these boards can be found with a motor on Amazon/AliExpress with
a motor. The motor will be: 28BYJ-48 Geared Stepper Motor DC 5V The
board will be one of: ULN2003 Driver Board, or L293D Motor Drive Module
DC4.5-25V

For either of the two motor control boards you choose, you will need to
cut down the connection header pins, or de-solder altogether. (I
de-soldered for best clearance)

Assembly Steps:
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 1.
Lay the printed chassis on your workplace.

2\. Place the motor, Arduino, and OLED display on the left of the
chassis.

3\. Place the motor module to the right of the chassis.

4\. Lay out your wire from the Arduino to the Motor Control board so as
there is enough to pass through the chassis and reach the control board.

5\. Cut the motor wires down so that there is just enough length to also
reach the control board but still leave the motor with a good inch
clearance from the chassis. See image: motor-mounting.png You will want
enough slack, once the motor board in installed to pull the motor off
the auger. See Image: assembly-2.png for a cutaway chassis diagram.

6\. Set the chassis aside and lay out the parts in the order shown in
image: wire-two.png Solder the motor wires to the control board, the
control board to the Arduino. The OLED to the Arduino (Leave wire slack)
etc\... The images should help.

7\. Glue the main chassis to the Auger tube (CA Glue) Place the main
chassis on a flat surface and apply glue to the top of the chassis,
while holding the auger tube, place onto the top of the chassis and hold
in place until dry. The auger tube rear flange should butt up against
the rear main chassis. See: \"tube_alignment.png\"

You can temporarily mount the motor cover to the auger tube as the
bottom of the motor cover will lay flat against the work surface along
with the main chassis, this will allow the tube and chassis to remain
properly aligned with one another while the glue dries.

8\. Mount the OLED, after the OLED in in place use CA Glue to align and
affix the screen bezel.

9\. Align and mount your button. Use glue to hold in place. NOTE: You
will notice that the chassis STL does not have a button hole. The first
model I Made did not have any menu or programmability and thus no
button. I added it later and as such I simply drilled a hole and glued a
small Tactile switch I had in place. Feel free to use any button you may
have, put where you want (Fits) Or even use two buttons and update the
code. There are plenty of free GPIO ports to work with. I am sure the
code can be improved upon.

10\. Insert the Arduino into the chassis. slide in and then to the rear,
making sure the USB port properly slides into the USB hole in the
chassis. Use a bit of PLA, toothpick, etc. to wedge the Arduino in
place. see image: board-mounting.png

11\. Slide the motor control board into the chassis and install the
front cover.

12\. Install the rear cover, making sure that the motor wires pass
through the slot in the cover.

13\. Slide the Auger into the chassis tube and press into the motor,
aligning the slot in the auger to that of the motor. If too tight heat
the motor shaft so it more readily slides into the PLA Or ensure that
the Auger and motor shaft fit ahead of time.

14\. Slide the motor_cover.stl over the motor and install screws to
secure the motor cover, and motor to the chassis. Again see images in
the images folder for help.

15\. Use CA Glue to affix the hopper and Auger tube cap.

16\. Connect to your computer and flash with the included code.

NOTE: The auger tube cap keeps the auger from accidentally coming off
the motor shaft and sliding out the end of the tube. While it does make
removing the Auger a bit more difficult as it can only exit the rear of
the housing after removing the motor cover, and motor, it does keep the
Auger in place.

NOTES: If you use the smaller rectangle shaped motor control board it
will slide in from the same side of chassis as the Arduino (Left) At a
slight tilted angle.

As of now, there is no recess, or specific mount for the OLED. It will
just fit into the opening. from the inside of the chassis. Once you have
it in place, use CA Glue, hot glue, or a PLA pen to hold in place
permanently. (Or edit the STL files)

Be patient. I wasn\'t sure at first if all the parts would fit, and
fought for a while before coming up with the method shown in the images.
I did manage to fit the larger square control board before re-designing
the chassis and using a smaller board as de-soldering that many pins was
tedious and I figured anyone making one of these would hate me just a
little less.

If you leave the Arduino an inch outside the chassis (left), and the
motor control board 1 inch outside the chassis (right), and measure out
the wire length, and use half that length for the OLED, it will all
stuff in the chassis nicely.

It\'s all easy to put in but becomes a bit fiddly once the OLED is glued
in place as the Arduino board, and motor have only an inch or so of
play.

MENU SYSTEM
==============================================================================
 1. Press the button once to enter the menu system. 2. Each press of the
button will move to the next menu setting. 3. Hold the button down for
one second to select that menu item

NOTE: If you reach the end of the menu it will round robin back to the
start.

Each menu setting is listed below as it appears on the screen.

Id Grouping Item
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 1.
Menu \| Options Load Food 2. Menu \| Feed Feed Now 3. Menu \| Feed Every
6 Hours 4. Menu \| Feed Every 3 Hours 5. Menu \| Feed Feed at night 6.
Menu \| Time Reset Timer 7. Menu \| Options Empty Feeder 8. Menu \|
Options Exit Menu

For any given menu item above, hold the button down for one second to
select that menu item. There is no sub-menu and after selecting a menu
item the menu will exit.

A description of menu item selection is given below.

1\. Load Food: This will aid in loading food into the feeder. Fill the
hopper and select this menu item. The auger in the feeder will rotate to
draw food to the end of the feeder, preparing for feeding.

2\. Feed Now: Dispenses food

3\. Every 6 Hours: When set the feeder will run a feed rotation every 6
hours or 4 times in a 24 hour period. See \"Feed at night\" to only feed
during day hours.

4\. Every 3 Hours: When set the feeder will run a feed rotation every 3
hours or 8 times in a 24 hour period. See \"Feed at night\" to only feed
during day hours.

5\. Feed at night: Skips the last 2, or last 4 feed rotations allowing
only daytime feeding. True = Food will dispense during nighttime feed
rotations. False = Food will only dispense during daytime feed
rotations.

6\. Reset Timer: This is used to start the timer for feeding. Whatever
time it is when this is selected will be the start of the timer.

7\. Empty Feeder: Runs the auger for 8 revolutions to help empty food
left in the feeder. You should first empty the hopper, then select this
option to assist with emptying the feeder of remaining food.

8\. Exit Menu: Exits the menu and returns to the running display.

Example feeding schedule. There is no clock in the Arduino Pro Micro, so
time is calculated in milliseconds since the board was booted, or since
the \"Reset Timer\" is selected.

Plug in the feeder at 9:00am, or select \"Reset Timer\" from menu at
9:00am to start the time rotation. You can start the feeder at any time
you want, 9:00 is used as an example.

Interval Feed at night
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 6 Hour
\| False

Food rotations will be 9:00am , 3:00pm

Interval Feed at night
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 3 Hour
\| False

Food rotations will be: 9:00am , 12:00pm , 3:00pm , 6:00pm

Interval Feed at night
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- 3 Hour
\| True

Food rotations will be: 9:00am , 12:00pm , 3:00pm , 6:00pm , 9:00pm ,
12:00am, 3:00am , 6:00am

NOTE: The feeder will not feed when first booted, or \"Reset Timer\" is
selected from menu. To initiate the first feeding, select \"Feed Now\"
from the menu. Subsequent feedings will occur at designated hour
intervals (6 hour or 3 hour)

Lastly: Do not print the files from /3MF Files/Assembled_Feeder.3mf The
individual .stl files are the most up to date. Use the
Assembled_Feeder.3mf for reference only whilst assembling the feeder.

Thank you, now go soak your poor fingers in some Palmolive soap and
relax.

\# EOF
