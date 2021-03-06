# LST-camera validation  (ongoing)
Scripts to do the tests for the validation of the LST cameras.

(Note): About the `lstchain` or `ctapipe` environements, needed in some stages of the analysis, see [https://github.com/cta-observatory](https://github.com/cta-observatory/cta-lstchain). You will need to execute `conda activate lst-dev` (or similar) before opening jupyter notebook.

# Rate scans analysis 
### Instructions to use

(Note): You need to have installed `PyPDF2` package, you can do it with `conda install -c conda-forge pypdf2`, and also not strictly requiered but recommended to use `lstchain` or `ctapipe` environements.

 1. Copy `.result` files from CaCo to your computer or PIC, inside some folder

2. Copy the contents of this github folder `rate_scans` all in same directory, from where we are going to run the script

3. We need more information than what's inside the files, that we do not have in CaCo, this needs to be written by hand in a file called `extra_data.txt` organised like this, matching the date in the doc and the date of the `.result` file (example of file used in LST-2 in https://github.com/juanjq/LST_camera_validation/blob/main/rate_scans/extra_data.txt)

```
date            HV          DAC     neighbor      gain
y-m-d-h:min:s , HV/not_HV , 1/2/3 , 0/1/2/3/4/5 , 0/7/10/15/20
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; And this ones will be the runs that we are going to extract the data. Put this file in same directory of the scripts.

4. Once we have this, we open the notebook `main.ipynb`, and complete the requiered parameters,
    - `data_type`, we use `='l0'` if we want to analyse the L0 or ipr runs (pixel analysis), and `='l1'` for the L1 data (cluster analysis)
    - `data_path`, the full directory name where we have the rate scans data (without final '/'), for example, `'/.../.../results'`
    - Other configuration is explained in the notebook, but is not necessary to change

5. Run all the notebook. Plots will be generated in a folder called `output` in same directory where you have the scripts

### Output:

You will get inside the `output` folder generated, a `.pdf` for each run, where you can find all the clusters/pixels fitted,

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/ratescans2.png" align="center" alt="drawing" width="400"/>

And the analysis of the 50% threshold with different plots, 

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/ratescans1.png" align="center" alt="drawing" width="400"/>

Also a `.pdf` separated with all the analysed data together for all the runs, tabulated in one plot

# Dark pedestal & pedestal with background: instructions to use

### Instructions to use

(Note): In order to extract the raw data drom the camera you need the `lstchain` environement.


 1. Copy `.result` files from CaCo to your computer or PIC, inside some folder

2. Copy the contents of this github folder `rate_scans` all in same directory, from where we are going to run the script

3. We need more information than what's inside the files, that we do not have in CaCo, this needs to be written by hand in a file called `extra_data.txt` organised like this, matching the date in the doc and the date of the `.result` file (example of file used in LST-2 in https://github.com/juanjq/LST_camera_validation/blob/main/rate_scans/extra_data.txt)

```
date            HV          DAC     neighbor      gain
y-m-d-h:min:s , HV/not_HV , 1/2/3 , 0/1/2/3/4/5 , 0/7/10/15/20
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; And this ones will be the runs that we are going to extract the data. Put this file in same directory of the scripts.

4. Once we have this, we open the notebook `main.ipynb`, and complete the requiered parameters,
    - `data_type`, we use `='l0'` if we want to analyse the L0 or ipr runs (pixel analysis), and `='l1'` for the L1 data (cluster analysis)
    - `data_path`, the full directory name where we have the rate scans data (without final '/'), for example, `'/.../.../results'`
    - Other configuration is explained in the notebook, but is not necessary to change

5. Run all the notebook. Plots will be generated in a folder called `output` in same directory where you have the scripts

### Output:

You will get inside the `output` folder generated, a `.pdf` for each run, where you can find all the clusters/pixels fitted,

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/ratescans2.png" align="center" alt="drawing" width="400"/>

And the analysis of the 50% threshold with different plots, 

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/ratescans1.png" align="center" alt="drawing" width="400"/>

Also a `.pdf` separated with all the analysed data together for all the runs, tabulated in one plot

# Pedestal recovery

---

# CrossTalk


---

# Time resolution

---


# Deadtime
Here I only did the script to extract the times data of a run, i.e. the time where the events happen, not any more information. That is the information we need to perform the Deadtime analysis

---


# Camera plots

## For plotting the waveforms for the pixels of determined runs
### Instructions:

1. Copy the notebook `waveforms_plots.ipynb` from this github folder: `plot_on_camera`

2. Change the parameters inside the notebook:

   * Run nummber
   * Events to extract (a small number recommended < 100)
   * Root folder with the location of the runs, with runs inside a folder with the name of the respective date.
   * Number of LST camera

3. Go to the respective block for only 1 event plot or multiple plots, and run the notebook

### Output:

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/waveforms.png" align="center" alt="drawing" width="400"/>

## For plotting an event on the camera
### Instructions:

1. Copy the notebook `camera_plots.ipynb` from this github folder: `plot_on_camera`

2. Change the parameters inside the notebook:

   * Run nummber
   * Events to extract (a small number recommended < 100)
   * Root folder with the location of the runs, with runs inside a folder with the name of the respective date.
   * Number of LST camera

3. Go to the respective block for only 1 event plot or multiple plots, and run the notebook

### Output:
The plot of the mean waveform values for respective event plotted on the camera

<img src="https://github.com/juanjq/LST_camera_validation/blob/main/graphs/camera_plot.png" align="center" alt="drawing" width="400"/>

## For getting an animation of some events

## Plot data from CaCo

## Geometry indexation


---

# Historical monitoring

---

# Other things done


### BP calibration scripts
---

