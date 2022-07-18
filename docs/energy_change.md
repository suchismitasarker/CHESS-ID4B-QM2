
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


