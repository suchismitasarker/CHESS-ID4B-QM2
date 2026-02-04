

# Practical guide of the temperature switch between nitrogen and helium

#### Consult beamline scientist before changing any temperatures


<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/sample-cryo1.png?raw=true){ width="500" }
</figure>


###  Manual Cryosystem 

Our standard cryosystem is broken. Below is the new cryosystem operations

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/new_cryo.png?raw=true){ width="800" }
</figure>



## Hutch Cryosystem 
###### The cryocooler is highly sensitive. To obtain an accurate temperature reading, please adhere to the following instructions. Note that the temperature change occurs gradually, so be patient! It requires time to reach the desired temperature.



<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/updated_temp.png?raw=true){ width="900" }
</figure>



### Temperature panels at beamline
<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/temp_panel.png?raw=true){ width="800" }
</figure>





<b><i><u> 300K ---> 280K : temperature range </b></u>

* Step 1 : Make sure nitrorgen (N2) valve is open and helium (He) valve is closed
* Step 2: <i> FOURC > `roomT`  (# set temperature to Input 1 : 220K and Input 3: 200K in screen 3)
* Step 3 : Make sure in the controller Channel A (Input 1) and Channel C (Input 3) will to reach the temperature <b>107K </b> and <b>196K </b> at screen 1.  It will be significantly lower if you are going from lower to higher temperature. 
* Step 4: <i> FOURC > `flow_set 6` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)
* Step 5 : FOURC > `te 300` </i>   (# set the sample temperature (Input 2) to 300K - green plot at screen 1)
* Step 6 : Wait until the sample reach the desired temperature before collecting the data


<b><i><u> 200K ---> 270 K : Temperature range </b></u>

* Step 1 : Make sure nitrorgen (N2) valve is open and helium (He) valve is closed
* Step 2: <i> FOURC > `prepN2_high`  (# set temperature to Input 1 : 165K and Input 3: 160K in screen 3)
* Step 3 : Make sure in the controller Channel A (Input 1) and Channel C (Input 3) will to reach the temperature <b>120K </b> and <b>160K </b>. The final temperature might be lower if you are going from lower to higher temperature
* Step 4: <i> FOURC > `flow_set 6` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)
* Step 5 : FOURC > `te 200` </i>    (# set the sample temperature (Input 2) to 200K- green plot at screen 1)
* Step 6 : Wait until the sample reach the desired temperature before collecting the data


<b><i><u> 160K ---> 200K : Temperature range </b></u>

* Step 1 : Make sure nitrorgen (N2) valve is open and helium (He) valve is closed
* Step 2: <i> FOURC > `prepN2_medium`  (# set temperature Input 1: 130K and Input 3: 110K in screen 3)
* Step 3 : Make sure in the controller Channel A (Input 1) and Channel C (Input 3) will to reach the temperature <b>101K </b> and <b>110K </b>.
* Step 4: <i> FOURC > `flow_set 9` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)
* Step 5 : FOURC > `te 160` </i>    (# set the sample temperature (Input 2) to 160K- green plotat screen 1)
* Step 6 : Wait until the sample reach the desired temperature before collecting the data

<b><i><u> 130K --> 150K : Temperature range </b></u>

* Step 1 : Make sure nitrorgen (N2) valve is open and helium (He) valve is closed
* Step 2: <i> FOURC > `prepN2_low`  (# set temperature Input 1: 87K and Input 3: 85K in screen 3)
* Step 3 : Make sure in the controller A (Input A) and C (input C) will to reach the temperature <b>87K </b> and <b>85K </b>.
* Step 4: <i> FOURC > `flow_set 12` ( # talk to Staff Scientist for the desired flow rate of your experimental setup)
* Step 5 : FOURC > `te 130` </i>   (# set the sample temperature (Input 2) to 130K - green plot at screen 1)
* Step 6 : Wait until the sample reach the desired temperature before collecting the data


!!! danger "Nitrogen to helium switch : Please use Helium sensibly!"
<b><i><u> 130K --> 15K : Cooling temperature of cryocooler with helium (He) </b></u> 

* Step 1: <i> FOURC > `prepswitch`  (# set temperature to Input 1 (A): 100K and Input 3 (C): 95K in screen 3; Input 1 (A) > 90, Input 1 (A) >85 are the good number to switch from N2 to helium)
* Step 2 : <i> FOURC > `te 240` </i> (# set the sample temperature (Input 2) to 240K - green plot at screen 1)
If the ice did not melt go to `te 260`
* Step 3 : <i> FOURC > `flow_set 10` </i>
* Step 4: <i> You need to wait until the temperature of the sample is 240K (it might be lower temperature)
* Step 5 : Turn on the Helium (He) valve  and close notrogen (N2) valve together, as soon as you do that run the next command

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

* Step 6 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 7 : <i> FOURC > `flow_set 10` </i> 
* Step 8 : Wait for base temperature Input 1 (A) ~8.4K Input 2 (C) ~44K to stabilize 


<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/2026%20temp%20partial.png?raw=true){ width="400" }
</figure>

* Step 9 : <i> FOURC > `te 15` </i>    (# To go to desired temperature (`te`) and change the `flow_set`look at the above plot)
* Step 10: <i> FOURC > `spin_xtal_phi` </i> (# rotate sample 360-->0 and 0-->360 degree in phi directions)
* Step 11: <i> FOURC > <b>control C </i> </b> ; you can STOP rotation; DONOT run control C twice, the program will crush


<b><i><u>  15K --> 130K: Heating temperature of cryocooler (change to He to N<sub>2</sub> flow)</b></u>


* Step 1 : <i> FOURC > `prepswitch` </i> (# it will setup the temperature setpoints 100K and 95K in the Lakeshore controller Input A 100K and input C 95K)
* Step 2 : <i> FOURC > `te 240` </i> (# it will setup the desired sample temperature; here sample temperature is 240 K)
* Step 3 : <b> Make sure all the temperatures (channel A, B, C) are above 80 K --->(Input 1 (A) >96 K, Input 2 (sample temperature)>200K and Input 3 (C) 85K in PLD controller) </b>
* Step 4 :<b> Send message to SLACK channel, please provide A, B, C channel temperature </b>

  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/Temp%2086-83%201.png?raw=true){ width="600" }
</figure>

!!! danger
    </i>N<sub>2</sub> in all conditions should be above 80K (N<sub>2</sub> (channel A, B, C) --> all temperature-->80K)
<figure markdown>
* Step 5 : <b> Once Input A, B and C are above 80K, then open the N2 valve and close He valve together </b>

  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/N2%20open2.png?raw=true){ width="600" }
</figure>

* Step 6 : <i> FOURC > `te 135` </i>   (# increase temperature to 135K or any other desired temperature)


<b><i><u>  300K --> 15K : Room Temperature to base (change N<sub>2</sub> to He flow)</b></u>

* Step 1 : <i> FOURC > `prepswitch` </i> (# it will setup the temperature in the Lakeshore controller channel A/Input 1 = 100K and channel C/Input 3 = 95K, A > 90, B >85 are the good number to switch from N2 to helium)
* Step 2 : <i> FOURC > Wait until the temperature of the channel A and C is stabilize to ~96K and ~87K
* Step 3 : <i> FOURC > `te 240` </i> (# set the sample temperature (Input 2) to 240K - green plot at screen 1)
* Step 4 : <i> FOURC > `flow_set 10` </i>
* Step 5: <i> You need to wait until the temperature of the sample is 240K (Make sure you do not have ice)
* Step 6 : Turn on the Helium (He) valve  and close nitrogen (N2) valve together, as soon as you do that run the next command

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

* Step 7 : <i> FOURC > `runninghelium` </i> (# it will setup the temperature in the Lakeshore controller)
* Step 8 : Wait for base temperature (Input A ~8.5K Input C ~30K) to stabilize (Input A ~8.5K Input C ~45K)
* Step 8 : <i> FOURC > `flow_set 15` </i> (flow_set 18 is only for 15K, if you want to go to high temperature slowly increase flowrate)
<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/2026%20temp%20partial.png?raw=true){ width="400" }
</figure>

* Step 9 : <i> FOURC > `te 15` </i>   (# make sure your `flow_set` is correct)
* Step 10: <i> FOURC > `spin_xtal_phi` </i> (# rotate sample 360-->0 and 0-->360 degree in phi directions)
* Step 11: <i> FOURC > <b>control C </i> </b> ; you can STOP rotation; DONOT run control C twice, the program will crush


<b><i><u> 15K --> 300K : Heating temperature of cryocooler  (change to He to N<sub>2</sub> flow)</b></u>


* Step 1 : <i> FOURC > `prepswitch` </i> (# it will setup the temperature in the Lakeshore controller channel A/Input 1 = 100K and channel C/Input 3 = 95K, A > 90, B >85 are the good number to switch from N2 to helium)
* Step 2 : <i> FOURC > `te 240` </i> (# set the sample temperature (Input 2) to 240K - green plot at screen 1)
* Step 3: <i> FOURC > `flow_set 10` </i> 
* Step 4 : <b> Make sure all the temperatures (channel A, B, C) are above 80 K --->(Input 1 (A) >96 K, Input 2 (sample temperature)>200K and Input 3 (C) 85K in PLD controller) </b>
* Step 5 :<b> Send message to SLACK channel once all the channels (A,B.C) are above 80K and before switching it to nitrogen from helium

!!! danger
    </i>N<sub>2</sub> in all conditions should be above 80K (N<sub>2</sub> (channel A, B, C) --> all temperature-->80K)
<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/N2%20open2.png?raw=true){ width="600" }
</figure>

* Step 6 : Turn on the N2 valve  and close He valve together
* Step 7 : <i> FOURC > `roomT` </i>   (# it will setup the temperature setpoints 222K and 220K in the Lakeshore controller Input A and input C and it will to reach the temperature 107K and 186K.)
* Step 8 : <i> FOURC > `te 300` </i>   (# increase temperature to 300K or any other desired temperature)



<b><i><u>  300K --> 500K : Performing experiment at high temperature </b></u>


* Step 1 : <b>Talk to beamline scientist, also send message to SLACK channel during temperature change  </b>
* Step 2 : Make sure N2 valve is open and He is closed
* Step 3 : FOURC > `highT` 
* Step 5: Make sure in the controller Input 1 (A): 300K and Input 2 (C): 300K, it will to reach that temperature and stabilize close to A 107K and C 196K.
* Step 6 : <i> FOURC > `flow_set 6`
* Step 7 : FOURC > `te 480` </i>   (#  temperature will go tho maximum 480K)


<b><i><u>  500K --> 300K : Performing experiment at high temperature </b></u>


* Step 1 : <b>Talk to beamline scientist, also send message to SLACK channel during temperature change  </b>
* Step 2 : Make sure N2 valve is open and He is closed
* Step 3 : FOURC > `roomT` 
* Step 5: Make sure in the controller Input A: 222K and B input C: 220K, it will to reach that temperature and stabilize close to A 105K and C 190K.
* Step 6 : <i> FOURC > `flow_set 6`
* Step 7 : FOURC > `te 300` </i>   





!!! danger
    Talk to beamline scientist before going high temperature

<b><i><u>  300K --> 500K : Performing experiment at high temperature when compressor need to turn off </b></u>


* Step 1 : <b>Talk to beamline scientist, also send message to SLACK channel during temperature change </b>
* Step 2 : Make sure N2 valve is open and He is closed
* Step 3 : Physically `Turn off` compressor (Go to the end of the hutch)

  * <b>Press `off` in the compressor (see the image below), send a message to the SLACK channel (this will help to track the compressor status and equipment condition)</b>

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/compressor.jpeg?raw=true){ width="300" }
</figure>

* Step 4 : <i> FOURC > `te 300`
* Step 5: <i> FOURC > `turn_off_compressor`  (# increase temperature to 1st and 2nd controller to 300K and 300K)
* Step 5: Make sure in the controller 1 (Input A: 300K and B input C: 300K), it will to reach that temperature and stabilize.
* Step 6 : <i> FOURC > `flow_set 6`
* Step 7 : FOURC > `te 480` </i>   (# increase temperature to 400K)

 <i> Note: Above 480K, it took long time to go 498K </i> 

<b><i><u>  500K --> 300K Performing experiment from high temperature to room temperature when compressor need to turn off</b></u>

* Step 1 : <b>Talk to beamline scientist, also send message to SLACK channel during temperature change </b>
* Step 1 : Make sure N2 valve is open and He is closed
* Step 2 : Physically `turn on` the compressor (Go to the end of the hutch)

  * <b>Press `on` in the compressor (see the image below), send a message to the SLACK channel (this will help to track the compressor status and equipment condition)</b>

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/compressor.jpeg?raw=true){ width="300" }
</figure>

* Step 3: <i> FOURC > `roomT`  (# increase temperature to 1st and 2nd controller to 130K and 110K)
* Step 3 : Make sure in the controller  Input A and Input C, it will to reach the temperature 101K and 110K.
* Step 4 : FOURC > `te 300` </i>   (# increase temperature to 300K)


<b><i><u> Turn off the temperature controller </b></i></u>

* Step 1 : Heat the temperature 300K, 300K, 300K
* Step 1 : Stop all the heaters manually in Lakeshore controller
* Step 2 : Turn off the compressor
* Step 3 : Wait until go to the required temperature
* Step 4 : Close the Nitrogen valve once A, B, C are 300K



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


#### Emergency proceduce if the temperature controller fails or Sudden power failure at beamline

!!! danger "Talk to Beamline Scientist or operators --- DONOT TRY THIS WITHOUT ASKING" 

* If the your setup is in nitrogen condition (300K - 80K) and suddenly temperature is dropiing drastically and you don't have controls 
  * Switch the valve Nitrogen to Helium 

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/He%20open%203.png?raw=true){ width="500" }
</figure>

  * Closed the compressor

  * Change the EPIC PVs range


