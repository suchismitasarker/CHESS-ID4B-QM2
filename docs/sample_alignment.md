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
         
            FOURC> umv phi 0
            FOURC> umv phi 180
            Move x and y to make the sample to the cursor
            FOURC> umv phi 90
            FOURC> umv phi 270
            Do it iteratively until the center of the axis match the sample position                   

######  <i>Step 2 :  Create file structure </i>

      a) Create newfile 

            FOURC>newfile <samplename> 
            # samplename : chemical name of your sample sample


      b) Open HDRMscans.mac script and sort your path (sortmypathout)
            i) Change the <_mysample> 
            # _mysample is the sample identifier

######  <i>Step 3: Run HDRMscans.mac script from terminal </i>
 
        FOURC> qdo ./HDRMscans.mac  
        # Notes: HDRMscans.mac contains all the script



######  <i>Step 4 : If you want to check the best height for the sample </i>

        FOURC>heightscan 

        a) Data will save at tiff folder in id4b
        b) Check the quality of the datasets at nexpy
        b) Go to the best position of the sample

######  <i>Step 5: Run three rotation crystal scan </i>
      It will rotate the crystal three times at different chi and theta angle

        FOURC> threextalscan 300 1 
        #Notes: In the threextalscan 1st parameter is temperature 300 and the second parameter is waiting time 1

        a) Data will save at raw6M in id4b folder

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
      Basic steps for single crystal thin-film sample alignment - HDRM. Detector height needs to change because of grazing incidence

Step 1:  Center the sample to the beam 

      a) Move chi, phi, and theta positions to their initial setup
            FOURC> umv chi 90   
            FOURC> umv phi 0  
            FOURC> umv th 0  

      b) Perform height adjustment
            FOURC> check the signal at the diode 
            FOURC> cut the beam in half (for example: if the beam size is 300 microns, move 150 microns from the surface when the signal goes down)            

      b) Move the sample to the opposite, so it will be visible to the camera
            FOURC> umv chi 270
            Place cursor at sample middle 
            FOURC> umv phi 90
            FOURC> umv phi 180

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

!!! danger "Resonant Elastic X-ray Scattering (REXS)"

Number of elements in the periodic table (K and L edges)

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/QM2b%20-%20REXS.png?raw=true){ width="500" }
</figure>


##### Basic Theory - REXS


##### Basic steps for sample alignments - REXS


</i>
### Beamsplitting polarimeter

The polarization analyzer isolates and measures a unique series of diffraction resonances at the different K-edge.
