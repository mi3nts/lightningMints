## DFRobot_AS3935_Lib.py Library for Raspberry pi
---------------------------------------------------------
This is the sample code for Gravity:Lightning Sensor, SKU: SEN0292.
## Table of Contents

* [Installation](#installation)
* [Methods](#methods)
<snippet>
<content>

## Installation
The Lightning Sensor should work with AS3935
(https://github.com/DFRobot/DFRobot_AS3935/tree/master/RaspberryPi/Python) 

Run the program:

```cpp

$> python DFRobot_AS3935.py

```
## Methods

```C++

/*
 * @brief Init The Lightning Sensor
 *
 * @param address  I2C address(1~3)
 *        bus      I2C bus
 */
DFRobot_AS3935(address, bus);

/*
 * @brief Sensor reset
 */
def reset(self);

/*
 * @brief Configure sensor
 *
 * @param capacitance Antenna tuning capcitance (must be integer multiple of 8, 8 - 120 pf)
 *        location    Indoor/outdoor mode selection
 *        disturber   Enable/disable disturber detection
 */
def manualCal(self, capacitance, location, disturber);

/*
 * @brief Get mid-range type
 *
 * @return 0  Unknown src
 *         1  Lightning detected
 *         2  Disturber
 *         3  Noise level too high
 */
def getInterruptSrc(self);

/*
 * @brief get lightning distance
 * 
 * @return unit kilometer
 */
def getLightningDistKm(self);

/*
 * @brief get lightning energy intensity
 * 
 * @return lightning energy intensity(0-1000)
 */
def getStrikeEnergyRaw(self);

/*
 * @brief Sets LCO_FDIV register
 *
 * @param fdiv Set 0, 1, 2 or 3 for ratios of 16, 32, 64 and 128, respectively
 */
def setLcoFdiv(self,fdiv);

/*
 * @brief Set interrupt source
 *
 * @param irqSelect 0 = NONE, 1 = TRCO, 2 = SRCO, 3 = LCO
 */
def setIrqOutputSource(self, irqSelect);

/*
 * @brief Set to the outdoor model
 */
def setOutdoors(self);

/*
 * @brief Set to the indoor model
 */
def setIndoors(self);

/*
 * @brief Disturber detection enabled
 */
def disturberEn(self);

/*
 * @brief Disturber detection disenabled
 */
def disturberDis(self);

/*
 * @brief Set the noise level
 *
 * @param 0~7,More than 7 will use the default value:2
 */
def setNoiseFloorLv1(self, nfSel);

/*
 * @brief Get the noise level
 *
 * @return 0~7
 */
def getNoiseFloorLv1(self);

/*
 * @brief Set an anti-interference rating
 *
 * @param 0~7,More than 7 will use the default value:2
 */
def setWatchdogThreshold(self, wdth);

/*
 * @brief read WDTH
 *
 * @return 0~7
 */
def getWatchdogThreshold(self);

/*
 * @brief Modify SREJ (spike rejection)
 *
 * @param 0~7,More than 7 will use the default value:2
 */
def setSpikeRejection(self, srej);

/*
 * @brief read SREJ (spike rejection)
 *
 * @return 0~7
 */
def getSpikeRejection(self);

```
## Credits

Written by DFRobot_JH, 2018. (Welcome to our [website](https://www.dfrobot.com/))







