# NER_SCIBERT_PIPELINE
 
For Executing the pipeliline script main.py that contains all the steps involved in our NER process,simply follow these steps-

# 1. Cloning Github repo contaiinng scripts and datasets
!git clone https://github.com/abhi0618/NER_SCIBERT_PIPELINE.git 

# 2. Installing Required Libraries
%cd /content/drive/MyDrive/NER_SCIBERT_PIPELINE \
!pip install -q -r requirements.txt

*If you are using your local environment , change the cd path to your path where the repo is cloned. 

#3. Running the main pipeline script main.py

!python main.py --input_dir "data/data.csv" \
--model_name_or_path "allenai/scibert_scivocab_uncased" \
--pre_train True \
--pre_train_block_size 128 \
--pre_train_epochs 10 \
--pre_train_batch_size 64 \
--pre_train_save_steps 100 \
--train_epochs 10 \
--train_batch_size 16


The main.py script that includes the execution steps, from the intial data-preprocessing(1) , vocabulary pretraining(2), NER FInetuning(3), and evaluation(4) of the model inferences on the training dataset of custom managment constructs.The data-preproccing script is invoked in the vocabulary pretraining part of the script that pretrains the model on our vocabulary dataset. The main.py script contains the input arguments for input data, pretraining ,traininig, as well as evaluation of dataset.\

The model can also be run on the existing vocabulary pretraining of the model.To do it without the pretraining or Language modelling of the model on our dataset, and continue with existing vocabulary pretraining , simple pass the argument --pre_train False  , instead of the --pre_train True .This is recommended to avoid use of an intense heavy resource enviroment, espicially in systems with low GPU memory, like local system environment.

