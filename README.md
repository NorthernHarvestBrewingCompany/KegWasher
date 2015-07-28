# KegWasher
Keg Washer Code That Controls The 8 Step Keg Washing Process 
This code is meant to be run on a Microcontroler or Microcomputer with General Purpose I/O ports that will interact with physical sensors, valves, and relays. 

The purpose of this code is to provide a fully automated Keg Washing system for use in a commercial brewery.
The Process of washing a commercial beer keg 

Keg Cleaning Articles: 
http://www.probrewer.com/library/archives/quality-control-for-keg-cleaning/
http://www.brewingnews.com/thriftygadgeteer/thriftykwinstructions.pdf

Cleaners:
Acid Cleaner #6 (Good for CO2 Envronments) --> http://www.fivestarchemicals.com/wp-content/uploads/Acid6Tech1.pdf
PBW --> http://www.fivestarchemicals.com/wp-content/uploads/PBWTech.pdf

Sanitizers:
Star-Xene --> http://www.fivestarchemicals.com/wp-content/uploads/StarXeneProductSheet.pdf
IO-Star (Lower Foam) --> http://www.fivestarchemicals.com/wp-content/uploads/IOStarTech2.pdf
Star-San (Foamy) --> http://www.fivestarchemicals.com/wp-content/uploads/StarSanTech5.pdf

High Level Controller View
1. Rinse the Keg with High Pressure HOT Water
2. Spray the Keg with an acid solution for 60 seconds
3. Rinse the Keg with High Pressure warm Water
4. Spray the Keg with an acid solution for 60 seconds
5. Rinse the Keg with High Pressure warm Water
6. Spray the Keg with sanitizer for 120 Seconds
7. Purge the air from the keg and fill with CO2
8. Wash Complete, Sound Buzzer, Flash Light 


Assuming the use of Acid Wash #6
---------------------------------------------------------------------------------
Keg Cleaning: Set automatic keg washer to a 2 minute wash cycle. The
temperature setting should be set between 120-160°F. 
Make up a solution of Acid # 6 at a rate of 1-2 oz. per gallon of water.
Pre rinse kegs with warm water to remove excessive beer.

Sanitize kegs with Star Xene at a rate of 25 to 40 ppms.
In a clean 1 gallon jug add 7 pints of water. 1 oz. of Citric Acid and 1 pint of STARXENE.
This will provide a stock solution of 6,250 ppms. Set injector to 100 ppm final sanitizing rinse


A More Detailed View
1. Depressurize any residual CO2 in the keg through the gas side drain
2. Rinse residual beer out of the keg with hot water.
3. Spray the interior of the keg with a solution of HOT Water and cleaning agent (PBW or similar)
4. Rinse the remaining cleaner out with HOT water removing any debris with it
3. Again Spray the interior of the keg with a solution of HOT Water and cleaning agent (PBW or similar)
4. Again Rinse the remaining cleaner out with HOT water removing any debris with it
5. Sanitize the keg useing a commercal brewery sanitizer solution, this can be room temprature
6. Close drain valve, and purge remaining air in the keg by pressurising with CO2, and opeing drain valve twice
7. Sound Buzzer which indecates keg is done and the next keg(s) can be added. 
 

----------------------------------------------------------------------------------------------------------------
Codeing Standards

Variables should use descriptive names like Valve1 and Heater1
Variables should start with capital letters

Brackets should always be on their own line, for example;

void myfunction(bool &istrue)
{
  int secondfunction(int IsANum)
  {
    IsANum = 1;
  }
  istrue = TRUE;
}

