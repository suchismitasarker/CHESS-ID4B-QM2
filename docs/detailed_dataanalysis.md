

# Detailed Data Analysis for QM2 Dataset 

Make sure your dataset is completely processed with QM2 in-house software or Nxrefine software.Once you have HKLI.nxs files, you can start start to perform in-depth data analysis. 



<b> In-depth data analysis (three different github links are below) </b>
Different <b> github </b> links are provided below for the in-depth QM2 data analysis, if you have any questions, please send an email to [beamlist scientist](ss3428@cornell.edu)

### [NXS-ANALYSIS-TOOL](https://nxs-analysis-tools.readthedocs.io/en/latest/examples/index.html)
!!! hint "Detailed Data Analysis of QM2 dataset - NXS-ANALYSIS-TOOL"

    Once you have received the HKLI data from the QM2 beamline, you can visualize it using Jupyter Notebook. Additionally, you can perform various data analyses with <b> [nxs-analysis-tool](https://nxs-analysis-tools.readthedocs.io/en/latest/examples/index.html) </b> developed by Dr. Steven Gomez.

    For 3D-PDF details, you can watch the [youtube video](https://www.youtube.com/watch?v=O4kexPa13ic) by  Dr. Steven Gomez.

        The software enables you to: 

        i)   Load data into Jupyter Notebook.
        ii)  Perform different slicing and visualization techniques.
        iii) Create line cuts
        iv)  Visualize temperature-dependent data.
        v)   Extract order parameters and 
        vi)   Symmetrize data
        vii)  Extract 3D-delta PDF.

        For access to the orGUI software, visit their GitHub repository: 
                         https://zenodo.org/records/15492957

    <i> <b> If you use the software, please cite the software package: 
    
    Steven Gomez Alvarado, & Soren Bear. (2025). stevenjgomez/nxs_analysis_tools: v0.1.3 (v0.1.3). Zenodo. 
    https://doi.org/10.5281/zenodo.15206517 </i> </b> 

 
## 🔬 Quantum Materials Analysis Notebook

#You can run the full HDRM processing notebook interactively in Google Colab:

<a href="https://colab.research.google.com/drive/13pxbP-x5YinKdkWpURBmMKRLp9SQCtqr?authuser=4#scrollTo=shP_EDON253l" target="_blank">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab load QM2 data"/>
</a>

      
### [orGUI](https://zenodo.org/records/14271047)
!!! hint "Thin-film data analysis - orGUI"

    A team led by Dr. Timo Fuch developed [orGUI](https://zenodo.org/records/14271047) is a software that can be used to determine the orientation of single crystal samples in X-ray diffraction experiments. Recently it is implemented at QM2 for thin-film sample for CTR meausrement. 

        For access to the orGUI software, visit their GitHub repository:
                     https://zenodo.org/records/14271047.

    <i> <b> If you use the software, please cite the software package:

    Fuchs, T. (2024). orGUI: Orientation and Integration with 2D detectors (1.2.0). Zenodo.
                     https://doi.org/10.5281/zenodo.14271047 <i> <b>




!!! info "If you want to access orGUI through CHESS general node"

    If you want to visulize raw data faster, then you need the access to the raw data from general server

        Follow the below steps: 
        i)   Talk to beamline scientist 
                    a) You need to create config file for the each samples to use the orGUI
                    b) You need to have the cif file
        ii)  Log in to the lnx201 general server
                    [....@lnx ~]>> ssh -Y <username>@lnx201.classe.cornell.edu
        iii) Link your proposal directory from the CHESS filesystem:        
                    [....@lnx201 ~]>>ln -s /nfs/chess/id4b/2025-2/<proposal_name> ~/<proposal_name>
                    (example)[....@lnx201 ~]>> ln -s /nfs/chess/id4b/2025-2/sarker-000-a ~/sarker-000-a
        iv)  Request Additional Memory and CPU Resources
                    [ss1234@lnx201 ~]>> qrsh -q interactive.q -l mem_free=200G -pe sge_pe 12
        v)   Activate the orGUI Environment
                    [ss1234@lnx308 ~]>>source /nfs/chess/sw/orGUI/bin/activate
        vi)  Launch orGUI
                    (orGUI)[ss1234@lnx308 ~]>> orGUI


### [X-TEC](https://www.pnas.org/doi/10.1073/pnas.2109665119)

!!! hint "Unsupervised Machine Learning with QM2 data - XTEC"

    A team led by Dr. Kim, including Cornell physicists and computer scientists in collaboration with Dr. Jacob Ruff, has developed an innovative and interpretable machine learning algorithm for the Quantum Materials beamline at CHESS. This algorithm, known as XRD Temperature Clustering (X-TEC), is designed to analyze and interpret big data from modern X-ray diffraction experiments.

    You can find more details in their publication: [Harnessing interpretable and unsupervised machine learning to address big data from modern X-ray diffraction](https://www.pnas.org/doi/10.1073/pnas.2109665119).


        

        For access to the X-TEC software, visit their GitHub repository:
                     https://github.com/KimGroup/XTEC.


### Structural Refinement

!!! hint "Single crystal refinement"
        QM2 data could be used for X-ray crystallography by commercial software packages such as Bruker’s APEX328[1] and Rigakus CrysAlisPro29[2]. Note: Beamline does directly support the structural refinement. However, if you need more information, talk to the beamline sscientist.


        1. Bruker AXS Inc. Apex3 software suite for single-crystal x-ray diffraction. //www.bruker.com/en/products-and-solutions/diffractometers-and-x-ray-microscopes/single-crystal-x-ray-diffractometers sc-xrd-software/apex.html.

        2. Rigaku Oxford Diffraction. Crysalispro software system, version 1.171.38.46. https://rigaku.com/products/crystallography/x-ray-diffraction/crysalispro, 2017. Rigaku Corporation,Oxford, UK.

