
### Start the new users at the beamline
* `newmac` (# <i> uploading all the macros </i>)
* `userslist.mac`
* `cd Scripts/`
* `./newusers-4b.sh 2022-3 sarker-0000-a` ( <i>this will create file both in id4b and id4baux </i>)
* copy HRDMscans.mac to the specific folder
* FOURC > `qdo ./HRDMscans.mac`
* FOURC > `newfile (name of newfile)`
* Change the HDRMscans.mac file with `_samplename` and `_sampledirectory`



#### Flux Calculator
[CHESS Flux calculator](https://www.chess.cornell.edu/userstechnical-resourcescalculators/ion-chamber-flux-calculator) at the beamline


#### flyscan 
* `flyscan_setup`
* selecct motor using space 
* check flyscan
* FOURC > `powderscan 300 1`


### User HDRMScan details about the macros




#### Energy change

##### Removing mirror for higher energy calibrations

'''

        newfile 
        wmirror
        umvr  mird  miru    
        opens
        wot
        tw tabzd    tabzui    tabzuo  
        ws2
        wot
        wm diftabz
        tw tabzd    tabzui    tabzuo  
        tw tabxd
        closes
        syncE

'''


##### Energy calibrations


'''

            moveE 25
            umvr mond
            matchUE 8
            tweakup
            wm
            lup montrav -3 3 60 0.1
            umv montrav 163.98
            tweakup
            wm monchi
            Tw monchi
            lup monchi -0.5 0.5 20 0.1
            plotselect ic2 diode
            splot
            Plotselect ic2
            splot
            syncE
            plotselect ic2 diode
            splot
            umv monchi pl_xMAX
            getE

            wot
            ws1
            tw tabzd    tabzui    tabzuo 1 1 1
            tw tabxd .05
            tweakup
            syncE
            moveE 30.6; matchUE 8


'''


### Detector setup

REXS 

Setup : 

mv pil6mx 100
mv pil6my 760

* `mv pil6mx 100` 		- move pilatus 6M to 100 mm x direction 
* `mv pil6my 760` 		- move pilatus 6M to 760 mm y direction


To take the detecotor all the way end of the hutch 

mv pil6mx 233
mv pil6my 885

* `mv pil6mx 233` 		- move pilatus 6M to 233 mm x direction 
* `mv pil6my 885` 		- move pilatus 6M to 885 mm y direction


### Change the config file 

open the terminal

```
config 
config configaration will open
Go to the specific motor 
change the required motor config
press w 
control c 
reconfig
```
To go to the specific motor press c,c (twice)   
shift+' to modify anything
     


