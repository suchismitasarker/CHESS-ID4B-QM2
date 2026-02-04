
# NXRefine
The code is written by Dr. Ray Osborn. More details will be available [NXRefine](https://nexpy.github.io/nxrefine/).The code provides various tools for stacking the raw data, finding Bragg peaks, solving the orientation matrix, and finally providing the HKL. 

# Data Policy 
!!! hint "Data policy"
      We only stored the raw data for six months and processed data for a year. Please process the data and copy it to your server. If you need more time, then consult your beamline scientist.




!!! danger "CHESS data processing steps" 

### Steps to use the NXRefine GUI at CHESS data analysis computer 

* <i> Step 0 </i>: Create the nxrefine folder with correct calibration file 
      Talk to beamline scientist if you have any questions)

* <i> Step 1 </i>: Link raw data to process data folder

            Import and link the data from id4b to id4baux folder


<iframe width="600" height="315" src="https://www.youtube.com/embed/IAX8-wOgImc?si=CdC_gDJQmBnrNGEq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



* <i> Step 2 </i>: Check data and manage workflow

            Load the data from the GUI


<iframe width="600" height="315" src="https://www.youtube.com/embed/9Js5P2Gn_nk?si=7tnBI5l4xqypNcmh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


* <i> Step 3 </i>: Find peaks and max peak values

            DONOT submit job link, max, find together, run it one by one, otherwise, program will break

<iframe width="600" height="315" src="https://www.youtube.com/embed/3bl7pVS2CWI?si=Zdvoku9h_T1JQkfG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


* <i> Step 4 </i>: Finding orientation matrix
      
            If you are not able to do that, talk to beamline scientist

<iframe width="600" height="315" src="https://www.youtube.com/embed/AKL9SOP9clQ?si=BmiP6PhG6uTt3T8u" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


* <i> Step 5 </i>: Check HKLI 
      
            Check the data

<iframe width="600" height="315" src="https://www.youtube.com/embed/qbSChMwf0Ck?si=4oNTPcOg9_gqFA2p" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


* <i> Step 6 </i>: Check data : HKLI Volume

<iframe width="600" height="315" src="https://www.youtube.com/embed/5_G1QN8JlMw?si=CckLYZPVJmbeBffS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

* <i> Step 7 </i>: Parent file selection for processing different temperatures datasets

            * Check the data
            * Make sure data looks good 
            * Select the file as the parent file

<iframe width="600" height="315" src="https://www.youtube.com/embed/dCsU3QN5yQ0?si=56-IMaUNto7gdNBh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


* <i> Step 8 </i>: Check the viewing server log


<iframe width="600" height="315" src="https://www.youtube.com/embed/EwwbVRqq308?si=u0m6DHsAH_AgnnOb" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



=================================================================

## Running jobs from the terminal in general node, during beamtime


!!! hint "During beamtime nxrefine "

       Steps for Data Analysis (during beamtime) 


            
            Step 1: Open your terminal:
            ssh <chess_id>@lnx201.classe.cornell.edu

            Step 2: In the beamline data analysis GUI nxrefine
            Import the data: https://www.youtube.com/watch?v=IAX8-wOgImc

            Step 3: Beamline file qsub file change: 
                  cd /nfs/chess/id4baux/2025-2/<proposal_id>/scripts/

            Step 4: Change the permission in beamline data analysis computer and your own computer
                  chmod -R 777 /nfs/chess/id4baux/<cycle_number>/<proposal_id>


            Step 5: Modify the qsub script in the folder (below is the details)

            Step 4: Change the permission again in beamline data analysis computer and your own computer
                   chmod -R 777 /nfs/chess/id4baux/<cycle_number>/<proposal_id>

            Step 6: Submit the job from your own terminal

                  qsub -q all.q -l mem_free=200G -pe sge_pe 16 /nfs/chess/id4baux/2025-1/<proposal_id>/qsub_116.sh 



##### Step 5 Details: How to change scripts:

* Rename the file name of the script with temperature
* Change the directory and temperature of the folder

                  Step 1: USER_DIR='/nfs/chess/id4baux/2026-1/sarker-0000-a/nxrefine/FeNiCo/S1/'
                  Step 2: for TEMP in 20;


### Option 1 : Parent file NOT available       
* If the parent file is not avilable when you submit the jobs, run only below commands and Comment out other commands

            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --load --overwrite
            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --link --max 
            nxfind --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 -t 10000 --overwrite

* Comment out other commands when parent file is not avilable

            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --link --copy --max
            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --copy
            # nxreduce --directory ${USER_DIR}${TEMP}  --entries f1 f2 f3 --refine
            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --transform --combine --regular
            # nxreduce --directory $USER_DIR$TEMP --pdf --regular

* After the parent file is ready, make sure all the previous jobs (load, link, max, find) are completed for one particular temperature, modify the same file and run below commands and comment out below commands

            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --copy
            nxreduce --directory ${USER_DIR}${TEMP}  --entries f1 f2 f3 --refine
            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --transform --combine --regular

* Comment out other commands as you already ran that

            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --load --overwrite
            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --link --max 
            # nxfind --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 -t 10000 --overwrite


### Option 2: Parent file available

If the parent file is avilable when you submit the jobs, run only below commands and Comment out other commands

            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --load --overwrite
            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --link --copy --max
            nxfind --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 -t 10000 --overwrite
            nxreduce --directory ${USER_DIR}${TEMP}  --entries f1 f2 f3 --refine
            nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --transform --combine --regular

* Comment out other commands (those are for option 1 only)

            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --link --max   
            # nxreduce --directory ${USER_DIR}${TEMP} --entries f1 f2 f3 --copy          

