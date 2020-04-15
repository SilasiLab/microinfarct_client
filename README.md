# Microinfarct\_client
This is the clinet of microinfarcts. You can align the image and label the beads on your own laptop. Select the cloud folders for loading files and saveing files, then all the human labeled result will be uploaded to the cloud drive shared by the computation server.
## 1. Install
* 1. `git clone https://github.com/SilasiLab/microinfarct_client.git`
* 2. get the atlas reference files from google drive share link: https://drive.google.com/a/uottawa.ca/file/d/1gWY_0LZDIYWut7o2haSa0zM-XRKGQxO_/view?usp=sharing
* 3. unzip it, copy all the contents(individual files rather than the folder) in the folder into the `atlas_refernece` folder.
* 4. install Anaconda on your computer.
* 5. `cd microinfarct_client`
* 6. `conda create -n micro python=3.6.8 Anaconda`
* 7. `conda activate micro`
* 8. `conda install opencv=3.4.1`
* 7. `cd src`
* 8. `conda activate microclient`
* 9. `python main.py`
## 2. Preparatory phase
  * 1. For the input raw data, the input folder directory structure should be: `[Your folder containing all the brains]/[brain id](individual brain)/raw/[images_b.jpg]`. Images should all have a postfix `b` (`imageid_b`, e.g.) which indicates color channel blue.
  * 2. You will need a folder to save the result as also. Feel free to create your own folders.
  * 3. Note that You can absolutely work locally, but you need to copy the labled result to the computational server afterwards. You can also work on the cloud drive shared with the server too. Then you need a virtua cloud directory(Google file stream or Rclone).
  
## 3. User guide
  * 1. `cd [your directory]/microinfarcts/src`
  * 2. `python main.py`
  * 3. 
       ![Gui](/pics/microinfarctsGUI.png)
  * 4. Check `Auto Segmentation` will perform a Discrete Fourier Transform to find the microinfarcts(bright circle area) in brain scans. You can also manually segement the bead by selecting `Manual beads labeling`. Note: By running any one in the two methods, a csv file will be cached on the local disk. Once the file is cached, the programme will skip the step of segmentation.  
  * 5. Check `Show the result`, the script will transform the bead location mask and project it on the brain scan. Showing the result and generating the summary files have some conflicts, so they cannot be run at the same time.
  * 6. Check `Write a summary`, a summary csv, a structual tree txt, as well as a structual tree image will be generated under `[result folder]/[brain id]/`.
  * 7. Select the brain folder you would like to analyse from the left list, then move it to the analysing list on the right side by clicking the button `>>`.
  * 8. Click on the analyse button.
  * 9. A manual alignment is required at the begining. You need firstly click the common point shared by the two neigbour images. Go the last section containing the anterior commissure, draw the line from top to bottom in the right middle of the brain. Save it, then draw the line across the anterior commissure. Press Q to save all and continue the processing step.
