

#####   6-Megapixel Pilatus3

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-photos/blob/main/detector.png?raw=true)
</figure>

 The large Dectris Pilatus 6M photon counting detector shown above. The detectos are used to count the x-rays from desired bunches.


Table 1 : Names of the Pilatus

| Motor | Commands | Comments | 
| -------------- | :---------: | ---------- | 
| PILATUS 2 | PIL2 | Pilatus |  
| PILATUS 6 | PIL6 | Pilatus 6M detector | 
| PILATUS 6 | Pil6my | Move pilatus 6M detector in Y direction |
| PILATUS 6 | Pil6mz | Move pilatus 6M detector in Y direction |
| PILATUS 6 | Pilroi | Pilatus 6M detector region of interest |


#### Pilatus

"The  PILATUS  300K  detector  is  a  2D  detector  (developed  by  PSI  and  sold  by Dectris)  with  a  pixel  size  of  172x172m2,  487x619  pixel  active  area,  20-bit/pixel  dynamic  range  and  readout  time  of  7  ms.  The  quantum  efficiency  is 91% at 5.4 keV, 96% at 8 keV and 37% at 17.5 keV.To start operating the Pilatus one has to proceed as follows:1)From the experimental terminal inEH2p10user@haspp10e2:~$ ssh –l det haspp10pilatushaspp10pilatus:~$cd p2_dethaspp10pilatus/p2_det:~$runtvx2)Start Pilatus Tango server ‘Pilatus/P10E2’ from the Astor panel3)Make sure the detector is uncommented in the online.xmlfile4)restart Spocksession5)Setup new filename /directoryby[]: p10_newfile directoryname6)Use ‘p300take’ or ‘p300series’ commands to record images.To start the P10 image viewer one has to brows to the following directory"


