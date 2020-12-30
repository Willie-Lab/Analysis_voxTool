# VoxTool 2.0


## Setup

- Clone the repository from GitHub
- Create a Conda environment from the definition file
  ```
  conda env create -f <PATH TO conda_env.yml>
  ```
  This creates an environment named `vt` in which to run voxTool.
  Note: cona_env.yml is located in the repository folder

## Running

- Activate the conda environment:
  ```
  source activate vt
  ```
- Launch the program:
  ```
  python launch_pyloc.py
  ```

## Usage
0. Load a CT file, adjusting the threshold as necessary. To adjust the
   threshold, change the number in the bar at the top of the window
   marked ```CT Threshold```, then press the ```Update``` button next to it.
1. If continuing a previous localization: load the existing coordinates
   from a JSON coordinate file using the ```Load Coordinates``` button.
2. Press ```Define leads``` to set the names, shapes, types, and microcontacts
   for each implanted lead. Shapes are rows x columns.
3. Select the lead you wish to localize in the dropdown menu labeled ```Label```
   in the upper left corner
4. Click on the CT to highlight the next contact on that lead, then press
   ```Submit``` to mark its location
   - Alternatively, press the ```Seeding``` button to turn on seeding. VoxTool
     will attempt to extrapolate the locations of the remaing contacts
     as you select them, incrementing the contact number. Be sure to double-check that
     the results make sense, as occasionally two contacts
     will be given the same location
   - Alternatively, add the ends of a strip or depth
     or the corners of the grid with the ```Submit``` button, then press
     the ```Interpolate``` button. VoxTool will attempt to fill in the lead.
     It may not be completely successful. Pressing ```Interpolate``` again
     may interpolate additional contacts.
5. Press ```Add Micro-Contacts``` to add micro-contacts to any macro/micro leads.
6. Press the ```Save as``` button to save the list of localized contacts.
   If the checkbox labelled ```Include Bipolar Pairs``` is checked, locations
   will also be saved for the midpoint of each pair of neighboring contacts.

## Additional Usage Notes (by JP 12/16/20) 
*When defining electrode contacts and picking them out, the implant list may not always be correct and so the following steps will help us prevent picking out contacts that don't exist as well as preventing us from not picking contacts that are obviously present*
1. Open up both the implant list and montage form and compare the number of contacts for each trajectory on the implant list to the number of contacts set to channels on the montage form. List any discrepancies under a new column to the far right titled **Research Notes** and in the second row write **By:YOUR INITIALS  TODAY's DATE**. If there are no discrepancies note that there are no differences between montage and implant list.
2. When picking out contacts on voxTool define the electrodes based off of the implant list # of contacts.
3. When selecting the actual contacts on the CT, if all contacts definied off the implant list are clearly select and lable those contacts.
4. If a contact is ambiguous (not clearly isolated/defined) then see if that contact is included in the montage form based on previous discrepancies noted.
  * If contact is no on montage, don't select & label it. If it is on the montage, estimate position of contact and label it.

## Strips Localization Guide (by JP 12/30/20)
*This section will help explain how to localize strips when present in a subject*
1. Firstly, in voxTool you have the ability to define a certain electrode as a "strip" instead of a "depth".
2. When figuring out which contact on the strip is contact 1 - look for any indication first on the strip cartoon (if it exists). Sometimes there may be a (1) (2) numbering and in other cases there may be a different type of indiciation.
3. If there is no clear indiication of numbering, look for a circle where the electrodes tend to meet - that may indicate the location where the pig tails of the strips come out of the dura/cranium. From this, the most distal end (farthest from the "circle") willl be contact 1. 

*See drawing below*



## Keyboard Shortcuts:

Button | Key Sequence
------ |  ------------
Load Scan | Ctrl-O
Define Leads | Ctrl-D
Save As | Ctrl-S
Submit (contact panel) | S
Submit (lead definition window) | S
Delete (contact panel)| Delete
Delete (lead definition window)| Delete
Confirm (lead definition window) | Enter

## Other Notes
* The list of contact names is sorted by lead name, and within each 
lead by contact number. The ```Interpolate``` button does not always assign
contact numbers in the expected order, so be sure to double-check 
that the numbers it has assigned are the ones that you want after using 
it. 

