# Fast and Memory-Efficient Compact Bilinear Pooling
## README
For a better user experience, we recommend you to directly use github repository
github [link](https://github.com/cvpr2021kp2/cvpr2021kp2)

## Prepare datasets
### Dataset
CUB [link](https://www.dropbox.com/s/dsgngcy3fmamgm7/cub200.tar.gz?dl=0)

MIT [link](https://www.dropbox.com/s/n6ymftqk8alihpu/mit.tar.gz?dl=0)

DTD [link](https://www.dropbox.com/s/co5lq11axokwkcj/dtd.tar.gz?dl=0)

please unzip the downloaded datasets and then move them to data


## Training

Step 1. Fine-tune the fc layer only.

CUDA_VISIBLE_DEVICES=0,1 python ./src/bilinear_cnn_fc_cub.py --base_lr 1 --batch_size 64 --epochs 81 --weight_decay 1e-6
    
Step 2. Fine-tune all layers.

CUDA_VISIBLE_DEVICES=0,1 python ./src/bilinear_cnn_all_cub.py --base_lr 1e-2 --batch_size 32 --epochs 50 --weight_decay 1e-3 --model "vgg_16_epoch_81.pth"



## Run Script


You can also run the above three experiments by one script in background:

    CUB:
    nohup bash script_cub.sh &

    MIT:
    nohup bash script_mit.sh &

    DTD:
    nohup bash script_dtd.sh &
