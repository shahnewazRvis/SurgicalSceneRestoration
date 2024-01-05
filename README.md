
# Currently Updating the repository 
# SurgicalSceneRestoration
Dataset for "One step surgical scene restoration for robot assisted minimally invasive surgery" method applied on Knee Arthroscopy. The model learns image restoration methods namely denoise, deblur,and color corrections.
For other minimally invasive surgical (MIS)  procedures or endoscopic images e.g. wireless capsule endoscopy, The model can be pre-trained on the following published dataset and can be used  
fine-tuned on small endoscopic images.

Directory Structure

 dataset/image: Real world endoscopic surgical images. [Updating]
 
 dataset/synthetic_gt: Synthetic rendered surgical images.
 
 dataset/clean: Clean restored denoised deblurred and color corrected surgical images.

![09-14-11-45-55_00555_L](https://github.com/shahnewazRvis/SurgicalSceneRestoration/assets/92858748/31eff9fc-a452-4377-b0b5-b628a2ce34a1) ![09-14-11-45-55_00555_L](https://github.com/shahnewazRvis/SurgicalSceneRestoration/assets/92858748/fc9ec4df-c306-4c63-999d-6dda72a9f4ee)

       Real world image                             Restored images




![00_025_24-10-2019_1_2019-10-24-13-01-04_00484_R](https://github.com/shahnewazRvis/SurgicalSceneRestoration/assets/92858748/d060fa24-da25-4584-bf14-9c174fba9bf4) ![1](https://github.com/shahnewazRvis/SurgicalSceneRestoration/assets/92858748/95b5474d-2564-42f6-bde5-e0c29878315d)





# image resize function

       import os
       import sys
       import numpy as np
       import cv2
       import csv
       import os


       rd_dir='./PATH_TO_READ_DIRECTORY/'
       save_dir='./PATH_TO_SAVE_DIRECTORY/'

       def make_dir_(dir_name):
           if not os.path.exists(dir_name):
               os.makedirs(dir_name)
               return True
           else:
               return False

       def resize_images():
           file_list= os.listdir(rd_dir)
           for c in range(len(file_list)):
               name=file_list[c]
               I = cv2.imread(rd_dir+name) # read the image
               # resize either 256x256 or 384x384
               #image = cv2.resize(I , (256, 256))
               image = cv2.resize(I , (384, 384))
               cv2.imwrite(save_dir+name, image)



# Citation:
       Ali, Shahnewaz, Yaqub Jonmohamadi, Davide Fontanarosa, Ross Crawford, and Ajay K. Pandey. "One step surgical scene restoration for robot assisted minimally invasive surgery." Scientific Reports 13, no. 1 (2023): 3127.
# Doi
       https://doi.org/10.1038/s41598-022-26647-4
