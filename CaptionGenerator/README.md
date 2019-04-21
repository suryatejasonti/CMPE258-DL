# README #

This README would normally document whatever steps are necessary to get your application up and running.

### Flickr 8r dataset ###

Please download the image dataset and description for training here:  
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_Dataset.zip  
https://github.com/jbrownlee/Datasets/releases/download/Flickr8k/Flickr8k_text.zip  

The dataset is up to 1GB, so we only keep the copy of it on the local machine. Please do not push the dataset to the remote repository. I have added the dataset to .gitignore to prevent accidentially push.
Unzip Flickr8k_Dataset.zip into the folder named Flicker8k_Dataset. Unzip Flickr8k_text.zip into the folder named Flickr8k_text. Put these 2 folders inside CaptionGenerator.

> (tf) thy@ironman:~/workspace/cmpe258-teamproject/CaptionGenerator$ ls  
> CaptionGenerator_Mid-reviewPresentation_Demo.ipynb  Flicker8k_Dataset  
> encoded_train_images_vgg16.p                        Flickr8k_text  

### Conda - environment set up ###

I highly recommend you to set up virtual environment for this project, that will help you keep the environment clean and not conflicted with other packages required in other projects.   
Tutorial: https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html   
For example: I need to create a new virtual env named cmpe_258, and I will install the required packages for the project:
~~~~ 
conda create -n cmpe258_env python=3.6.8
conda activate cmpe258_env
conda install pandas matplotlib jupyter notebook scipy scikit-learn nb_conda nltk spyder pillow nltk glob2
conda install -c conda-forge tensorflow keras
~~~~
You can deactivate the current virtual env by:
~~~~
source deactivate
~~~~
Rember to activate your virtual env before open jupyter notebook:
~~~~
source activate cmpe258_env
jupyter notebook
~~~~
Some other notices:    
- Tensorlow for CPU might not be installed succesfully with python 3.7. So make sure you use python 3.6.8 (that's why we need virtual env, in case you use python 3.7 for other projects)    
- I pushed my packages list in the requirements.txt. But that one has specified packages for GPU (like tensorflow-gpu), so please disregard that.    
- We might need to install more packages on the go, make sure you let the team know which packages are required for your work    
- Try to use conda instead of pip, I know some packages installed by pip might be outdated when working with tensorflow    

### Image Encoder ###
I have finished extracting features from image training set using VGG16 (pre-trained model). After this step, each image can be presented by a vector of 2048 dimensions. This step requires a lot of computation, there's no need to run it all over again. So I dump the result to a file named encoded_train_images_vgg16.p.
You can try to run the function extract_features_vgg16 in the notebook to see how it works. But next time you can ignore it unless you need to extract features for other image datasets.   

