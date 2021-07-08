# Semantic Segmentation on aerial (drone) images

You can use this repo to generate semantic segmentations on drone images. The model was trained using publicly available [Semantic Drone Dataset](http://dronedataset.icg.tugraz.at/). For training, I trained the model on HRNet using the amazing CSAIL Vision's [semantic segmentation pipeline](https://github.com/CSAILVision/semantic-segmentation-pytorch). <br>
I trained the model on Google Colab. If you want to train your own models on colab using this pipeline, please see the [train_on_colab.ipynb](train_on_colab.ipynb) notebook. Note that we will be saving all the checkpoints on Google drive, as the files are deleted everytime colab environment is reset. For longer trainings, don't save checkpoint for every epoch, as it can fill up your google drive quickly.

### Some Results on validation data
![result 1](./results/042.png) <br> <br>
![result 2](./results/057.png) <br> <br>
![result 3](./results/004.png) <br> <br>
![result 4](./results/028.png) <br> <br>
![result 5](./results/003.png) <br> <br>
![result 6](./results/005.png) <br> <br>
![result 7](./results/015.png)
 
 
### Usage:
You can use the trained model to get results on your custom images. <br>
Step 1: clone the CSAIL Vision's [semantic segmentation pipeline](https://github.com/CSAILVision/semantic-segmentation-pytorch). <br>
Step 2: Edit the HRNet config file in the cloned repo (config/ade20k-hrnetv2.yaml). Or use the [one in this repo](./config/aerial-sseg.yaml). <br>
Step 3: Update the checkpoint path in config file. Use the chekpoint present in the checkpoint folder. <br>
Step 4: Run the CSAIL Vision's test.py: python test.py --gpu 0 --cfg path-to-config-file --imgs path-to-images-directory
