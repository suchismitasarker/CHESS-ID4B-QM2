# Welcome to CHESS QM2 Sample Alignment


![Image title](https://github.com/suchismitasarker/CHESS-photos/blob/main/beamline.jpeg?raw=true){ width="300" }

!!! danger "High Dynamic Range Reciprocal Space Mapping (HDRM)"


##### Basic Theory - HDRM

The High Dynamic Range Mapping (HDRM) is primarily a method for studying single crystal samples, although it can also be effective for studying thin films. The aim of HDRM is to rapidly study wide regions of reciprocal space, collecting the intense Bragg peaks required to refine crystal structures along with weak features associated with superstructures, and the slowly modulated scattering associated with phonons and short-range order[[1](https://www.chess.cornell.edu/srn-article-cartography-7-dimensions-chess)].


##### Basic steps for sample alignment - HDRM

Step 1:  Center the sample to the beam 

Step 2 :  Creating file structure

      a) Creating newfile 

            FOURC>newfile samplename


      b) Open HDRMscans.mac script
            Change the sample ID

Step 3: Run HDRMscans.mac script from terminal

          FOURC> qdo ./HDRMscans.mac 


Step 3: Check the best height for the sample

        FOURC>powderscan 300 1

        a) Check the quality of the data sets at nexpy
        b) Go to the best position of the sample

Step 4: Run three rotation crystal scan 

        FOURC> threxstalscan 300 1 
        #Notes: Parameters: Temperature = 300, Sleep = 1




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
