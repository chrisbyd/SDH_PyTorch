# Supervised Discrete Hashing

## REQUIREMENTS
1. pytorch
2. loguru

`pip install -r requirements.txt`

## DATASET
1. [CIFAR10-gist](https://pan.baidu.com/s/1qE9KiAOTNs5ORn_WoDDwUg) Password: umb6

## USAGE
```
usage: run.py [-h] [--dataset DATASET] [--root ROOT]
              [--code-length CODE_LENGTH] [--max-iter MAX_ITER]
              [--num-anchor NUM_ANCHOR] [--num-train NUM_TRAIN]
              [--num-query NUM_QUERY] [--topk TOPK] [--gpu GPU] [--seed SEED]
              [--evaluate-interval EVALUATE_INTERVAL] [--lamda LAMDA]
              [--nu NU] [--sigma SIGMA]

SDH_PyTorch

optional arguments:
  -h, --help            show this help message and exit
  --dataset DATASET     Dataset name.
  --root ROOT           Path of dataset
  --code-length CODE_LENGTH
                        Binary hash code length.(default:
                        12,16,24,32,48,64,128)
  --max-iter MAX_ITER   Number of iterations.(default: 5)
  --num-anchor NUM_ANCHOR
                        Number of anchor.(default: 1000)
  --num-train NUM_TRAIN
                        Number of training data points.(default: 5000)
  --num-query NUM_QUERY
                        Number of query data points.(default: 1000)
  --topk TOPK           Calculate map of top k.(default: all)
  --gpu GPU             Using gpu.(default: False)
  --seed SEED           Random seed.(default: 3367)
  --evaluate-interval EVALUATE_INTERVAL
                        Evaluation interval.(default: 1)
  --lamda LAMDA         Hyper-parameter.(default: 1)
  --nu NU               Hyper-parameter.(default: 1e-5)
  --sigma SIGMA         Hyper-parameter. 2e-3 for cifar-10-gist, 3e-4 for
                        others.
```

## EXPERIMENTS
       bits                   |   12   |   16   |   24   |   32   |   48   |   64   |   128  
        :-:                   |   :-:  |  :-:   |   :-:  |   :-:  |   :-:  |   :-:  |   :-:  
  cifar-10-gist@ALL           | 0.2919 | 0.3163 | 0.3397 | 0.3531 | 0.3734 | 0.3937 | 0.3972
  cifar-10-alexnet@ALL        | 0.5480 | 0.5703 | 0.6006 | 0.6367 | 0.6261 | 0.6355 | 0.6591
  nus-wide-tc21-alexnet@5000  | 0.7711 | 0.7687 | 0.7788 | 0.7893 | 0.7915 | 0.7997 | 0.8108
  imagenet-tc100-alexnet@1000 | 0.3193 | 0.3650 | 0.4266 | 0.4669 | 0.4973 | 0.5231 | 0.5551
