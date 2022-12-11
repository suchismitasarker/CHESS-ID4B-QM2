

# Practical guide of the temperature switch between nitrogen and helium


!!! danger
          </i>N<sub>2</sub> in all conditions should be above 77K (N<sub>2</sub> --> all temperature-->77K)



<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/sample-cryo1.png?raw=true){ width="500" }
</figure>


<b><i> Cooling temperature of cryocooler with N<sub>2</sub> : room temperature 300K --> 95K </b> 

* Step 1 : Open the N<sub>2</sub> valve and close He valve
* Step 2 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : <i> FOURC > `te 170` </i>   (# lowering temperature to 170K)



<b><i> Cooling temperature of cryocooler with He : 77K --> 13K (change to N<sub>2</sub> to He flow)</b> 

* Step 1 : Please let CHESS operator know about changing the gas flow from N<sub>2</sub> to He
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : Turn on the He valve  and close N2 valve together
* Step 4 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 5 : Wait for base temperature (channel A ~5K channel B ~36K) to stabilize 
* Step 6 : <i> FOURC > `te 13` </i>   (# lowering temperature to 13K or others)

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20cooling.png?raw=true){ width="400" }
</figure>



!!! danger "Please use Helium sensibly!"

<b><i> Heating temperature of cryocooler : 13K --> 78K (change to He to N<sub>2</sub> flow)</b> 


* Step 1 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature setpoints 83K and 86K in the Lakeshore controller channel A and channel B)
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the desired sample temperature; here sample temperature is 180 K)
* Step 2 : Make sure all the temperature is above 77 K (channel A 83 K, B (sample temperature) and C 86K in PLD controller)
* Step 3 : Open the N2 valve and close He valve together
* Step 4 : <i> FOURC > `te 100` </i>   (# increase temperature to 100K or any other desired temperature)



<b><i> Performing exoeriment above room temperature : 300K --> 500K </b> 

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prephighT`  (# increase temperature to 1st and 2nd controller to 143K and 220K)
* Step 3 : Make sure in the controller 1 (channel 1) and 2 (channel 3), it will to reach the temperature 143K and 220K.
* Step 4 : FOURC > `te 400` </i>   (# increase temperature to 400K)


<b><i> Goging to room temperature </b> 

* Step 1 : Heat the temperature 300K, 300K, 300K
* Step 2 : close the compressor
* Step 3 : Wait until go to the required temperature
* Step 4 : Close the valve



