## Cryocoolers



<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-photos/blob/main/Crysocooler.png?raw=true)

</figure>

The cryocooler is manufactured by [CYRO Industries of America, Inc.](http://www.cryoindustries.com/).

<i> Close-circle cryostats are installed in &#60QM&#62<sup>2</sup> allowing samples to be comprehensively studied in a wide range of temperatures from 12K to 500K. The cryocooler can operate both helium (12K to 300K) and nitrogen gas (300K to 500K ) using a single stream flow. In-house nitrogen and helium gas are used for cryocoolers. Just by switching the knob outside of the hutch, the gas supply can be altered. 

The external tip-heater prevents frost and maintains a dry tip that helps to create an ice-free sample environment at low temperatures. A platinum temperature sensor is installed to control the low alarm setting temperature that triggers back the temperature controller to energize and maintain the ice-free environment. 

The main component of the cryostat can be divided into five different components: 
<br>

* (i) <b> source </b> : the refrigerator or the cryostat act as a source to cool a reliable cryogenic temperature for a long continuous periods
<br>

* (ii)<b> compressor </b>
<br>

* (iii) <b> PID temperature controller </b>: Cryogenic temperature controlled Model 336 manufactured by Lake Shore is used.  The controller’s zone tuning feature allows you to measure and control temperatures seamlessly from 300 mK to over 1,500 K by automatically switching temperature sensor inputs [1].
<br>

* (iv) <b> Power supply </b> : 30 V digital and 24V DC are used
<br> 

* (v) <b> Gas flow controller </b> : The digital flow automatically control and displays the flow rate

<b> Gas flow parameters </b>
<br>
<b> Helium gas</b>: Normal flow rate is between 8 – 12 liters/min, typically 11 l/min
</br>
<b> Nitrogen gas </b> : Normal flow rate is between 8 – 12 liters/min, typically 9 l/min.
</br>

<b> Safety </b>

* Do not touch the cold helium and nitrogen gas stream. Exposure to the skin of the cold gas could result in severe injuries.
* The dewar system has pressure relief protection installed. Do not remove pressure reliefs or check valves.

Motors

| Motor | Commands | Comments | 
| -------------- | :---------: | ---------- | 
| Temperature controller | sampleT | Set the temperature |  


### To open the lakeshore

* Open terminal
*  > `css` 
* The Lakeshore controller will open
* Output (1(input A): stage 1 heater, 2(input C): Sample temperature, 3 (input B): Stage 2 heater ), you can control.
* Change the  Range : Rang3/High  


## StripTool
* Open terminal
*  > `StripTool` 

!!! danger "Practical guide of the temperature switch between nitrogen and helium"

</i>
## N<sub>2</sub> and He switch at beamline (N<sub>2</sub> --> all temperature--> >77)


<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/sample-cryo1.png?raw=true){ width="500" }
</figure>


<b><i> Cooling temperature of cryocooler with N<sub>2</sub> : room temperature 300K --> >77K </b> 

* Step 1 : Open the N<sub>2</sub> valve and close He valve
* Step 2 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in hte Lakeshore controller)
* Step 3 : <i> FOURC > `te 170` </i>   (# lowering temperature to 170K)


<b><i> Cooling temperature of cryocooler with He : 77K --> 13K (change to N<sub>2</sub> to He flow)</b> 

* Step 1 : Please let CHESS operator know about changing the gas flow from N<sub>2</sub> to He
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : Turn on the He valve  and close N2 valve together
* Step 4 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 5 : Wait for base temperature to stabilize 

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20cooling.png?raw=true){ width="400" }
</figure>
* Step 6 : <i> FOURC > `te 13` </i>   (# lowering temperature to 13K or others)


!!! danger "Please use Helium sensibly!"

<b><i> Heating temperature of cryocooler : 13K --> 78K (change to He to N<sub>2</sub> flow)</b> 


* Step 1 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in hte Lakeshore controller)
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the temperature in hte Lakeshore controller)
* Step 2 : Make sure all the temperature is above 77 K (channel A, B and C in PLD controller)
* Step 3 : Open the N2 valve and close He valve together
* Step 4 : <i> FOURC > `te 100` </i>   (# increase temperature to 100K or any other desired temperature)



<b><i> Performing exoeriment above room temperature : 300K --> 500K </b> 

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prephighT`  (# increase temperature to 1st and 2nd controller to 143K and 220K)
* Step 3 : Make sure in the controller 1 (channel 1) and 2 (channel 3), it will to reach the temperature.
* Step 4 : FOURC > `te 400` </i>   (# increase temperature to 400K)


<b><i> Goging to room temperature </b> 

* Step 1 : Heat the temperature 300K, 300K, 300K
* Step 2 : close the compressor
* Step 3 : Wait until go to the required temperature
* Step 4 : Close the valve


