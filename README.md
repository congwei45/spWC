
**Self-paced Weight Consolidation for Continual Learning**<br>
Wei Cong<sup>1</sup>, Yang Cong<sup>1</sup>, Gan Sun<sup>1</sup>, Yuyang Liu<sup>1</sup>, Jiahua Dong<sup>1</sup><br>
<sup>1</sup> <sub>Shenyang Institute of Automation, Chinese Academy of Sciences</sub><br />



## Dataset Prepare
- PASCVAL VOC 2012  
    ```sh data/download_voc.sh```



## Environment
1. ```conda install --yes --file requirements.txt```
2. Install [inplace-abn](https://github.com/mapillary/inplace_abn)



## Training
1. Dowload pretrained model from [ResNet-101_iabn](https://github.com/arthurdouillard/CVPR2021_PLOP/releases/download/v1.0/resnet101_iabn_sync.pth.tar) to ```pretrained/```
2. We have prepared some training scripts in ```scripts/```. You can train the model by
```
sh scripts/voc/rcil_10-1-overlap.sh
```

## Inference
You can simply modify the bash file by adding ```--test```, like
```
CUDA_VISIBLE_DEVICES=${GPU} python3 -m torch.distributed.launch --master_port ${PORT} --nproc_per_node=${NB_GPU} run.py --data xxx ... --test
```