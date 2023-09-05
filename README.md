# Ethanol
The homebrewers & home distillers assistant, an Ethanol maker. A small device with external modules to measure, record, and display the rate of fermentation in a bubble airlock, control fermentation temperature, and control the output of a Still.

This project serves two purposes: a Fermentation assistant, and a still controller for regulating the output of a Still.

## The project consists of the following physical components:
1.	The “Core” unit – the central module that accessories are plugged into. Handles measurement, control, and datalogging.
2.	The bubble detector – an external module responsible for detecting bubbles passing through the clear plastic of the fermentation airlock.
3.	The Mains control unit – an external module that plugs inline with a main’s electrically powered heating element to control heating to either a fermenter or a Still. 

## Core unit overview:
The core unit consists of an RP2040 and peripheral signal conditioning/interfacing electronics to allow several sources of data to be collected. The core unit measures the fermentation rate of an active fermenter through the bubble detector external module, controls heat to a fermentation pad/band and regulates the operation of a still using the mains control module. The core unit also gathers temperature information using a K-type thermocouple and an optional DS18B20 temperature sensor. 
Information about fermentation measurements are displayed on a small OLED screen, the user interacts with the core unit using pushbuttons. Data from the fermentation/distillation process can be saved to a microSD card.
 
## Fermentation Process Background & Application:
When making homebrew alcohol a liquid containing yeast available sugar and yeast is placed in a sanitized food safe container. The yeast consume the sugar and produce ethanol ("alcohol") and CO2, this is the "fermentation" process. The excess CO2 gas produced is allowed to escape the fermentation vessel using something that doesn’t allow (non-sanitized) air to flow back into the fermentation vessel. Often this is accomplished with an ‘airlock’; water placed in an S bend tube, like a smaller scale of the water trap in a sink.
This bubble airlock allows the rate of fermentation to be monitored by casually observing approximately how many bubbles per time-period pass through the air lock.
The first external module to the core unit is a bubble detector, this consists of an Infra-Red photo interrupter that sits either side of the bottom of the S-bend in the fermentation airlock. It sends logic pulses to the core unit each time it detects a bubble. The core unit then records the number of bubbles per unit time to track the fermentation rate.

The second external module is the mains control unit. This module controls mains power to an optional fermenter heater pad/band. The mains power is switched on with a simple logic high signal at 3.3V. 

## Distillation Process Background & Project Application
Distillation is the process of taking the product of the fermentation process and heating it until the ethanol evaporates from the liquid, condensing, and capturing the vapour. Changing the rate at which product comes out of the still changes various qualities of the product. The rate of production (mL/min) from the still is directly proportional to the temperature of the vapour just prior to entering the condenser.
For this reason, it can be useful to control the power supplied to stills heating system in relation to the temperature of the vapour entering the condenser.

This is achieved using the mains control module, just like the fermenter heater control discussed above.
