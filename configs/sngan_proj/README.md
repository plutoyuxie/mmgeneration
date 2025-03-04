# SNGAN

> [Spectral Normalization for Generative Adversarial Networks](https://openreview.net/forum?id=B1QRgziT-)

## Abstract

One of the challenges in the study of generative adversarial networks is the instability of its training. In this paper, we propose a novel weight normalization technique called spectral normalization to stabilize the training of the discriminator. Our new normalization technique is computationally light and easy to incorporate into existing implementations. We tested the efficacy of spectral normalization on CIFAR10, STL-10, and ILSVRC2012 dataset, and we experimentally confirmed that spectrally normalized GANs (SN-GANs) is capable of generating images of better or equal quality relative to the previous training stabilization techniques.

<!-- [IMAGE] -->

<div align=center>
<img src="https://user-images.githubusercontent.com/28132635/143154496-6a03def4-4507-4d80-a948-89a5b747d916.png"/>
</div>

## Results and models

<div align="center">
  <b> Results from our SNGAN-PROJ trained in CIFAR10 and ImageNet</b>
  <br/>
  <img src="https://user-images.githubusercontent.com/28132635/125151484-14220b80-e179-11eb-81f7-9391ccaeb841.png" width="400"/> &nbsp;&nbsp;
  <img src="https://user-images.githubusercontent.com/28132635/127621152-7b7a0f2c-c743-485a-bf2e-2beca849a6e6.png" width="400"/>
</div>


|                  Models                   | Dataset  | Inplace ReLU | disc_step | Total Iters\* |  Iter  |   IS    |   FID   |                                                                             Config                                                                             |                                                                                 Download                                                                                  |                                                                                    Log                                                                                     |
| :---------------------------------------: | :------: | :----------: | :-------: | :-----------: | :----: | :-----: | :-----: | :------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|  SNGAN_Proj-32x32-woInplaceReLU Best IS   | CIFAR10  |     w/o      |     5     |    500000     | 400000 | 9.6919  | 9.8203  |        [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_32_woReLUinplace_lr-2e-4_ndisc5_cifar10_b64x1.py)         |           [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_woReLUinplace_is-iter400000_20210709_163823-902ce1ae.pth)            |           [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_woReLUinplace_20210624_065306_fid-ba0862a0_is-902ce1ae.json)           |
|  SNGAN_Proj-32x32-woInplaceReLU Best FID  | CIFAR10  |     w/o      |     5     |    500000     | 490000 | 9.5659  | 8.1158  |        [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_32_woReLUinplace_lr-2e-4_ndisc5_cifar10_b64x1.py)         |           [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_woReLUinplace_fid-iter490000_20210709_163329-ba0862a0.pth)           |           [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_woReLUinplace_20210624_065306_fid-ba0862a0_is-902ce1ae.json)           |
|   SNGAN_Proj-32x32-wInplaceReLU Best IS   | CIFAR10  |      w       |     5     |    500000     | 490000 | 9.5564  | 8.3462  |         [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_32_wReLUinplace_lr-2e-4_ndisc5_cifar10_b64x1.py)         |            [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_wReLUinplace_is-iter490000_20210709_202230-cd863c74.pth)            |           [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_wReLUinplace_20210624_065306_fid-ba0862a0_is-902ce1ae.json)            |
|  SNGAN_Proj-32x32-wInplaceReLU Best FID   | CIFAR10  |      w       |     5     |    500000     | 490000 | 9.5564  | 8.3462  |         [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_32_wReLUinplace_lr-2e-4_ndisc5_cifar10_b64x1.py)         |           [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4-b64x1_wReLUinplace_fid-iter490000_20210709_203038-191b2648.pth)            |           [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_cifar10_32_lr-2e-4_b64x1_wReLUinplace_20210624_065306_fid-ba0862a0_is-902ce1ae.json)            |
| SNGAN_Proj-128x128-woInplaceReLU Best IS  | ImageNet |     w/o      |     5     |    1000000    | 952000 | 30.0651 | 33.4682 | [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_128_woReLUinplace_Glr-2e-4_Dlr-5e-5_ndisc5_imagenet1k_b128x2.py) | [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_woReLUinplace_is-iter952000_20210730_132027-9c884a21.pth)  | [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_woReLUinplace_20210730_131424_fid-061bf803_is-9c884a21.json) |
| SNGAN_Proj-128x128-woInplaceReLU Best FID | ImageNet |     w/o      |     5     |    1000000    | 989000 | 29.5779 | 32.6193 | [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_128_woReLUinplace_Glr-2e-4_Dlr-5e-5_ndisc5_imagenet1k_b128x2.py) | [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_woReLUinplace_fid-iter988000_20210730_131424-061bf803.pth) | [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_woReLUinplace_20210730_131424_fid-061bf803_is-9c884a21.json) |
|  SNGAN_Proj-128x128-wInplaceReLU Best IS  | ImageNet |      w       |     5     |    1000000    | 944000 | 28.1799 | 34.3383 | [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_128_wReLUinplace_Glr-2e-4_Dlr-5e-5_ndisc5_imagenet1k_b128x2.py)  |  [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_wReLUinplace_is-iter944000_20210730_132714-ca0ccd07.pth)  | [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_wReLUinplace_20210730_132401_fid-9a682411_is-ca0ccd07.json)  |
| SNGAN_Proj-128x128-wInplaceReLU Best FID  | ImageNet |      w       |     5     |    1000000    | 988000 | 27.7948 | 33.4821 | [config](https://github.com/open-mmlab/mmgeneration/tree/master/configs/sngan_proj/sngan_proj_128_wReLUinplace_Glr-2e-4_Dlr-5e-5_ndisc5_imagenet1k_b128x2.py)  | [ckpt](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_wReLUinplace_fid-iter988000_20210730_132401-9a682411.pth)  | [Log](https://download.openmmlab.com/mmgen/sngan_proj/sngan_proj_imagenet1k_128_Glr2e-4_Dlr5e-5_ndisc5_b128x2_wReLUinplace_20210730_132401_fid-9a682411_is-ca0ccd07.json)  |

'\*' Iteration counting rule in our implementation is different from others. If you want to align with other codebases, you can use the following conversion formula:
```
total_iters (biggan/pytorch studio gan) = our_total_iters / disc_step
```

We also provide converted pre-train models from [Pytorch-StudioGAN](https://github.com/POSTECH-CVLab/PyTorch-StudioGAN).
To be noted that, in Pytorch Studio GAN, **inplace ReLU** is used in generator and discriminator.

|            Models            | Dataset  | Inplace ReLU | disc_step | Total Iters | IS (Our Pipeline) | FID (Our Pipeline) | IS (StudioGAN) | FID (StudioGAN) |                                                    Config                                                    |                                                         Download                                                          |                              Original Download link                               |
| :--------------------------: | :------: | :----------: | :-------: | :---------: | :---------------: | :----------------: | :------------: | :-------------: | :----------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------: |
|  SAGAN_Proj-32x32 StudioGAN  | CIFAR10  |      w       |     5     |   100000    |       9.372       |      10.2011       |     8.677      |     13.248      |  [config](https://github.com/open-mmlab/mmgeneration/blob/master/configs/_base_/models/sngan_proj_32x32.py)  |  [model](https://download.openmmlab.com/mmgen/sngan_proj/sngan_cifar10_convert-studio-rgb_20210709_111346-2979202d.pth)   | [model](https://drive.google.com/drive/folders/16s5Cr-V-NlfLyy_uyXEkoNxLBt-8wYSM) |
| SAGAN_Proj-128x128 StudioGAN | ImageNet |      w       |     2     |   1000000   |      30.218       |      29.8199       |     32.247     |     26.792      | [config](https://github.com/open-mmlab/mmgeneration/blob/master/configs/_base_/models/sngan_proj_128x128.py) | [model](https://download.openmmlab.com/mmgen/sngan_proj/sngan_imagenet1k_convert-studio-rgb_20210709_111406-877b1130.pth) | [model](https://drive.google.com/drive/folders/1Ek2wAMlxpajL_M8aub4DKQ9B313K8XhS) |


* `Our Pipeline` denote results evaluated with our pipeline.
* `StudioGAN` denote results released by Pytorch-StudioGAN.

For IS metric, our implementation is different from PyTorch-Studio GAN in the following aspects:
1. We use [Tero's Inception](https://nvlabs-fi-cdn.nvidia.com/stylegan2-ada-pytorch/pretrained/metrics/inception-2015-12-05.pt) for feature extraction.
2. We use bicubic interpolation with PIL backend to resize image before feed them to Inception.

For FID evaluation, we follow the pipeline of [BigGAN](https://github.com/ajbrock/BigGAN-PyTorch/blob/98459431a5d618d644d54cd1e9fceb1e5045648d/calculate_inception_moments.py#L52), where the whole training set is adopted to extract inception statistics, and Pytorch Studio GAN uses 50000 randomly selected samples. Besides, we also use [Tero's Inception](https://nvlabs-fi-cdn.nvidia.com/stylegan2-ada-pytorch/pretrained/metrics/inception-2015-12-05.pt) for feature extraction.

You can download the preprocessed inception state by the following url: [CIFAR10](https://download.openmmlab.com/mmgen/evaluation/fid_inception_pkl/cifar10.pkl) and [ImageNet1k](https://download.openmmlab.com/mmgen/evaluation/fid_inception_pkl/imagenet.pkl).

You can use following commands to extract those inception states by yourself.
```
# For CIFAR10
python tools/utils/inception_stat.py --data-cfg configs/_base_/datasets/cifar10_inception_stat.py --pklname cifar10.pkl --no-shuffle --inception-style stylegan --num-samples -1 --subset train

# For ImageNet1k
python tools/utils/inception_stat.py --data-cfg configs/_base_/datasets/imagenet_128x128_inception_stat.py --pklname imagenet.pkl --no-shuffle --inception-style stylegan --num-samples -1 --subset train
```

## Citation

```latex
@inproceedings{miyato2018spectral,
  title={Spectral Normalization for Generative Adversarial Networks},
  author={Miyato, Takeru and Kataoka, Toshiki and Koyama, Masanori and Yoshida, Yuichi},
  booktitle={International Conference on Learning Representations},
  year={2018},
  url={https://openreview.net/forum?id=B1QRgziT-},
}
```
