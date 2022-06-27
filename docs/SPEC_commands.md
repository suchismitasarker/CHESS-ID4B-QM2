# Welcome to ID4B SPEC command

!!! hint "SPEC Detailed Descriptions"
    For full documentation visit [certif.com](https://certif.com/).


"spec is internationally recognized as the leading software for instrument control and data acquisition in X-ray diffraction experiments."

---
In ID4B, we used several SPEC along with python and C written by [Dr. Jacob Ruff](https://www.chess.cornell.edu/about/staff-directory/jacob-ruff). Few important commands are shown below. For more information visit to the above mentioned website.

---
!!! danger " For more information visit [SPEC manual](https://certif.com/) and [SPEC macros](http://127.0.0.1:8000/SPEC_macros/)"

## Important SPEC commands 

* `mkdir` - Create a new directotry.
* `a2scan` - two-motor scan.
* `abscan` - incident-reflected angle scan.
* `br` - br and ubr - move to the reciprocal space coordinates (HKL).
* `ca` 			- calculate motor settings for a given point in reciprocal space
* `cal` 			- calculate motor settings for a given point in reciprocal space
* `cat` 			- UNIX shell cat command
* `cd` 			- change working directory
* `cmAX` 		- Compumotor AX motor controller
* `config` 		- edit the hardware configuration
* `config_adm` 		- configuration - administer hardware configuration file
* `constant` 		- define a constant global symbol
* `counting` 		- timer/scaler commands, macros and variables
* `cscan` 		- Continuous Scans
* `ct` 			- count and print results
* `dscan/lup` 		- motor scan relative to the starting position
* `d2scan` 		- two-motor scan relative to the starting positions
* `def` 			- def and rdef - define a macro
* `disable` 		- disable and enable - Disable and Enable Hardware
* `do` 			- execute a command file
* `dtscan` 		- relative temperature scan
* `dxp` 			- XIA DXP CAMAC MCA
* `encode` 		- encode()/decode() - data stream manipulation
* `epics` 		- EPICS specific functions
* `files` 		- conventions for file/device output
* `flow` 		- flow control
* `flyscan` 		- Continuous Scans with Multichannel Scalers
* `fourc` 		- 4-circle geometry modes
* `funcs` 		- functions - built-in functions
* `global` 		- declare global variables
* `hbeamscan`   - Horizontal direction beam scan based on start, finish, interval and time arrguments
* `history` 		- command recall facility
* `hklscan` 		- general linear scan in reciprocal space
* `hscan` 		- scan along the H-axis in reciprocal space
* `install` 		- spec installation procedure
* `l` 			- UNIX file listing
* `libedit` 		- libedit/readline - command line recall and editing
* `lm` 			- list motor software limits
* `ls` 			- UNIX file listing
* `lscan` 		- scan along the L-axis in reciprocal space
* `macros` 		- description of macro facility
* `mk / umk` 		- move to the reciprocal space coordinates (HKL)
* `mono` 		- monochromator - monochromator control macros
* `motors` 		- commands and functions for controlling motors
* `move_info` 		- move_info() - returns what would happen on a move
* `mr` 			- move to a given angle of specular reflection
* `mv` 			- mv and umv - move one motor
* `mvd` 			- move a motor in dial units
* `mvr` 			- mvr and umvr - move a single motor relative to its current position
* `newvbeam`        - new beam position based on vertical beam or horizontal beam scan
* `newfile` 		- data file management
* `newmac` 		- re-read the standard macro definitions
* `nu`          - `???????`
* `os1`         - `optical slit 1??????`
* `os2`         - `??????`
* `pwd` 		- print spec's current working directory
* `park6m`      - park the 6M PILATUS detector to 175m (x), 924.5m (y) and 200m (z) in  directions
* `qdo` 		- execute a command file without echo
* `rscan` 		- specular reflectivity scan
* `r2scan` 		- reflectivity background scans
* `readline` 		- libedit/readline - command line recall and editing
* `resume` 		- continue an aborted scan
* `roi` 		- Region of Interest counters
* `scans` 		- scans and scans.4 - read data from ASCII spec data format scan files
* `server` 		- spec server/client - issue commands and control hardware remotely
* `set` 		- define the user angle of a motor
* `set_dial` 		- define the dial position of a motor
* `set_lm` 		- set lower and upper software limits
* `set_sim` 		- set simulate (no hardware) mode
* `setplot` 		- set plotting options
* `setpowder` 		- configure powder-averaged scans
* `setscans` 		- configure scan options
* `showtemp` 		- display the current temperature
* `sixc` 		- 6-circle geometry modes
* `spec` 		- spec, fourc, twoc, surf, etc. - X-ray diffractometer operation for specific configurations
* `spec_menu` 		- spec_menu() - create interactive menu from specifications
* `spec_par` 		- spec_par() - sets internal parameters
* `te` 			- read or set the temperature
* `teramp` 		- ramp the temperature to a new set point
* `tscan` 		- temperature scan
* `tw` 			- "tweak" motors
* `tweakup` 	- scan the monochromator in d direction (mond), go to the midlle and scan the undulator and move to the highest position
* `unkludgenu`  - `??????`
* `vi` 			- invokes the standard UNIX visual editor
* `vscan` 		- Variable Step Size Scans
* `vbeamscan` 	- Vertical direction beam scan based on start, finish, interval and time arrguments
* `w` 			- wait for moving and counting and then beep
* `wa` 			- list all motor positions
* `wait` 		- wait() - synchronization with moving, counting and other activity
* `wh` 			- where, principal axes and reciprocal space
* `whats` 		- identify what an object is
* `wm` 			- print information about one or more motors
* `wmono`       - where is monochromatic beam
* `wmonoall`    - where motor and their position including the motors, phi and filters 
* `wmonoall`    - where is mirror position
* `wot`         - where is optical tables
* `ws1`         - where is first slit
* `ws1`         - where is second slit
* `w6m`         - where 6M detector
* `wslits`      - where is both slit 1 and slit 2

---