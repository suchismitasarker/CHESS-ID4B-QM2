# Welcome to CHESS &#60QM&#62<sup>2</sup> Sample Alignment



!!! danger "High Dynamic Range Reciprocal Space Mapping (HDRM)"


#### Basic Theory - HDRM

High Dynamic Range Mapping (HDRM) is primarily a method for studying single crystal samples, although it can also be effective for studying thin films. HDRM aims is to rapidly study wide regions of reciprocal space, collecting the intense Bragg peaks required to refine crystal structures along with weak features associated with superstructures, and the slowly modulated scattering associated with phonons and short-range order[[1](https://www.chess.cornell.edu/srn-article-cartography-7-dimensions-chess)].

!!! hint "Single Crytal Alignment"
      Basic steps for single crystal sample alignment - HDRM

<figure markdown>
  ![Image title](https://github.com/suchismitasarker/CHESS-ID4B-QM2/blob/main/pictures/goniometer1.png?raw=true){ width="150" }
</figure>


!!! danger "Carefully and slowly insert the sample in the top of the sample stage"
######  <i>Step 1:  Manually stage:  center the sample to the beam </i>

            FOURC> umvr samz 0.1 (relative motion of the sample movement up (+) and down (-)) 
            FOURC> umv phi 0
            FOURC> umv phi 180
            Move x and y to make the sample to the cursor
            FOURC> umv phi 90
            FOURC> umv phi 270
            Do it iteratively until the center of the axis match the sample position   


######  <i>Step 2 :  Create file structure </i>

      # Create newfile from the SPEC terminal, you need to provide acurate Element Name (K, Sc etc), special character does not work (.,:" etc)
      # samplename : chemical name of your sample, make sure you created folder in your directory
                  
                  FOURC>newfile <samplename> 
           
      
            

      # Look the table in the googgle doc
      Provide all the correct informations for metadata in the server
      

      | Sample name | chemical formula | Crystal Structure | Space group | Space group #| Unit cell parameters | 
      | :----------:| :---------------:| :----------------:| :---------: | :-----------:| :--------------------:
      |   CeO2      |       CeO2       |       Cubic       |   Fm-3m     |    225         |a=5.41, b=5.41, c=5.41, alpha=90, beta=90, gamma=90
      | :----------:| :---------------:| :----------------:| :---------: | :-----------:| :---------------------:      


      # sample_chemical_formula -- Provide chemical formula of the sample (e.g AV3Sb5): CeO2
      # crystal_system_rt -- Provide room temperature sample crystal system : cubic
      # sample_space_group -- Provide the sample space group :Fm-3m
      # sample_space_group_number -- Provide the sample space group number : 225
      # sample_unit_cell -- Unit cell dimensions  (units: angstrom) :  a = 5.41, b = 5.41, c = 5.41, alpha = 90, beta = 90, gamma = 90
      # phase_transition -- Will the sample undergo a phase transition during the experiment? If yes,what are the temperature and space group? (default: ):N.A

######  <i>Step 3: Run HDRMscans.mac script from terminal </i>
 
New experiment, you need start and run  HDRMscans.mac which contains all the script




                FOURC> qdo ./HDRMscans_new.mac 


            Reading file "/nfs/chess/id4b/2026-2/sarker-0000-a/HDRMscans_new.mac".

            ================================================
                    HDRM MACRO SYSTEM LOADED
            ================================================

            Welcome! Start with: setup_scan_parameters
            help or show_commands- command list

                
######  <i>Step 4: Show commands from the script </i>

show_comand script will show availble commands at the terminal


                
                FOURC> show_commands 



            === QUICK COMMAND REFERENCE ===

            setup_scan_parameters     - Setup (run first!)
            heightscan               - Height scan (default params)
            heightscan <s> <e> <n> <t> - Height scan (custom)
            powderscan <temp> <sleep> - Powder scan
            threextalscan <temp> <sleep> - Main HDRM scan
            low_temp_scan            - Default 20K-130K
            low_temp_scan_custom     - Custom low temp
            warmup                   - Default 140K-270K
            warmup_custom            - Custom warmup
            cooldown [start end step] - Cooldown sequence
            spin_xtal_phi            - Continuous spin
            spin_ice                 - Ice continuous spin
            help                     - Full help
            Type command name for details.

######  <i>Step 5: Run setup_scan_parameters script from terminal </i>

SETUP:
  setup_scan_parameters    - Set sample name and count time (RUN THIS FIRST!)
  
        FOURC> setup_scan_parameters 

        === SCAN SETUP ===
        Enter sample name [default: standard/]:  ()? sample1
        Enter count time [default: 0.1]:  (0)? 0.1 (#this is exposure time)


        # provide the sample name
        # if the chemical name of your sample is same, however, it is different sample of the same batch, you need to change the setup_scan_parameters. 



######  <i>Step 6: Run heightscan script from terminal </i>

SETUP:
   heightscan               - Run height scan with default parameters (-0.6 0.6 60 0.2)
   heightscan <start> <end> <steps> <exp_time> - Run custom height scan


            FOURC> heightscan

        a) Data will save at 'tiff' folder (Example : /nfs/chess/id4b/2026-1/sarker-0000-a/tiffs) inside the user folder at id4b
        b) Check the quality of the datasets at nexpy, DONOT Double click the image, the program will crush
        b) Go to the best position of the sample 
            FOURC> umv samz <position of the sample>  


#### <i> Step 7 </i> : Take a look at the height scan data 

        * Step1 : Go to 'File' tab
        * Step 2 : Go to 'Import' tab 
        * Step 3: Go to 'Import image stack'
        * Step 4: Go to desired file location
        * Step 5: Select the folder (it will not show any images)
        * Step 6: Select the images (mostly 50-60 images)
        * Double clicked the stack images
        * Go to the signal and click log scale
        * Go to z tab and press forward (it will go through the images)
        * Find the maximum signal in the height
        * Go to the terminal FOURC > umv samz <best_sample_height>

#### Quick video on <i> 'heightscan' </i> visualization (there is text below as well)
<iframe width="600" height="300" src="https://www.youtube.com/embed/lC853bBnRas?si=OLcOmv5HoKCyejph" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


######  <i>Step 8: Collect data at room temperature - Run three rotation crystal scan </i>
       # It will rotate the crystal three times at different chi and theta angle

                FOURC> threextalscan 300 1 

        # here parameter 300 is temperature and 1 is sleeping time

        Note: DONOT forget to put the paramters (temerature and sleep time), otherwise, temperature controller will try to go to 0K
       
        #Notes: In the threextalscan 1st parameter is temperature 300K and the second parameter is waiting time 1 min
            - It will vary chi, theta and phi angle
            - Collect data phi 0-365 with 3650 images (1 degree/frame)
            - You can the change the exposure time (if needed)

        # Data will save at raw6M in id4b folder (Example : /nfs/chess/id4b/2026-1/sarker-0000-a/raw6M )

######  <i>Different temperaturescan commands </i>



!!! danger "You need to follow "Temperature switch" instruction manual befor running any command!"


                low_temp_scan                                   - Default scan: 15K to 110K (step 15K)
                low_temp_scan_custom                            - Interactive custom low temp scan
                low_temp_scan_custom <start> <end> <step>       - Custom low temp scan
                warmup                                          - Default: 120K-290K with gas controls
                warmup_custom                                   - Interactive custom warmup sequence
                warmup_custom <start> <end> <step>              - Custom warmup sequence
                cooldown                                        - Interactive cooldown sequence
                cooldown <start> <end> <step>                   - Custom cooldown sequence


######  <i>Step: Run temperaturescan scan </i>

        spin_xtal_phi            - Spin sample continuously (phi 0-360)
        spin_ice                 - CONTINUOUS spinning for ice samples
        spin_xtal_phi_10min      - Spin sample 5 cycles (10 min approx)
        spin_xtal_phi_20min      - Spin sample 10 cycles (20 min approx)

######  <i> SHORT WORKFLOW </i>

        1. setup_scan_parameters  (set your sample name and count time)
        2. heightscan            (check sample quality)
        3. threextalscan 300 1   (main HDRM measurement)
        4. warmup/cooldown       (temperature series)


######  <i> UTILITY </i>
        help                     - Show this help message
        show_commands            - Show command reminders



        FOURC> help

        === HDRM MACRO HELP ===
        Available commands:

        SETUP:
        setup_scan_parameters    - Set sample name and count time (RUN THIS FIRST!)

        SCANS:
        heightscan               - Run height scan with default parameters (-0.6 0.6 60 0.2)
        heightscan <start> <end> <steps> <exp_time> - Run custom height scan
        powderscan <temperature> <sleep_time>       - Run powder diffraction scan
        threextalscan <temperature> <sleep_time>    - Run main HDRM scan

        TEMPERATURE SCANS:
        low_temp_scan            - Default scan: 20K to 130K (step 20K)
        low_temp_scan_custom     - Interactive custom low temp scan
        low_temp_scan_custom <start> <end> <step> - Custom low temp scan
        warmup                   - Default: 140K-270K with gas controls
        warmup_custom            - Interactive custom warmup sequence
        warmup_custom <start> <end> <step> - Custom warmup sequence
        cooldown                 - Interactive cooldown sequence
        cooldown <start> <end> <step> - Custom cooldown sequence

        SAMPLE SPINNING:
        spin_xtal_phi            - Spin sample continuously (phi 0-360)
        spin_ice                 - CONTINUOUS spinning for ice samples
        spin_xtal_phi_10min      - Spin sample 5 cycles (10 min approx)
        spin_xtal_phi_20min      - Spin sample 10 cycles (20 min approx)

        UTILITY:
        help                     - Show this help message
        show_commands           - Show command reminders

        WORKFLOW:
        1. setup_scan_parameters  (set your sample name and count time)
        2. heightscan            (check sample quality)
        3. powderscan 300 1      (optional: powder diffraction)
        4. threextalscan 300 1   (main HDRM measurement)
        5. warmup/cooldown       (temperature series)

        ICE SAMPLE WORKFLOW:
        1. setup_scan_parameters
        2. heightscan
        3. spin_ice (start continuous spinning)
        4. In another terminal: run threextalscan <temp> <sleep>

        EXAMPLES:
        setup_scan_parameters
        heightscan
        low_temp_scan            # Default 20K-130K
        low_temp_scan_custom 50 200 30  # 50K to 200K in 30K steps
        warmup                   # Default 140K-270K
        warmup_custom 150 300 25 # 150K to 300K in 25K steps
        cooldown 300 100 20     # 300K to 100K in 20K steps
        spin_ice

