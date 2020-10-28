# NodemcuWakeUpAlarm
Wake up alarm system made with Nodemcu


/* Get 3 values from user through webserver.  Alarm Hour. Alarm Minute. Alarm counter
 * when alarm hour and minute match, 3 relays turn on (i am using for heaters.)
 * caunter value = minutes, wait time for speaker turn on. 
 * For example i want to wake up 07.00, the heater relays turn on 6.30 and speaker turn on 7.00  - alarm hour=06,alarm minute=30,counter=30
 * Normally system power from 220vac-5vdc power supply. if electricity goes, internal 18650 batteries meet the energy of the system. and when electricity goes, heater or when you used relays for doesnt work but spekaer work.
 * these 3 values storage at eeprom. Because after the set alarm, nodemcu energy can goes, restart by 18650 battery.
 * Real time values taken by ntp server and saved eeprom too. 
 * if router wifi goes,system read last real time values from eeprom and calculate to alarm time by itself.
 * if electricty goes, and came again. nodemcu ip change. for this reason used to static ip for nodemcu.
 * if you use your mobile phone hotspot, you dont need to get static ip. if you restart to phone, nodemcu ip doenst change.  
 * i use 2 different wifis. local router wifi and mobile phone . i select these with button. this button selected before turn on power.
 * in loop, nodemcu sleep 1 min and wake up with pin16 to rst pin. and check alarm,and sleep again. (i used 55 sec. not 1min. 5 secends for system recovery)
 * in loop, check to connection (pnig pong-google) if connection is available. read ntp or calculate by nodemcu.
 * This project made by mixed 4 or 5 differents examples from github.
 * save to ip when used mobile phone hotspot. it will never change. if you want a mobile app you need these. 
 */
