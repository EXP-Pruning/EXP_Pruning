# EXP_Pruning
EXP way : Complete pruning using the expectation scaling factor

## Running Code

In this code, you can run our models on CIFAR-10 and ImageNet dataset. The code has been tested by Python 3.6, Pytorch 1.6 and CUDA 10.2 on Windows 10.

## parser
```shell
/data_dir/ : Dataset storage address
/dataset/ ： dataset - CIFAR10 or Imagenet
/lr/ ： initial learning rate
/lr_decay_step/ ： learning rate decay step
/resume/ ： load the model from the specified checkpoint
/resume_mask/ ： After the program is interrupted, the task file can be used to continue running
/job_dir/ ： The directory where the summaries will be stored
/epochs/ ： The num of epochs to fine-tune
/start_cov/ ： The num of conv to start prune
/compress_rate/ ： compress rate of each conv
/arch/ ： The architecture to prune
/pruning_way/ ： The chosen pruning method,A:bn priority pruning ; B:Full-layer redundant pruning
```

## Model Training

For the ease of reproducibility. we provide some of the experimental results and the corresponding pruned rate of every layer as belows:

##### 1. VGG-16

| Flops         | Accuracy      |Pre-training models|compress_rate        |
|---------------|---------------|-------------------|---------------------|
| 108.61M(65.3%)| 92.34%        |                   |
|---------------|---------------|-------------------|
| 108.61M(65.3%)| 92.34%        |                   |


```shell
--arch vgg_16_bn \
--compress_rate [0.95]+[0.5]*6+[0.9]*4+[0.8]*2 \
```
[VGG16](https://share.weiyun.com/6Ruys9dc)
