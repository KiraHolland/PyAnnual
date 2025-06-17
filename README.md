# PyAnnual (v1.1.0)
For annual layer identification and counting in glacier ice cores.

Based on Matchmaker (https://www.iceandclimate.nbi.ku.dk/data), PyAnnual is a Python-based, streamlined package that aids in multi-parameter annual layer identification in glacier ice cores using seasonally varying geochemical and physical parameters–no coding required! Improves upon Matchmaker for annual layer identification by allowing for:

* Easy editing of previously identified annual layer picks which can be uploaded and modified
* Straightforward addition or removal of chemical/physical parameters on every initiation of PyAnnual
* Simple tracking of edits to annual layer picks with each session

PyAnnual is designed for annual layer counting only and does not allow for the development of common timescales between ice cores (like in Matchmaker).

## Directions

**1.** Update input variables (“fn_path”, “columns”, “species_names (_optional_)”) in config.txt and save file.
   
**2.** Run PyAnnual.py to initiate software with your continuous ice core data.

**3.** To select an annual layer "pick", click anywhere in any subplot along the depth you have chosen. To delete a selection (uploaded or manually selected), right-click on the pick, or click   "Undo" if recently done. Click "Clear" to clear all manual selections.

**4.** To upload previous picks, click “Load Picks” and navigate to .csv or .xlsx file. File must be formatted with the first column as an “ID” (e.g., a running number), and the second column as depth. If you have previously used PyAnnual for annual layer ID, the output file is formatted for re-upload.
   
**5.** To save your selection, click “Save”.

## Options

* 'Min./Max.': Set x-lim range by inputting depth minimum and maximum, and click "Set"
* 'Undo': control-z function
* 'Pan: OFF/ON': Allows for manual panning without inadvertently selecting a new pick
* 'Load Picks': Upload previously identified annual layer picks. If previously uploaded  and updated with manual picks in a past session, previously uploaded picks will plot in blue, manually selected picks (from last session) will plot in purple, and uncertain picks will plot in grey.
* 'Clear': Clears ALL manually selected picks
* ‘max/min': Set y-lim of each paramater
* '<– Core Up': Pans to the left (up core, or shallower)
* 'Core Down –>': Pans to the right (down core, or deeper)
* 'Uncertain: ON/OFF': Allows user to identify a pick as "uncertain" for later investigation or estimation of error. Plots as grey line. Uploaded picks with "uncertain" picks will continue to plot grey. Indicated in ouput file as certain == 0, uncertain == 1.
* 'Save': Save all annual layer picks (uploaded or manually selected) as a .csv. "Source" coded as 1 == (new) manually selected, 2 == uploaded.

## Inputs (must be updated in config.txt)

**fn_path**:  Pathname to geochemical database with core depth information (.xslx only)

**header**:   Header row number in your geochemical database (example, first row = 0)

**columns**:  A LIST of column (parameter) names (strings) that will be used in annual layer identification, starting with the DEPTH column.<br/>Ex: columns = ['depth_m', 'h2o2_uM', 'IP_0.8_10um_ug_g', 'nssS_ssNa', 'Na_ng_g', 'nh4_uM', 'd18O_permil']

**species_names** (_optional_): Names to be used in y-axis labelling (starting with DEPTH), otherwise, "columns" will be used.<br/>Ex: species_names = ['Depth', 'H2O2', 'Particles', 'nssS/ssNa', 'Na', 'NH4', u'$\\mathrm{\\delta}$$^{18}$O']

## Outputs (once saved)
    
**selections.csv**: .csv file with uploaded and selected depth picks. "Source" defined as 1 = manually selected pick, 2 = uploaded pick.

## Requirements
Dependencies are automatically installed when you install the package
* python 3.7 or higher
* matplotlib>=3.0
* numpy>=1.18
* pandas>=1.0
* pyqt5>=5.15
* ipympl>=0.9.3
* notebook>=6.0
