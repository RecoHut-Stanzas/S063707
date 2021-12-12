# Learning Robust Recommender from Noisy Implicit Feedback

## Usage

### Training
#### T_CE
```
python main.py --dataset=$1 --model=$2 --drop_rate=$3 --num_gradual=$4 --gpu=$5
```
or use run.sh
```
sh run.sh dataset model drop_rate num_gradual gpu_id
```
The output will be in the ./log/xxx folder.

#### R_CE
```
sh run.sh dataset model alpha gpu_id
```
### Inference
We provide the code to inference based on the well-trained model parameters.
```
python inference.py --dataset=$1 --model=$2 --drop_rate=$3 --num_gradual=$4 --gpu=$5
```
### Examples
1. Train GMF by T_CE on Yelp:
```
python main.py --dataset=yelp --model=GMF --drop_rate=0.1 --num_gradual=30000 --gpu=0
```
2. Train NeuMF by R_CE on Amazon_book
```
python main.py --dataset=amazon_book --model=NeuMF-end --alpha=_0.25 --gpu=0
```
We release all training logs in ./log folder. The hyperparameter settings can be found in the log file. 
The well-trained parameter files are too big to upload to Github. I will upload to drives later and share it here.

## Project structure
```
.
├── [252K]  images
│   ├── [137K]  img1.png
│   ├── [ 87K]  img2.png
│   └── [ 24K]  process_flow.svg
├── [ 57K]  nbs
│   └── [ 53K]  P254192_Training_GMF_with_Truncated_and_Reweighted_Denoising_Losses_on_Yelp_Dataset.ipynb
├── [ 78K]  R_CE
│   ├── [4.1K]  data_utils.py
│   ├── [3.2K]  evaluate.py
│   ├── [2.2K]  inference.py
│   ├── [ 50K]  log
│   │   ├── [ 25K]  adressa
│   │   │   ├── [ 11K]  GMF_0.2.log
│   │   │   └── [ 11K]  NeuMF-end_0.25.log
│   │   ├── [ 12K]  amazon_book
│   │   │   ├── [3.9K]  GMF_0.3.log
│   │   │   └── [4.0K]  NeuMF-end_0.25.log
│   │   └── [9.4K]  yelp
│   │       ├── [2.7K]  GMF_0.2.log
│   │       └── [2.7K]  NeuMF-end_0.2.log
│   ├── [ 420]  loss.py
│   ├── [6.1K]  main.py
│   ├── [3.7K]  model.py
│   ├── [4.0K]  models
│   └── [  94]  run.sh
├── [1019]  README.md
├── [ 12K]  reports
│   └── [7.7K]  S063707_report.ipynb
└── [113K]  T_CE
    ├── [4.1K]  data_utils.py
    ├── [3.2K]  evaluate.py
    ├── [2.1K]  inference.py
    ├── [ 85K]  log
    │   ├── [ 46K]  adressa
    │   │   ├── [ 11K]  GMF_0.05-30000.log
    │   │   ├── [ 10K]  GMF_0-0.log
    │   │   ├── [ 11K]  NeuMF-end_0-0.log
    │   │   └── [ 11K]  NeuMF-end_0.2-1000.log
    │   ├── [ 20K]  amazon_book
    │   │   ├── [4.0K]  GMF_0-0.log
    │   │   ├── [4.0K]  GMF_0.1-30000.log
    │   │   ├── [4.0K]  NeuMF-end_0-0.log
    │   │   └── [4.0K]  NeuMF-end_0.2-30000.log
    │   └── [ 15K]  yelp
    │       ├── [2.7K]  GMF_0-0.log
    │       ├── [2.7K]  GMF_0.1-30000.log
    │       ├── [2.7K]  NeuMF-end_0-0.log
    │       └── [2.7K]  NeuMF-end_0.2-30000.log
    ├── [ 611]  loss.py
    ├── [6.7K]  main.py
    ├── [3.7K]  model.py
    ├── [4.0K]  models
    └── [ 118]  run.sh

 518K used in 15 directories, 38 files
```