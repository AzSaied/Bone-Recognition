# Bone-Recognition

#This is my bone recognition project.
#I have downloaded 391 publicly available X-ray images from the internet. These are saved as .png files and constitute my training/validation data

#I have created a 167 dimentional vector with the name of every bone possible to see on an x-ray (ignoring right / left handedness), and labeled each x-ray image for every bone that is and is not present in the x-ray. This information is saved as a csv file.

#I have built a simple CNN with a view to being able to read an X-ray, and output the correct label of which bones are present on the x-ray. Even using data augmentation techniques, I have not been able to get this CNN to correctly label x-rays. This perhaps is unsprurising given there are 2^167 possibile configurations of bones, which is of the order of magniture of 10^50.

#As such, I built a simple CNN to act as a binary classifier for a given bone (eg. Humerus), and output a 0 if the bone is not present in the X-ray, and a 1 if it is. Before using data augmentation techniques, the binary classifier acheives ~75% accuracy. 


Getting started
---------------

1. Install dependencies
   ```bash
   pipenv install
   ```

2. Start jupyter
   ```bash
   pipenv run jupyter notebook
   ```

3. Download data into the `data` directory
   ```bash
   gsutil -m rsync -r gs://bone_rec_project/data data
   ```

Tips
----
Run tensorboard
```bash
pipenv run tensorboard --logdir=logs
```