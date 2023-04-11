# <p align=center>`CamoFormer: Masked Separable Attention for Camouflaged Object Detection`</p>

> **Authors:**
> [Bowen Yin](http://yinbowen-chn.github.io/),
> [Xuying Zhang](),
> [Qibin Hou](),
> [Bo-Yuan Sun](),
> [Deng-Ping Fan](), &
> [Luc Van Gool]().


This official repository contains the source code, prediction results, and evaluation toolbox of paper 'CamoFormer: Masked Separable Attention for Camouflaged Object Detection'. The technical report could be found at [arXiv](https://arxiv.org/abs/2212.06570). 
The whole benchmark results can be found at [One Drive](https://mailnankaieducn-my.sharepoint.com/:f:/g/personal/bowenyin_mail_nankai_edu_cn/EmB36EZb_fdMvWGgKx2EalgBuQnj8AFifyR-ip7Jtkfwqg?e=nu6DJz), [Baidu Netdisk](https://pan.baidu.com/s/1k5CxYzcgizzJ4sRdAxBNlA?pwd=srtf), or [Google Drive](https://drive.google.com/drive/folders/1gsCeYtS9cwsMpTHQzkx81n4jsRK4LYdf?usp=sharing).



<p align="center">
    <img src="figs/CamoFormer.png" width="600"  width="1200"/> <br />
    <em> 
    Figure 1: Overall architecture of our CamoFormer model. First, a pretrained Transformer-based backbone is utilized to extract multi-scale features of the input image. Then, the features from the last three stages are aggregated to generate the coarse prediction. Next, the
progressive refinement decoder equipped with masked separable attention (MSA) is applied to gradually polish the prediction results. All
the predictions generated by our CamoFormer are supervised by the ground truth (GT).
    </em>
</p>




## 1. :fire: NEWS :fire:

- [2022/12/09] Releasing the codebase of CamoFormer and the whole COD benchmarking results (21 models).
- [2022/12/08] Creating repository.

> We invite all to contribute in making it more acessible and useful. If you have any questions about our work, feel free to contact me via e-mail (bowenyin@mail.nankai.edu.cn). If you are using our code and evaluation toolbox for your research, please cite this paper ([BibTeX]()).

## 2. Get Start

**0. Install**

```
conda create --name CamoFormer python=3.8.5
conda activate CamoFormer
conda install pytorch==1.12.1 torchvision==0.13.1 cudatoolkit=11.3 -c pytorch
pip install opencv-python
conda install tensorboard
conda install tensorboardX
pip install timm
pip install matplotlib
pip install scipy
pip install einops

Please also install [apex](https://github.com/NVIDIA/apex).
git clone https://github.com/NVIDIA/apex
cd apex
pip install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" ./
```


**1. Download Datasets and Checkpoints.**

- **Datasets:** 

By default, you can put datasets into the folder 'dataset'.

[Baidu Netdisk](https://pan.baidu.com/s/1Tcvt0IJYdKSYAb_BD5QrTg?pwd=2gf4),
[One Drive](https://mailnankaieducn-my.sharepoint.com/:f:/g/personal/bowenyin_mail_nankai_edu_cn/EuSpxg1R9l1OmSkOqlUpMCcBvOE-JgtaeJVZfwwKOEjJhQ?e=sCWZE9)

- **Checkpoints:** 

By default, you can put datasets into the folder 'checkpoint'.

CamoFormer: [Baidu Netdisk](https://pan.baidu.com/s/1QyE_HkxCp9vWlhnJAx20dQ?pwd=f4bp), [One Drive](https://mailnankaieducn-my.sharepoint.com/:f:/g/personal/bowenyin_mail_nankai_edu_cn/Eg2fWTz1pjFBiJfAdj1XqGQBbQ2pOjpNq0AbIjseadTgSA?e=BFvBkU)
Backbone: [Baidu Netdisk](https://pan.baidu.com/s/1E10fb4_Gr08_6LV6AdyhSg?pwd=pgdk),  [One Drive](https://mailnankaieducn-my.sharepoint.com/:f:/g/personal/bowenyin_mail_nankai_edu_cn/Et3EzPUD2GJOn1YafL1NDDYBXwWtdsLd3EZCVua-mVSdhw?e=7XoXoR)

**2. Test.**
```
bash test.sh
```

**3. Eval.**
```
bash eval.sh
```


## 3. Proposed CamoFormer

### 3.1. The F-TA in MSA:


<p align="center">
    <img src="figs/F-TA.png"  width="600"  width="1200"/> <br />
    <em> 
    Figure 2: Diagrammatic details of the proposed F-TA in our MSA. Our B-TA shares a similar structure except for the mask.
    </em>
</p>


### 3.2 COD Benchmark Results:

The prediction of our CamoFprmer can be found in [One Drive](https://mailnankaieducn-my.sharepoint.com/:f:/g/personal/bowenyin_mail_nankai_edu_cn/EmB36EZb_fdMvWGgKx2EalgBuQnj8AFifyR-ip7Jtkfwqg?e=nu6DJz), [Baidu Netdisk](https://pan.baidu.com/s/1k5CxYzcgizzJ4sRdAxBNlA?pwd=srtf), or [Google Drive](https://drive.google.com/drive/folders/1gsCeYtS9cwsMpTHQzkx81n4jsRK4LYdf?usp=sharing). Here are quantitative performance comparison.

<p align="center">
    <img src="figs/Performance.png" width="600"  width="1200"/> <br />
    <em> 
    Figure 3: Comparison of our CamoFormer with the recent SOTA methods. ‘-R’: ResNet, ‘-C’: ConvNext, ‘-S’: Swin Transformer, ‘-P’: PVTv2. As can be seen, our CamoFormer-P performs much better than previous methods with either CNN- or
Transformer-based models. ‘↑’: the higher the better, ‘↓’: the lower the better.
    </em>

</p>



## Acknowlegement
Thanks [mczhuge](https://github.com/mczhuge) providing a friendly [codebase](https://github.com/mczhuge/ICON) for binary segmentation tasks. And our code is built based on it. 



## Reference
You may want to cite:
```
@article{yin2022camoformer,
  title={CamoFormer: Masked Separable Attention for Camouflaged Object Detection},
  author={Bowen Yin and Xuying Zhang and Qibin Hou and Bo-Yuan Sun and Deng-Ping Fan and Luc Van Gool},
  journal={arXiv preprint arXiv:2212.06570},
  year={2022}
}
```

### License

Code in this repo is for non-commercial use only.






