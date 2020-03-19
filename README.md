# Microinfarct\_client
This is the clinet of microinfarcts. You can align the image and label the beads on your own laptop. Select the cloud folders for loading files and saveing files, then all the human labeled result will be uploaded to the cloud drive shared by the computation server.
## 1. Install
* 1. git clone https://github.com/SilasiLab/microinfarct_client.git
* 2. get the atlas reference files from google drive share link: https://drive.google.com/a/uottawa.ca/file/d/1gWY_0LZDIYWut7o2haSa0zM-XRKGQxO_/view?usp=sharing
* 3. unzip it, copy all the contents(individual files rather than the folder) in the folder into the `atlas_refernece` folder.
* 4. install Anaconda on your computer.
* 5. `cd microinfarct_client`
* 6. `conda env create -f req/environment.yml`
* 7. `cd src`
* 8. `conda activate microclient`
* 9. `python main.py`
## 2. Preparatory phase
  * 1. For the input raw data, the input folder directory structure should be: `[Your folder containing all the brains]/[brain id](individual brain)/raw/[images_b.jpg]`. Images should all have a postfix `b` (`imageid_b`, e.g.) which indicates color channel blue.
  * 2. You will need a folder to save the result as also. Feel free to create your own folders.
  * After downloading as well as compiling ANTs, you should find the dirctory of `antsRegistrationSyNQuick.sh` under ANTs `Scripts` folder. For an instance, it is `/home/username/ANTs/Scripts/antsRegistrationSyNQuick.sh`. As for the folder containing `antsRegistrationSyNQuick.sh`, that is `/home/username/ANTs/Scripts/` which will be used as the parameter `--ant` of the whole project. Here we leave it as [Script folder] for short and for future use.
  
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
