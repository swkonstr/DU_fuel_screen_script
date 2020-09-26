# DU_fuel_screen_script

WIP

Never run out of gas again! Dual Universe script to display your ship's fuel tank capacity. 

Credit to thespartacus29 (https://github.com/thespartacus29). This is pretty much his exact code for his Ore Monitor (https://github.com/thespartacus29/DualUniverse-OreMonitor) with only a few tweeks. 

This is an instruction with script on how to set up a screen to display your fuel tank's capacity. The script in it's current form will support 2 medium Atmospheric tanks and 2 medium Space tanks. However, you can edit it to as many tanks as you want or differant sizes. We'll go over that later after install. 

Items needed
* 2 Atmospheric Fuel tanks Medium
* 2 Space Fuel tanks Medium
* 1 Manual Switch
* 1 Programing Board
* 1 Screen XS 

Instructions
1. Place your items
2. Links Tanks to Programing Board. Do one link at a time so you can name appopriatly. To name them, look at your programing board and press ctrl+L to enter the Lua editing screen. Names are below, they are case sensative. 
      * AtomFuel1
      * AtmoFuel2
      * SpaceFuel1
      * SpaceFuel2
3. Link Switch to Programing Board. Name below, it is case sensative
      * switch
4. Link Programing Board to screen. Name below, it is case sensative
      * screen
5. Enter the lua editing and create 3 filters under "Unit". Those 3 filters are in the repository. "Live" is case sensative when you create the tick filter. 
      * tick(Live)
      * start()
      * stop()
6. Copy/paste the code from each repository file into each filter. 
7. Apply the changes. You are done. 



You can stop reading now but if you want to be able to edit the script to fit your fuel setup, keep on reading. Insructions for editing are below. 

There are 3 sections of the main script tick(Live)

      * Section 1 are lines 1-19
      * Section 2 are lines 20-63
      * Section 3 are lines 64-120

We only neeed to edit section 2 if you change the size of the tank. If you change the amount of tanks, you'll need to edit sections 2 and 3. 

Section 2 is broken down further with each fuel tank. I will use AtmoFuel1 as an example. Line 21 is where you set the fuel tank size. The variable to edit is 
>"maxAtmoFuel1 = 1600"

* Small is 400
* Medium is 1600 
* Large is 12800

If all you needed to do was change the size, then you're done editing. If you wanted to add a 3rd atmospheric tank, you would just copy and paste lines 20-29. Every variable with *"AtmoFuel1"* would need to be changed to something like *"AtmoFuel3"*. Example is below. 
   >massAtmoFuel1 = round(math.ceil(AtmoFuel1.getItemsMass()/weightAtmoFuel1),1)

to

   >massAtmoFuel3 = round(math.ceil(AtmoFuel3.getItemsMass()/weightAtmoFuel3),1)
   
   
You would repeat this for every variable in that pasted section
      
Secction 3 need similar edits. You would copy and paste one of the tank sections, the first one would be lines 88-93. You would change every variable with *"AtmoFuel1"* to *"AtmoFuel3*". An example line is below. 
> <th>]]..massAtmoFuel1..unitMeasure..[[</th>

to

> <th>]]..massAtmoFuel3..unitMeasure..[[</th>


      WIP
