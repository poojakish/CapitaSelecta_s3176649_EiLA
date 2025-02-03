# Capita selecta code for testing FER models on the EiLA dataset

This repository contains code for testing FER models on the EiLA dataset. The code is written in Python and uses the PyTorch library. The code is divided into three parts: the first part is the code for extracting images from the videos based on the annotations and creating a dataset, the second part is the code for testing the FER models on the EiLA dataset(collected data), and the third part is to fine-tune the worst performing models.

## Extraction of images from videos

The code for extracting images from the videos is in the `Data_extraction` folder. You should run the files in the following order:

- The first step is to save the videos into the `Data_extraction/videos` folder.
- `Data_Extraction_main.ipynb`: This file extracts images from the videos based on the annotations and creates a folder with frames.
- `face_detection.ipynb`: This file detects faces in the images and saves the images with faces in the `Data_extraction/faces` folder.
- `Move_data_main.ipynb`: This file moves the images from the faces folder to the EiLA dataset folder.

The other two files are used to Analyse the data and to create data based on gender.

## Testing FER models on the EiLA dataset

The code for each type of model should be downloaded from the respective repository. The files for the specific models whose results are included in the paper is available in the `models_used` folder, this is the [link](https://drive.google.com/file/d/1KuhzvNb8umhLsEPi4qHdQCJHIKV_VTVK/view?usp=sharing) to the models_used zip file. Download and place the folder in this code along with other folders. You can use these models and test the performance on the EiLA dataset. 
The code for the models can be found below:
- Multi-Task Efficientnet model: [link](https://github.com/av-savchenko/face-emotion-recognition)
- Poster++ model: [link](https://github.com/talented-q/poster_v2)
- DDAMFN model: [link](https://github.com/SainingZhang/DDAMFN/tree/main)

Do download the code from the above links and create separate enviroments for each model. Then use the dataset created from the previous section to test the models. The `Evaluation` folder contains the modified code to evaluate the models on the EiLA dataset.

## Fine-tuning the worst-performing models

To fine-tune the models that performed the worst on the EiLA dataset, you can use the code in the `Fine_tuning` folder, and place these files into the respective environment. To train the model the extracted dataset is split into training, validation, and testing folders with an approx. ratio of 70:20:10. The code to split the data is available in `Data_extraction/Move_data_main.ipynb` file.
The poster++ model trained on the RAF-DB dataset and multi-task efficientnet-B2 models were the worst-performing models. So, they were selected to fine-tune on EiLA dataset. This ' Fine-tuning` folder contains the code for fine-tuning the models on the EiLA dataset.
The Fine-tuned models are also available in the `models_used` folder.
