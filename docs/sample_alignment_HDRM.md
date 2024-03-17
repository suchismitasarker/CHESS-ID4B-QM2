# Welcome to CHESS &#60QM&#62<sup>2</sup> Sample Alignment


![Image title](https://github.com/suchismitasarker/CHESS-photos/blob/main/beamline.jpeg?raw=true){ width="300" }

!!! danger "High Dynamic Range Reciprocal Space Mapping (HDRM)"


#### Basic Theory - HDRM

High Dynamic Range Mapping (HDRM) is primarily a method for studying single crystal samples, although it can also be effective for studying thin films. HDRM aims is to rapidly study wide regions of reciprocal space, collecting the intense Bragg peaks required to refine crystal structures along with weak features associated with superstructures, and the slowly modulated scattering associated with phonons and short-range order[[1](https://www.chess.cornell.edu/srn-article-cartography-7-dimensions-chess)].

!!! hint "Single Crytal Alignment"
      Basic steps for single crystal sample alignment - HDRM

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/goniometer1.png?raw=true){ width="150" }
</figure>


######  <i>Step 1:  Center the sample to the beam </i>

            FOURC> umvr samz 0.1 (relative motion of the sample movement up (+) and down (-)) 
            FOURC> umv phi 0
            FOURC> umv phi 180
            Move x and y to make the sample to the cursor
            FOURC> umv phi 90
            FOURC> umv phi 270
            Do it iteratively until the center of the axis match the sample position     

######  <i>Step 2 :  Create file structure </i>

      a) Create newfile 

            FOURC>newfile <samplename> 
            # samplename : chemical name of your sample, make sure you created folder in your directory


      b) Open HDRMscans.mac script and sort your path (sortmypathout)
            i) Change the _mysample = <sample_identifier> 
            # _mysample is the sample identifier
            # save the file


!!! danger "check the signals"




######  <i>Step 3: Run HDRMscans.mac script from terminal </i>
 
        FOURC> qdo ./HDRMscans.mac  
        # Notes: HDRMscans.mac contains all the script



######  <i>Step 4 : If you want to check the best height for the sample (finding smaller sample best position) </i>

        FOURC>heightscan 

        a) Data will save at 'tiff' folder inside the user folder at id4b
        b) Check the quality of the datasets at nexpy
        b) Go to the best position of the sample 
            FOURC> umv samz <position of the sample>  

######  <i>Step 5: Run three rotation crystal scan </i>
      It will rotate the crystal three times at different chi and theta angle

        FOURC> threextalscan 300 1 

        #Notes: In the threextalscan 1st parameter is temperature 300K and the second parameter is waiting time 1 min
            - It will vary chi, theta and phi angle
            - Collect data phi 0-365 with 3650 images (1 degree/frame)
            - You can the change the exposure time (if needed)

        a) Data will save at raw6M in id4b folder



#### Quick video on data collection (make sure you read the above instructions before watching the video)


<iframe width="600" height="305" src="https://www.youtube.com/embed/qsAZLayF4Ow?si=oIitQSArHTU1FunV" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>




######  <i>Step 6: Check data nexpy  </i>
Please look at the [Data visualization](https://suchismitasarker.github.io/CHESS-ID4B-QM2/nexpy/ ) - Nexpy section

=============================================================================
!!! type "Temperature modify and collect data"

######  Change temperature from 300K and 90 K- (if you are at Nitrogen atomosphere)
            
        FOURC> te 100
        # note: temperature here is 100 Kelvin
        
Make sure the temperature is stable before you run script

        FOURC> threextalscan 100 1 


!!! danger "Practical guide of the temperature switch between nitrogen and helium"
      Click the link for details
            [Nitrogen --> Helium and Helium --> Nitrogen](https://suchismitasarker.github.io/CHESS-ID4B-QM2/temp/)

######


=============================================================================

!!! hint "Thin-film Alignment"
      Basic steps for single crystal thin-film sample alignment - HDRM. Detector height needs to change because of grazing incidence. Make sure you are able to see the samples (proper light arrangements)

Step 1:  Center the sample to the beam 

      a) Move chi, phi, and theta positions to their initial setup
            FOURC> umv chi 90   
            FOURC> umv phi 0  
            FOURC> umv th 0  

      b) Perform height adjustment
            Check the signal at the diode 
            FOURC> tw samz 0.01
            Move the sample in the Z-directions and cut the beam in half (for example: if the beam size is 300 microns, move 150 microns from the surface when the signal goes down)            

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/signals1.png?raw=true){ width="500" }
</figure>


      c) Place cursor at center of the sample 
                  
                  FOURC> umv phi 0
                  FOURC> umv phi 180
                  FOURC> umv phi 90
                  FOURC> umv phi 270

Step 2 :  Creating the file structure

      a) Create newfile 

            FOURC>newfile samplename


      b) Open HDRMscans.mac script for thin-film
            Change the sample ID

Step 3: Run HDRMscans.mac script from terminal

          FOURC> qdo ./HDRMscans.mac 
          #Notes:HDRMscans.mac contains all the script


Step 3: Check the best height for the sample it will generate tiff file

        FOURC>powderscan 300 1

        a) Check the quality of the data sets at nexpy
        b) Go to the best position of the sample

Step 4: Run three rotation crystal scan 

        FOURC> threxstalscan 300 1 
        #Notes: Parameters: Temperature = 300, Sleep = 1

Step 5: Check data nexpy 
(<i>please look at the Data visulization - Nexpy section </i>)


## Temperature dependent scans 

#### 300K- 475K at 25K temperature interval

Step 1: Follow the instruction of temprature switch 300K-500K and the temperature to stabilize

      def TScans_warmN2 '
      te = 325
      for (loopT=325; loopT<476; loopT=loopT+25){
      eval(sprintf("threextalscan %s 180",loopT))
      }

      '

#