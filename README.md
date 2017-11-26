# 12V_battery_arduino_charger
12V battery charger based on an arduino with LCD panel and keypad

Please enter your type of battery and Ah-rating: 
For lead-acid (FLA/VRLA) batteries, type 1
For nickel-iron (NiFe) batteries, type 2
For nickel-metal hydride (NiMH) batteries, type 3

Ah rating:

---Code---
Information tables for program:

Type      Number of cells   DoD       DoC         Charge C-rate   Charge voltage		
FLA/VRLA  6			            30% SOC   95% SOC     0,25C           2,35-2,45V per cell
NiFe      10                15% SOC   95% SOC     0,14C           1,7v per cell
NiMH      10                20% SOC   95% SOC     0,5C            1,4-1,6v per cell

Peak/off peak hours table:
between 00 hours to 06 hours: off-peak hours
between 06 hours to 22 hours: peak hours
between 22 hours to 00 hours: off-peak hours

Program calculations:
Entered battery type charge voltage X number of cells = ? volts to supply to battery
Entered battery type charge C-rate X entered Ah-rating for battery = ? amps to supply to battery

Start charging:
When DoD SOC level of battery type selected has been reached AND off-peak hours are in effect.

Stop charging:
When DoC SOC level of battery type selected has been reached

Notes:
DOD means depth of discharge, so how much the battery is allowed to be discharged
DOC means depth of charge, so how much the battery is allowed to be charged
SOC means State of Charge, or hence the capacity rated in percent.
The charge C-rate is the maximum continuous rate (not peak rate !) at which the battery can be charged.
1C hereby means that the battery can be charged at 100% of the Ah-rate of the battery.
1C also means that the battery would be recharged in 1 hour. 
Maximum discharge C-rate is not needed for the charger, so was dropped.
12V FLA or VRLA batteries contain 6 cells with a nominal voltage of 2 volt = 12V
12V NiFe batteries contain 10 cells with a nominal voltage of 1,2 volt.
12V NiMH batteries contain 10 cells with a nominal voltage of 1,2 volt.
Temperature is also very important for charging; if the battery becomes too hot damage could occur and efficiency of the charging drops. Also, with some battery types (such as NiMh), there's a risk of fire. As such, the charging c-rate for the NiMh batteries has been set lower (0,5C) than what it is actually capable of accepting (1C)
The arduino needs to be connected to a 3x3 matrix keypad and a 32x2 LCD panel
Only 3 types of batteries that are known to have long shelf lives and/or good recycling charisteristics were taken into the recharger code.

References:
http://batteryuniversity.com/learn/article/charging_the_lead_acid_battery
https://www.electrical4u.com/nickel-iron-batteries-or-edison-batteries/
http://www.sciencedirect.com/science/article/pii/S2214993714000037
http://batteryuniversity.com/learn/article/charging_nickel_metal_hydride
http://www.electro-tech-online.com/attachments/mhcharge-gif.20501/
