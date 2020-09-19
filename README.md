# spade-nir2rgb
This is an implementation of Near IfraRed image to RGB image translation using SPADE and gray scale image approximated self- reconstruction.
Near InfraRed (NIR) image is robust to ambient light and have clear textures. we propose
a two source conditioned RGB image generative model for fusing NIR image textures and
low light RGB image colors. This method solve the training objective contradiction exists in the previously proposed method [ACGAN].
We address this problem by using a single directional two branches architecture which completely separate the color and texture features.
The proposed image domain translation model consists of two VAEs (texture encoder and color encoder) and a Spatially Adaptive Denormalization (SPADE) generator.

**Note**: The current software works well with PyTorch 1.4.
This application is inspired of [NVlabs/SPADE] https://github.com/NVlabs/SPADE.

If you use this code for your research, please cite:
...



## Prerequisites
- Linux or macOS
- Python 3.6+
- CPU or NVIDIA GPU + CUDA CuDNN

## Getting Started
### Installation

- Clone this repo:
```bash
cd pytorch-spade-fusion
```

- Install PyTorch 1.4+ and torchvision from http://pytorch.org and other dependencies (e.g., [dominate](https://github.com/Knio/dominate)). You can install all the dependencies by
```bash
pip install -r requirements.txt
```

### NIR-RGB fusion train/test
- - Download a paired NIR-RGB dataset, and select the dataset model (fusion), the aligned data should be stored dividedly in sub-folder of "nir", "dark" and "rgb"

- Train a model:
```bash
python train.py --dataroot ./datasets/fusion --name SPADE_fusion --model fusion
```

- Test the model:
```bash
python test.py --dataroot ./datasets/ftest --name ACGAN_colorization --model fusion
```
The test results will be saved to a html file here: `./results/SAPDE_fusion/test_latest/index.html`.

## Citation
If you use this code for your research, please cite our papers.
```




## Related Projects
**[CycleGAN-Torch](https://github.com/junyanz/CycleGAN) |
[Cycle GAN] https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix |
[BicycleGAN](https://github.com/junyanz/BicycleGAN)**


## Acknowledgments
Our code is inspired by [NVlabs/SPADE] https://github.com/NVlabs/SPADE
