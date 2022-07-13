# Welcome to Data Processing 

!!! type "NOTE"
    Single crystal data-processing codes are written by  [Dr. Jacob Ruff](https://www.chess.cornell.edu/about/staff-directory/jacob-ruff) based on reference

    * [1] [H. You, J. Appl. Cryst.(1999).32, 614-623](https://onlinelibrary.wiley.com/doi/epdf/10.1107/S0021889899001223) and 
    * [2] [W. R. & Levy, H. A. (1967). Acta Cryst. 22, 457–464](https://scripts.iucr.org/cgi-bin/paper?s0365110x67000970)

The purpose of this guide is to illustrate some of the main features that Jacob's code provides. It assumes a very basic working knowledge with python pakages. To download the package please go to the github link. 

The code provides various tools for stacking the raw data, finding Bragg peaks, solving orientation matrix and finally provide the HKL. The results are visible to [NeXpy GUI](https://nexpy.github.io/nexpy/). 


---
### Single crystal data-processing steps
---

* `STEP I`:  Calibrate Detector & Beamline
* `STEP II`:  Stack data
* `STEP III`:  Find Bragg peaks
* `STEP IV`:  Solve orientation matrix
* `STEP V`:  Convert stacks of data to HKL volume 


!!! danger "Usage"

# Examples


!!! tip " Step I :  Calibrate Detector & Beamline" 



After collecting data from CeO2, LaB6, we calibrate the date by using pyFAI-calib2. Referemce shown below

Reference: 
pyFAI reference :[pyFAI](https://pyfai.readthedocs.io/en/master/).
pyFAI-calib2 : [calibration_video](https://pyfai.readthedocs.io/en/master/usage/cookbook/calib-gui/index.html#cookbook-calibration-gui) Calibration of a diffraction setup using the Graphical User Interface (GUI) 

    >>>``pyFAI-calib2``            #   generates .poni and mask.edf files

 

===========================================================================

!!! tip "STEP II :  Stack data"

The script take all the detector's raw .cbf files and performed calibration. You can the get the [stack_em_all](https://github.com/suchismitasarker/CLASSE-id4b/blob/main/codebase_for_use/stack_em_all_cbf_2022.py). 
 
    
    >>>``python stack_em_all_cbf_2022.py``    chem_formula sample_id spec_scan_num temperature



===========================================================================

!!! tip "STEP III:  Find Bragg peaks"
[simple_peakfinder](https://github.com/suchismitasarker/CLASSE-id4b/blob/main/simple_peakfinder.py) script

    >>>``python simple_peakfinder.py`` */full/path/to/stack/ 0.95*

Would consider anything above 95% of max counts as a Bragg peak

===========================================================================

!!! tip "STEP IV:  Solve orientation matrix"
[auto_ormfinder](https://github.com/suchismitasarker/CLASSE-id4b/blob/main/auto_ormfinder.py) script 

    >>>``python auto_ormfinder.py`` */full/path/to/stack/ peakfilename.nxs*

===========================================================================

!!! tip "STEP V:  Convert stacks of data to HKL volume"

[Pil6M_HKLConv](https://github.com/suchismitasarker/CLASSE-id4b/blob/main/Pil6M_HKLConv_3D_2022.py) python script (edit to point to project, ormatrix, and define HKL grid)

    >>>``python  Pil6M_HKLConv_3D_2022.py`` *temperature* 


===========================================================================