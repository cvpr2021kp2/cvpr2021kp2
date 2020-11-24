    Python3.6 with Numpy supported
    PyTorch-1.4.0 



LAYOUT
    ./data/                 # Datasets
    ./src/                  # Source code

DATA

    CUB: https://www.dropbox.com/s/dsgngcy3fmamgm7/cub200.tar.gz?dl=0
    MIT: https://www.dropbox.com/s/n6ymftqk8alihpu/mit.tar.gz?dl=0
    DTD: https://www.dropbox.com/s/co5lq11axokwkcj/dtd.tar.gz?dl=0 
    pleae download each data file through above links, zip them and move the folders into the ./data/ 


USAGE


    Step 1. Fine-tune the fc layer only.
    CUDA_VISIBLE_DEVICES=0,1 python ./src/bilinear_cnn_fc_cub.py --base_lr 1 --batch_size 64 --epochs 81 --weight_decay 1e-6 
    Step 2. Fine-tune all layers.
    CUDA_VISIBLE_DEVICES=0,1 python ./src/bilinear_cnn_all_cub.py --base_lr 1e-2 --batch_size 32 --epochs 50 --weight_decay 1e-3 --model "vgg_16_epoch_81.pth"
    
    You can also run the above three experiments by one script in background: 
    CUB:
    nohup bash script_cub.sh &

    MIT:
    nohup bash script_mit.sh &

    DTD:
    nohup bash script_dtd.sh &





