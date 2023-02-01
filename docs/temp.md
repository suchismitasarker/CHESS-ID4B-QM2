

# Practical guide of the temperature switch between nitrogen and helium

#### Consult beamline scientist before changing any temperatures


<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/sample-cryo1.png?raw=true){ width="500" }
</figure>


<b><i><u> Cooling temperature of cryocooler with N<sub>2</sub> : room temperature 300K --> 95K </b> </u>

* Step 1 : Open the N<sub>2</sub> valve and close He valve
* Step 2 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : <i> FOURC > `te 170` </i>   (# lowering temperature to 170K)


!!! danger "Please use Helium sensibly!"
<b><i><u> Cooling temperature of cryocooler with He : 77K --> 13K (change to N<sub>2</sub> to He flow)</b></u> 

* Step 1 : Please let CHESS operator know about changing the gas flow from N<sub>2</sub> to He
* Step 2 : <i> FOURC > `te 220` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : Turn on the He valve  and close N2 valve together

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

* Step 4 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 5 : Wait for base temperature (Input A ~5K Input C ~36K) to stabilize (look at the plot below)
* Step 6 : <i> FOURC > `te 13` </i>   (# lowering temperature to 13K or others)

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/Temp%2036-4%201.png?raw=true){ width="700" }
</figure>


<b><i><u> Heating temperature of cryocooler : 13K --> 78K (change to He to N<sub>2</sub> flow)</b></u>


* Step 1 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature setpoints 87K and 83K in the Lakeshore controller Input A and input C)
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the desired sample temperature; here sample temperature is 180 K)
* Step 2 : Make sure all the temperature is above 77 K (Input A 87 K, Input B (sample temperature) and Input C 83K in PLD controller)

  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/Temp%2086-83%201.png?raw=true){ width="600" }
</figure>

!!! danger
    </i>N<sub>2</sub> in all conditions should be above 77K (N<sub>2</sub> (channel A, B, C) --> all temperature-->77K)
<figure markdown>
* Step 3 : Once Input A, B and C are above 77K, then open the N2 valve and close He valve together
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/N2%20open2.png?raw=true){ width="600" }
</figure>

* Step 4 : <i> FOURC > `te 100` </i>   (# increase temperature to 100K or any other desired temperature)



<b><i><u> Performing experiment above room temperature : 300K --> 500K </b></u>

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prephighT`  (# increase temperature to 1st and 2nd controller to 143K and 220K)
* Step 3 : Make sure in the controller 1 (Input A) and B (input C), it will to reach the temperature 143K and 220K.
* Step 4 : FOURC > `te 400` </i>   (# increase temperature to 400K)


<b><i><u> Performing experiment above room temperature : 500K --> 300K </b></u>

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prepnitrogen`  (# increase temperature to 1st and 2nd controller to 143K and 220K)
* Step 3 : Make sure in the controller  Input A and Input C, it will to reach the temperature 143K and 220K.
* Step 4 : FOURC > `te 300` </i>   (# increase temperature to 300K)


<b><i><u> Turn off the temperature controller </b></i></u>

* Step 1 : Heat the temperature 300K, 300K, 300K
* Step 2 : close the compressor
* Step 3 : Wait until go to the required temperature
* Step 4 : Close the valve



# Problem : Ice formation at low temperature

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/icing_issue.png?raw=true){ width="600" }
</figure>
 
* <i><b> a) Figure 1</b></i> : Check the distance between the cryo-stream and sample (it should be as close as possible)
* <i><b> b) Figure 2</b></i> : Continuously rotate the phi `umv phi 360; umv phi 0` at low temperature
* <i><b> c) Figure 3</b></i> : Check the gas flow and if needed talk to the staff scientist


# Problem : High temperature issues
* <i><b> a) Figure 3</b></i> : Check the gas flow and if needed talk to the staff scientist

# Problem : Accidentally closed the temperature controller

* <i><b> Step 1 </b></i> : Open terminal and type ` StripTool`
* <i><b> Step 2 </b></i> : Connect to epics PVs

