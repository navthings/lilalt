# lilalt journal

## nov 4 · ~5.5 hrs

schematic from this morning

![](journal/01.png)

added a status led on the spare pin. backwards

![](journal/02.png)

footprints. no idea what any of this is

![](journal/03.png)

typed into the wrong box

![](journal/04.png)

coin cell holder

![](journal/05.png)

3 headers that look identical. picked 1

![](journal/06.png)

picked the sideways switch by accident

![](journal/07.png)

header fixed. switch still wrong

![](journal/08.png)

led the right way round now

![](journal/09.png)

every part has a footprint

![](journal/10.png)

0 errors

![](journal/11.png)

added a 10u cap. typed 10n. 1000x too small

![](journal/12.png)

fixed

![](journal/13.png)

every part on top of each other

![](journal/14.png)

spread out. there is no auto place button

![](journal/15.png)

chip still in the corner

![](journal/16.png)

chip in the middle

![](journal/17.png)

tiny parts in the wrong spot

![](journal/18.png)

good enough

![](journal/19.png)

found edge.cuts

![](journal/20.png)

board outline. tight

![](journal/21.png)

buzzer hanging off the edge

![](journal/22.png)

fixed

![](journal/23.png)

menus are at the top of the screen on mac. took a while

![](journal/24.png)

ground pour. it was on the front, not the back

![](journal/25.png)

autorouted it with freerouting, asked claude to debug so it doesnt explode then moved c1/c2 next to the chip, mounting holes, pin labels, my n@ + made with <3. bom.csv all claude tho (if this is a issue tell me and ill redo bom.csv myself

## nov 6 · ~2.5 hrs

reviewer said the ch32v003 isnt on mouser or digikey, so i deleted everything and started over

attiny412 instead. same 8 pins, programs over 1 wire (updi)

![](journal/26.png)

sensor header + caps. swapped sda and scl

![](journal/27.png)

fixed that then wired sda into the programming pin

![](journal/28.png)

actually fixed

![](journal/29.png)

buzzer. 10k so it doesnt chirp while the chip boots, 1n4148 so the coil doesnt fry the transistor when it switches off

![](journal/30.png)

led

![](journal/31.png)

battery, switch, power flags. 0 errors

![](journal/32.png)

whole schematic

![](journal/33.png)

everything through hole except the chip so its easy to solder. picked a fan header for j2 by accident

![](journal/34.png)

parts dumped on the board

![](journal/35.png)

first layout. 42mm wide, wont fit in a rocket tube and the sensor would sit on the buzzer

![](journal/36.png)

30mm wide now. sensor plugs into j1 and hangs off the end so nothing hits it

![](journal/37.png)

routed. ground pour on both sides, 0 drc errors

![](journal/38.png)

![](journal/39.png)

bom.csv exported from kicad with digikey part numbers for everything

## nov 8 · ~0.5 hrs

reviewer said a cr2032 can only give ~3mA and the buzzer wants ~35mA. it would brown out the chip mid beep

swapped it for a passive piezo (tdk ps1240p02bt) wired straight across pa3 and pa7. the pins take turns so it gets a 6v swing off a 3v cell. no transistor, no diode, no base resistors

![](journal/40.png)

deleted q1 d1 r1 r2, piezo goes where the old buzzer was, rerouted by hand. pa3 sneaks under the sda pin to get across. 3v3 to the sensor used to run through the old diode so it got a new trace down the edge. drc clean

bom re-exported from kicad
