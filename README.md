# LWDN
## Exploration of Lightweight Single Image Denoising with Transformers and Truly Fair Training (ICMR 2023, ACM International Conference on Multimedia Retrieval)

Haram Choi<sup>*</sup>, Cheolwoong Na, Jinseop Kim, and Jihoon Yang<sup>+</sup>

<sup>*</sup>: This work has been done during my 3rd semester of Master Course in Sogang University.

<sup>+</sup>: Corresponding author.

[ArXiv](https://arxiv.org/abs/2304.01805) | [Visual Results](https://1drv.ms/f/s!AoUesdU_BVZritcF9FL05jkHOAkqCA?e=Ql685q)

- Proposes seven lightweight image denosing (LWDN) Transformer baselines.
  - Three come from lightweight super-resolution and four are downsized versions of the current best large denoising models.
  - Lightweight Super-Resolution Models: [SwinIR-light](https://arxiv.org/abs/2108.10257) (ICCVW21), [ELAN-light](https://arxiv.org/abs/2203.06697) (ECCV22), [NGswin](https://arxiv.org/abs/2211.11436) (CVPR23)
  - Large Denosing Models: [Restormer](https://arxiv.org/abs/2111.09881) (CVPR22), [Uformer](https://arxiv.org/abs/2106.03106) (CVPR22), [CAT](https://openreview.net/forum?id=wQ2QNNP8GtM) (NeurIPS22), [ART](https://arxiv.org/abs/2210.01427) (ICLR23)
- Trains and compares the baselines in a truly fair manner.
  - Identical randomly cropped patches are selectd every iteration in each epoch.
  - Records and provides cropped areas (starting point of height (top) and width (left) to be cropped) and random data augmentation (horizontal flip and angle of rotation)
  - Robust to random seed in terms of reproducibility.
- Emperically analyzes various aspects of our baselines.
  - _Hierarchical Structure_.
  - _Spatial vs. Channel Self-Attention_.
  - _Excessive Weight Sharing_.
  - _Still Useful CNN_.
  
### News
**May 03, 2023:** Visual results shared

**Apr 04, 2023:** Codes released publicly (will be re-available soon due to several issues.)

**Apr 02, 2023:** Our paper accepted at ICMR 2023

### Visual Results

<details>
<summary>Comparison of Our Lightweight Baselines (Please Click)</summary>

![001denoising_results](https://user-images.githubusercontent.com/69415453/229990361-53e7d0e4-969b-4539-8c91-214f61a3ceb2.png)

</details>

<details>
<summary>Comparison with Large Models (Please Click)</summary>

![002comp_with_large](https://user-images.githubusercontent.com/69415453/229990365-b7eae8f8-976c-4fca-a866-4c3cf26a922d.png)

</details>

### Main Results

<details>
<summary>Comparison of Our Lightweight Baselines for Color Gaussian Blind Denoising (Please Click)</summary>

![003color_denoising](https://user-images.githubusercontent.com/69415453/229990368-a77730fb-8ba7-493a-bdf8-0754f6eb46d4.png)

</details>

<details>
<summary>Comparison of Our Lightweight Baselines for Grayscale Gaussian Blind Denoising (Please Click)</summary>

![004gray_denoising](https://user-images.githubusercontent.com/69415453/229990371-93aee4d0-165f-489d-9170-65f10667fd60.png)

</details>

## Requirements

### Libraries
* Python 3.6.9
* PyTorch >= 1.10.1+cu102
* timm >= 0.6.1
* torchvision >= 0.11.2+cu102
* einops 0.3.0
* numpy 1.19.5
* OpenCV 4.6.0
* tqdm 4.61.2

### Datasets (names and path)

```
TBD
```

## Testing with pre-trained models
### You can get the results in the Tables of our paper.

If you have multi gpus that can be used for Distributed Data Parallel (DDP), follow the commands below.

Please properly edit the first five arguments to work on your devices.
```
TBD
```

## Training from scratch: x2 task
### with DDP
- NOTE: argument ```batch_size``` means the size of mini-batch assigned per gpu
```
TBD
```

## Training by warm-start: x3, x4 tasks
### with DDP
```
TBD
```

### Citation
```
(preferred)
@inproceedings{choi2023exploration,
  title={Exploration of Lightweight Single Image Denoising with Transformers and Truly Fair Training},
  author={Choi, Haram and Na, Cheolwoong and Kim, Jinseop and Yang, Jihoon},
  booktitle={Proceedings of the 2023 International Conference on Multimedia Retrieval},
  year={2023, To Appear}
}

@article{choi2023exploration,
  title={Exploration of Lightweight Single Image Denoising with Transformers and Truly Fair Training},
  author={Choi, Haram and Na, Cheolwoong and Kim, Jinseop and Yang, Jihoon},
  journal={arXiv preprint arXiv:2304.01805},
  year={2023}
}
```

## Credits
#### SwinIR: https://arxiv.org/abs/2108.10257
#### Restormer: https://arxiv.org/abs/2111.09881
#### Uformer: https://arxiv.org/abs/2106.03106
#### ELAN: https://arxiv.org/abs/2203.06697
#### CAT: https://openreview.net/forum?id=wQ2QNNP8GtM
#### ART: https://arxiv.org/abs/2210.01427
#### NGswin: https://arxiv.org/abs/2211.11436
