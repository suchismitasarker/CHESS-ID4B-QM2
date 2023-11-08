

# Practical guide of the temperature switch between nitrogen and helium

#### Consult beamline scientist before changing any temperatures


<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/sample-cryo1.png?raw=true){ width="500" }
</figure>


<b><i><u> Performing experiment at room temperature : 240K --> 300K </b></u>

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `roomT`  (# set temperature to 1st and 2nd controller to 130K and 110K)
* Step 3 : Make sure in the controller 1 (Input A) and B (input C), it will to reach the temperature 97K and 110K.
* Step 4: <i> FOURC > `flow_set 6` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)
* Step 5 : FOURC > `te 300` </i>   (# set the temperature to 300K)


<b><i><u> Cooling temperature of cryocooler with N<sub>2</sub> : room temperature 240K --> 95K </b> </u>

* Step 1 : Open the N<sub>2</sub> valve and close He valve
* Step 2 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 3 : <i> FOURC > `te 170` </i>   (# lowering temperature to 170K)
* Step 4: <i> FOURC > `flow_set 9` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)



!!! danger "Please use Helium sensibly!"
<b><i><u> Cooling temperature of cryocooler with He : 85K --> 13K (also if you want only room temperature 300K and 15K) (change to N<sub>2</sub> to He flow)</b></u> 

* Step 1 : <b> Please let CHESS operator know about changing the gas flow from N<sub>2</sub> to He </b>
* Step 2 : <i> FOURC > `te 230` </i> (# it will setup the temperature in the Lakeshore controller)
If the ice did not melt 
* Step 3 : <i> FOURC > `flow_set 9` </i>
* Step 4 : Turn on the He valve  and close N2 valve together

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

* Step 5 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 6 : Wait for base temperature (Input A ~5K Input C ~36K) to stabilize (look at the plot below)
* Step 7 : <i> FOURC > `te 14` </i>   (# lowering temperature to 14K or others)
* Step 8: <i> FOURC > `spin_xtal_scan` </i> (# rotate sample 360-->0 and 0-->360 degree in phi directions and you can STOP that by control C )

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/Temp%2036-4%201.png?raw=true){ width="700" }
</figure>


<b><i><u> Heating temperature of cryocooler : 13K --> 85K (change to He to N<sub>2</sub> flow)</b></u>


* Step 1 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature setpoints 87K and 83K in the Lakeshore controller Input A and input C)
* Step 2 : <i> FOURC > `te 180` </i> (# it will setup the desired sample temperature; here sample temperature is 180 K)
* Step 4 : Make sure all the temperature is above 77 K (Input A 87 K, Input B (sample temperature) and Input C 83K in PLD controller)

  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/Temp%2086-83%201.png?raw=true){ width="600" }
</figure>

!!! danger
    </i>N<sub>2</sub> in all conditions should be above 77K (N<sub>2</sub> (channel A, B, C) --> all temperature-->77K)
<figure markdown>
* Step 3 : Once Input A, B and C are above 77K, then open the N2 valve and close He valve together
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/N2%20open2.png?raw=true){ width="600" }
</figure>

* Step 4 : <i> FOURC > `te 100` </i>   (# increase temperature to 100K or any other desired temperature)


<b><i><u> Room Temperature to base : 300K --> 15K (change N<sub>2</sub> to He flow)</b></u>

* Step 1 : <b> Please let CHESS operator know about changing the gas flow from N<sub>2</sub> to He </b>
* Step 2 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature in the Lakeshore controller channel A = 85K and channel B = 83K)
* Step 2 : <i> FOURC > Wait until the temperature of the channel A and C is stabilize to 85K and 83K
* Step 3 : <i> FOURC > `te 230` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 4 : <i> FOURC > `flow_set 9` </i>
* Step 5 : Turn on the He valve  and close N2 valve together

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

* Step 6 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 7 : Wait for base temperature (Input A ~5K Input C ~41K) to stabilize (look at the plot below)
* Step 8 : <i> FOURC > `te 15` </i>   (# lowering temperature to 15K or others)
* Step 9: <i> FOURC > `spin_xtal_scan` </i> (# rotate sample 360-->0 and 0-->360 degree in phi directions and you can STOP that by control C )


<b><i><u> Heating temperature of cryocooler : 13K --> 300K (change to He to N<sub>2</sub> flow)</b></u>


* Step 1 : <i> FOURC > `prepnitrogen` </i> (# it will setup the temperature setpoints 85K and 83K in the Lakeshore controller Input A and input C)
* Step 2 : <i> FOURC > `te 220` </i> (# it will setup the desired sample temperature; here sample temperature is 220 K)
* Step 3 : Make sure all the temperature is above 77 K (Input A 87 K, Input B (sample temperature) and Input C 83K in PLD controller)
!!! danger
    </i>N<sub>2</sub> in all conditions should be above 77K (N<sub>2</sub> (channel A, B, C) --> all temperature-->77K)
<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/N2%20open2.png?raw=true){ width="600" }
</figure>

* Step 4 : <i> FOURC > `roomT` </i>   (# it will setup the temperature setpoints 130K and 110K in the Lakeshore controller Input A and input C and it will to reach the temperature 97K and 110K.)
* Step 5 : <i> FOURC > `flow_set 6` </i>   (# increase temperature to 100K or any other desired temperature)
* Step 6 : <i> FOURC > `te 300` </i>   (# increase temperature to 100K or any other desired temperature)



<b><i><u> Performing experiment above room temperature : 300K --> 500K </b></u>

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prephighT`  (# increase temperature to 1st and 2nd controller to 235K and 220K)
* Step 3 : <i> FOURC > `flow_set 6`
* Step 4 : Make sure in the controller 1 (Input A) and B (input C), it will to reach certain temperature and stabilize.
* Step 5 : FOURC > `te 400` </i>   (# increase temperature to 400K)


<b><i><u> Performing experiment from high temperature to room temperature : 500K --> 300K </b></u>

* Step 1 : Make sure N2 valve is open and He is closed
* Step 2: <i> FOURC > `prepnitrogen`  (# increase temperature to 1st and 2nd controller to 87K and 82K)
* Step 3 : Make sure in the controller  Input A and Input C, it will to reach the temperature 87K and 82K.
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
        
    * `FOURC> flow_set <number>`
    * `FOURC> flow_get `


# Problem : High temperature issues
* <i><b> a) Figure 3</b></i> : Check the gas flow and if needed talk to the staff scientist

# Problem : Accidentally closed the temperature controller

* <i><b> Step 1 </b></i> : Open terminal and type ` StripTool`
* <i><b> Step 2 </b></i> : Connect to epics PVs


* Need to connect to epics PVs that you want to monitor

      * LAKESHORE2:KRDG0
      * LAKESHORE2:KRDG1
      * LAKESHORE2:KRDG2

* y-axis click “Modify” button (same y axis for all the curves)
