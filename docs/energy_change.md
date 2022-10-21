
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
