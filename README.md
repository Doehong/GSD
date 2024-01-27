# GSD
# HOWTO

The dependence versions that the code is tested:

| Dependence 	| Version     	|
|------------	|-------------	|
| g++        	| 11.4.0       	|
| cmake      	| 3.22.1      	|
| gflags     	| 2.1.2-3     	|
| openmp     	| 3.7.0-3     	|
| SWIG      	| 4.0.2       	|

## Preprocessing for C++ code 
Create an interface shared by C++ code and Python code
```bash
cd sampler
./compile.sh
```
### Start with conda for python part
```bash
conda create -n your_env_name python=3.8.16
```
Install dependencies by
```bash
pip install -r requirements.txt
```

### Run 
```bash
python main.py --dataname cora --gpu 0  --sample 4 --input_droprate 0.5 --hidden_droprate 0.5 --dropnode_rate 0.5 --hid_dim 32 --early_stopping 100 --lr 1e-2  --epochs 2000
python main.py --dataname citeseer --gpu 0  --sample 2 --input_droprate 0.0 --hidden_droprate 0.2 --dropnode_rate 0.5 --hid_dim 128 --early_stopping 100 --lr 1e-2  --epochs 2000
python main.py --dataname pubmed --gpu 0  --sample 4 --input_droprate 0.6 --hidden_droprate 0.8 --dropnode_rate 0.5 --hid_dim 16 --early_stopping 200 --lr 0.2 --epochs 2000 --use_bn
```


## Acknowledgement

The implementation of randomized singular value decomposition is by [redsvd](https://code.google.com/p/redsvd/) and [HPCA](https://github.com/idiap/hpca).
