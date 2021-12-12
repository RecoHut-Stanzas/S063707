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