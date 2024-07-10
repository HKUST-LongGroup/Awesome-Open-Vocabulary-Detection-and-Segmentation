![Static Badge](https://img.shields.io/badge/Build-Updating-blue)
[![Static Badge](https://img.shields.io/badge/PR-Welcome-orange)](https://github.com/seanzhuh/awesome-open-vocabulary-detection-and-segmentation/pulls)
[![Static Badge](https://img.shields.io/badge/%E7%9F%A5%E4%B9%8E-%E4%B8%AD%E6%96%87%E7%89%88-blue)](https://zhuanlan.zhihu.com/p/692846245)
<a href='https://arxiv.org/abs/2307.09220'>
    <img src='https://img.shields.io/badge/arXiv-PDF-green?style=flat&logo=arXiv&logoColor=green' alt='arXiv PDF'>
</a>
<p align="center">
  <h1 align="center"><a href='https://arxiv.org/abs/2307.09220'>A Survey on Open-Vocabulary Detection and Segmentation: Past, Present, and Future</a></h1>
  <p align="center">
    <a href="https://scholar.google.com/citations?user=jkxdiToAAAAJ&hl=en" style="text-decoration: none;">Chaoyang Zhu</a>,
    <a href="https://scholar.google.com/citations?hl=en&user=-gtmMpIAAAAJ" style="text-decoration: none;">Long Chen<sup>*</sup></a>
  </p>
<br>

## News

Please remain tuned, this repo will be maintained on a week-to-week basis.

* 27/06/2024: NeRF and 3DGS based 3D scene understanding is added.
* 05/06/2024: Our 2nd version manuscript is accepted by TPAMI.

## :sparkles: PR is welcome!

Though we aim to cover every paper, still chances may happen that some works are missing. Peer review is welcome and will be highly appreciated, if you are the authors and find our recordings are incorrect, don't hesitate to contact me and fire a PR.

## General Overview

In this survey, we cover two settings (zero-shot and open-vocabulary) and six tasks (object detection, semantic/instance/panoptic segmentation, 3D scene understanding, and video understanding). We pivot on the permission to weak supervision signals and the usage of weak supervision signals to build a taxonomy that is universal across these diverse settings and tasks. The weak supervision signals can be image-text pairs or large vision-language models. Below is a general overview of each methodology.

<image src="figs/comp.png" width="50%" aligh="middle">

In current literature, zero-shot and open-vocabulary are used interchangeably, however, we highlight their subtle differences through the evolvement from traditional zero-shot to the newly formulated open-vocabulary setting.

<image src="figs/table.png" width="50%">

## Table of Contents

- [Zero-Shot Object Detection](#zsd)
  - [Visual-Semantic Space Mapping](#zsd-vssm)
  - [Novel Visual Feature Synthesis](#zsd-nvfs)
- [Zero-Shot Segmentation](#zss)
    - [Zero-Shot Semantic Segmentation](#zsss)
        - [Visual-Semantic Space Mapping](#zsss-vssm)
        - [Novel Visual Feature Synthesis](#zsss-nvfs)
    - [Zero-Shot Instance Segmentation](#zsis)
- [Open-Vocabulary Object Detection](#ovd)
    - [Region-Aware Training](#ovd-rat)
    - [Pseudo-Labeling](#ovd-pl)
    - [Knowledge Distillation](#ovd-kd)
    - [Transfer Learning](#ovd-tl)
- [Open-Vocabulary Segmentation](#ovs)
    - [Open-Vocabulary Semantic Segmentation](#ovss)
        - [Region-Aware Training](#ovss-rat)
        - [Pseudo-Labeling](#ovss-pl)
        - [Knowledge Distillation](#ovss-kd)
        - [Transfer Learning](#ovss-tl)
    - [Open-Vocabulary Instance Segmentation](#ovis)
        - [Region-Aware Training](#ovis-rat)
        - [Pseudo-Labeling](#ovis-pl)
        - [Knowledge Distillation](#ovis-kd)
    - [Open-Vocabulary Panoptic Segmentation](#ovps)
        - [Region-Aware Training](#ovps-rat)
        - [Knowledge Distillation](#ovps-kd)
        - [Transfer Learning](#ovps-tl)
- [Open-Vocabulary 3D Scene Understanding](#ov3d)
    - [Open-Vocabulary 3D Detection](#ov3d-det)
    - [Open-Vocabulary 3D Segmentation](#ov3d-seg)
        - [Open-Vocabulary 3D Semantic Segmentation](#ov3d-seg-sem)
        - [Open-Vocabulary 3D Instance Segmentation](#ov3d-seg-ins)
    - [NeRF and 3DGS based](#ov3d-nerf-3dgs)
- [Open-Vocabulary Video Understanding](#ovvu)
    - [Open-Vocabulary Video Instance Segmentation](#ovvu-seg-ins)
- [Acknowledgement](#ack)

<a id="zsd"></a>
## Zero-Shot Object Detection

<a id="zsd-vssm"></a>
### Visual-Semantic Space Mapping

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ECCV'18|[ZSDv1](https://arxiv.org/abs/1804.04340)|N/A|
|ACCV'18 & IJCV'20|[ZSDv2](https://arxiv.org/abs/1803.06049)|N/A|
|AAAI'20|[CA-ZSR](https://arxiv.org/abs/1904.09320)|[Code](https://github.com/ruotianluo/Context-aware-ZSR)|
|AAAI'19|[ZSD-TD](https://ojs.aaai.org/index.php/AAAI/article/view/4891)|N/A|
|ACCV'20|[BLC](https://arxiv.org/abs/2010.04502)|[Code](https://github.com/zhengye1995/BLC)|
|ICCV'19|[TL-ZSD](https://openaccess.thecvf.com/content_ICCV_2019/html/Rahman_Transductive_Learning_for_Zero-Shot_Object_Detection_ICCV_2019_paper.html)|N/A|
|arXiv'23|[SSB](https://arxiv.org/abs/2302.07319)|N/A|
|WACV'20|[MS-Zero](https://openaccess.thecvf.com/content_WACV_2020/papers/Gupta_A_Multi-Space_Approach_to_Zero-Shot_Object_Detection_WACV_2020_paper.pdf)|N/A|
|TCSVT'19|[ZS-YOLO](https://ieeexplore.ieee.org/abstract/document/8642945)|N/A|
|AAAI'21|[DPIF](https://ojs.aaai.org/index.php/AAAI/article/view/16295)|[Code](https://github.com/Lppy/DPIF)|
|TPAMI'21|[ContrastZSD](https://arxiv.org/abs/2109.06062)|N/A|
|IJCAI'20|[ZSD-CNN](https://www.ijcai.org/proceedings/2020/126)|N/A|

<a id="zsd-nvfs"></a>
### Novel Visual Feature Synthesis

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'20|[DELO](https://arxiv.org/abs/1911.07933)|N/A|
|ACCV'20|[SU](https://arxiv.org/abs/2010.09425)|[Code](https://github.com/nasir6/zero_shot_detection)|
|AAAI'20|[GTNet](https://arxiv.org/abs/2001.06812)|[Code](https://github.com/X-BrainLab/GTNet)|
|CVPR'22|[RRFS](https://arxiv.org/abs/2201.00103)|[Code](https://github.com/HPL123/RRFS)|

<a id="zss"></a>
## Zero-Shot Segmentation

<a id="zsss"></a>
### Zero-Shot Semantic Segmentation

<a id="zsss-vssm"></a>
#### Visual-Semantic Space Mapping

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'20|[SPNet](https://ieeexplore.ieee.org/document/8953827)|[Code](https://github.com/subhc/SPNet)|
|NeurIPS'20|[ULZSS](https://proceedings.neurips.cc/paper/2020/hash/f73b76ce8949fe29bf2a537cfa420e8f-Abstract.html)|[Code](https://github.com/feinanshan/ULZSS)|
|ICCV'21|[JoEm](https://arxiv.org/abs/2108.06536)|[Code](https://github.com/cvlab-yonsei/JoEm)|
|ICCVW'19|[VM](https://ieeexplore.ieee.org/document/9022071)|N/A|
|ICCV'21|[PMOSR](https://ieeexplore.ieee.org/document/9709966)|N/A|

<a id="zsss-nvfs"></a>
#### Novel Visual Feature Synthesis

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|NeurIPS'19|[ZS3Net](https://arxiv.org/abs/1906.00817)|[Code](https://github.com/valeoai/ZS3)|
|NeurIPS'20|[CSRL](https://proceedings.neurips.cc/paper/2020/hash/7504adad8bb96320eb3afdd4df6e1f60-Abstract.html)|N/A|
|MM'20|[CaGNet](https://arxiv.org/abs/2008.06893)|[Code](https://github.com/bcmi/CaGNet-Zero-Shot-Semantic-Segmentation)|
|ICCV'21|[SIGN](https://arxiv.org/abs/2108.12517)|[Code](https://github.com/cplusx/SIGN)|

<a id="zsis"></a>
### Zero-Shot Instance Segmentation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'21|[ZSIS](https://arxiv.org/abs/2104.06601)|[Code](https://github.com/zhengye1995/Zero-shot-Instance-Segmentation)|

<a id="ovd"></a>
## Open-Vocabulary Object Detection

<a id="ovd-rat"></a>
### Region-Aware Training

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'21|[OVR-CNN](https://arxiv.org/abs/2011.10678)|[Code](https://github.com/alirezazareian/ovr-cnn)|
|GCPR'22|[LocOv](https://arxiv.org/abs/2205.06160)|[Code](https://github.com/lmb-freiburg/locov)|
|arXiv'23|[MMC-Det](https://arxiv.org/abs/2308.15846)|N/A|
|NeurIPS'22|[DetCLIP](https://arxiv.org/abs/2209.09407)|N/A|
|CVPR'23|[DetCLIPv2](https://arxiv.org/abs/2304.04514)|N/A|
|CVPR'24|[DetCLIPv3](https://arxiv.org/abs/2404.09216)|N/A|
|AAAI'24|[WSOVOD](https://arxiv.org/abs/2312.12437)|[Code](https://github.com/HunterJ-Lin/WSOVOD)|
|CVPR'23|[RO-ViT](https://arxiv.org/abs/2305.07011)|N/A|
|ICCV'23|[CFM-ViT](https://arxiv.org/abs/2309.00775)|N/A|
|ICCV'23|[DITO](https://arxiv.org/abs/2310.00161)|[Code](https://github.com/google-research/google-research/tree/master/fvlm/dito)|
|ICLR'23|[VLDet](https://arxiv.org/abs/2211.14843)|[Code](https://github.com/clin1223/VLDet)|
|ICCV'23|[GOAT](https://openaccess.thecvf.com/content/ICCV2023/papers/Wang_Open-Vocabulary_Object_Detection_With_an_Open_Corpus_ICCV_2023_paper.pdf)|N/A|
|ECCV'22|[OV-DETR](https://arxiv.org/abs/2203.11876)|[Code](https://github.com/yuhangzang/OV-DETR)|
|arXiv'23|[Prompt-OVD](https://arxiv.org/abs/2303.14386)|N/A|
|CVPR'23|[CORA](https://arxiv.org/abs/2303.13076)|N/A|
|ICCV'23|[EdaDet](https://arxiv.org/abs/2309.01151)|[Code](https://chengshiest.github.io/edadet/)|
|ICCV'21|[MDETR](https://arxiv.org/abs/2104.12763)|[Code](https://github.com/ashkamath/mdetr)|
|ECCV'22|[MAVL](https://arxiv.org/abs/2111.11430)|[Code](https://github.com/mmaaz60/mvits_for_class_agnostic_od)|
|NeurIPS'24|[MQ-Det](https://arxiv.org/abs/2305.18980)|[Code](https://github.com/YifanXu74/MQ-Det)|
|CVPR'24|[YOLO-World](https://www.yoloworld.cc/)|[Code](https://github.com/AILab-CVC/YOLO-World)|
|MM'23|[SGDN](http://arxiv.org/abs/2307.03339)|N/A|
|CVPR'24|[USE](https://openaccess.thecvf.com/content/CVPR2024/html/Wang_USE_Universal_Segment_Embeddings_for_Open-Vocabulary_Image_Segmentation_CVPR_2024_paper.html)|N/A|

<a id="ovd-pl"></a>
### Pseudo-Labeling

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'22|[RegionCLIP](https://arxiv.org/abs/2112.09106)|[Code](https://github.com/microsoft/RegionCLIP)|
|ECCV'22|[VL-PLM](https://arxiv.org/abs/2207.08954)|[Code](https://github.com/xiaofeng94/VL-PLM)|
|CVPR'22|[GLIP](https://arxiv.org/pdf/2112.03857.pdf)|[Code](https://github.com/microsoft/GLIP)|
|NeurIPS'22|[GLIPv2](https://arxiv.org/pdf/2206.05836.pdf)|[Code](https://github.com/microsoft/GLIP)|
|arXiv'23|[Grounding-DINO](https://arxiv.org/abs/2303.05499)|[Code](https://github.com/IDEA-Research/GroundingDINO)|
|ECCV'22|[PromptDet](https://arxiv.org/abs/2203.16513)|[Code](https://github.com/fcjian/PromptDet)|
|arXiv'23|[SAS-Det](https://arxiv.org/abs/2308.06412)|[Code](https://github.com/xiaofeng94/sas-det)|
|ECCV'22|[PB-OVD](https://arxiv.org/abs/2111.09452)|[Code](https://github.com/salesforce/PB-OVD)|
|AAAI'24|[CLIM](https://arxiv.org/abs/2312.11376)|[Code](https://github.com/wusize/CLIM)|
|arXiv'22|[VTP-OVD](https://arxiv.org/abs/2211.00849)|N/A|
|AAAI'24|[ProxyDet](https://arxiv.org/abs/2312.07266)|[Code](https://github.com/clovaai/ProxyDet)|
|NeurIPS'23|[CoDet](https://arxiv.org/abs/2310.16667)|[Code](https://github.com/cvmi-lab/codet)|
|ECCV'22|[Detic](https://arxiv.org/abs/2201.02605)|[Code](https://github.com/facebookresearch/Detic)|
|ICML'23|[MMC](https://arxiv.org/abs/2306.05493)|[Code](https://github.com/prannaykaul/mm-ovod)|
|arXiv'23|[3Ways](https://arxiv.org/abs/2303.13518)|N/A|
|arXiv'23|[PLAC](https://arxiv.org/abs/2312.02103)|N/A|
|arXiv'23|[PCL](https://arxiv.org/abs/2303.13040)|N/A|
|NeurIPS'24|[OWLv2](arxiv.org/abs/2306.09683)|[Code](https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit)|

<a id="ovd-kd"></a>
### Knowledge Distillation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ICLR'22|[ViLD](https://arxiv.org/abs/2104.13921)|[Code](https://github.com/tensorflow/tpu/tree/master/models/official/detection/projects/vild)|
|ICDMW'22|[ZSD-YOLO](https://arxiv.org/abs/2109.12066)|[Code](https://github.com/Johnathan-Xie/ZSD-YOLO)|
|WACV'24|[LP-OVOD](https://arxiv.org/abs/2310.17109)|[Code](https://github.com/VinAIResearch/LP-OVOD)|
|arXiv'23|[EZSD](https://arxiv.org/abs/2303.12145)|[Code](https://github.com/dragonlzm/EZAD)|
|AAAI'24|[SIC-CADS](https://arxiv.org/abs/2312.10439)|[Code](https://github.com/mala-lab/sic-cads)|
|CVPR'23|[BARON](https://arxiv.org/abs/2302.13996)|[Code](https://github.com/wusize/ovdet)|
|CVPR'23|[OADP](https://arxiv.org/abs/2303.05892)|[Code](https://github.com/LutingWang/OADP)|
|arXiv'23|[GridCLIP](https://arxiv.org/abs/2303.09252)|N/A|
|NeurIPS'22|[RKDWTF](https://arxiv.org/abs/2207.03482)|[Code](https://github.com/hanoonaR/object-centric-ovd)|
|ICCV'23|[DK-DETR](https://openaccess.thecvf.com/content/ICCV2023/html/Li_Distilling_DETR_with_Visual-Linguistic_Knowledge_for_Open-Vocabulary_Object_Detection_ICCV_2023_paper.html)|[Code](https://github.com/hikvision-research/opera)|
|CVPR'22|[HierKD](https://arxiv.org/abs/2203.10593)|[Code](https://github.com/mengqiDyangge/HierKD)|
|CVPR'22|[DetPro](https://arxiv.org/abs/2203.14940)|[Code](https://github.com/dyabel/detpro)|
|arXiv'23|[CLIPSelf](https://arxiv.org/abs/2310.01403)|[Code](https://github.com/wusize/CLIPSelf)|
|CVPR'24|[SAMP](https://openaccess.thecvf.com/content/CVPR2024/html/Zhao_Scene-adaptive_and_Region-aware_Multi-modal_Prompt_for_Open_Vocabulary_Object_Detection_CVPR_2024_paper.html)|N/A|
|IJCV'24|[OV-DAR](https://link.springer.com/article/10.1007/s11263-024-02144-1)|N/A|
|CVPR'24|[LBP](https://openaccess.thecvf.com/content/CVPR2024/html/Li_Learning_Background_Prompts_to_Discover_Implicit_Knowledge_for_Open_Vocabulary_CVPR_2024_paper.html)|N/A|

<a id="ovd-tl"></a>
### Transfer Learning

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ECCV'22|[OWL-ViT](https://arxiv.org/abs/2205.06230)|[Code](https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit)|
|CVPR'23|[UniDetector](https://arxiv.org/abs/2303.11749)|[Code](https://github.com/zhenyuw16/UniDetector)|
|ICLR'23|[F-VLM](https://arxiv.org/abs/2209.15639)|[Code](https://github.com/google-research/google-research/tree/master/fvlm)|
|CVPR'23|[ScaleDet](https://arxiv.org/abs/2306.04849)|N/A|
|ICCV'23|[OpenSeed](https://arxiv.org/abs/2303.08131)|[Code](https://github.com/IDEA-Research/OpenSeeD)|
|arXiv'23|[DRR](https://arxiv.org/abs/2309.00227)|N/A|
|arXiv'23|[Sambor](https://arxiv.org/abs/2312.03628)|[Code](https://github.com/ucas-vg/Sambor)|

<a id="ovs"></a>
## Open-Vocabulary Segmentation

<a id="ovss"></a>
### Open-Vocabulary Semantic Segmentation

<a id="ovss-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ECCV'22|[OpenSeg](https://arxiv.org/abs/2112.12143)|N/A|
|arXiv'23|[SLIC](https://arxiv.org/abs/2310.13355)|N/A|
|CVPR'22|[GroupViT](https://arxiv.org/abs/2202.11094)|[Code](https://github.com/NVlabs/GroupViT)|
|ECCV'22|[ViL-Seg](https://arxiv.org/abs/2207.08455)|N/A|
|ICML'23|[SegCLIP](https://arxiv.org/abs/2211.14813)|[Code](https://github.com/ArrowLuo/SegCLIP)|
|CVPR'23|[OVSegmentor](https://arxiv.org/abs/2301.09121)|[Code](https://github.com/Jazzcharles/OVSegmentor/)|
|CVPR'23|[PACL](https://arxiv.org/abs/2212.04994)|N/A|
|CVPR'23|[TCL](https://arxiv.org/abs/2212.00785)|[Code](https://github.com/kakaobrain/tcl)|
|ECCV'22|[SimSeg](https://arxiv.org/abs/2112.14757)|[Code](https://github.com/MendelXu/zsseg.baseline)|

<a id="ovss-pl"></a>
#### Pseudo-Labeling

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ECCV'22|[TTD](https://link.springer.com/chapter/10.1007/978-3-031-25063-7_4)|N/A|

<a id="ovss-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|arXiv'23|[GKC](https://arxiv.org/abs/2303.09181)|N/A|
|arXiv'23|[SAM-CLIP](https://arxiv.org/abs/2310.15308)|N/A|
|ICCV'23|[ZeroSeg](https://openaccess.thecvf.com/content/ICCV2023/html/Chen_Exploring_Open-Vocabulary_Semantic_Segmentation_from_CLIP_Vision_Encoder_Distillation_Only_ICCV_2023_paper.html)|[Code](https://github.com/facebookresearch/ZeroSeg)|

<a id="ovss-tl"></a>
#### Transfer Learning

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ICLR'22|[LSeg](https://arxiv.org/abs/2201.03546)|[Code](https://github.com/isl-org/lang-seg)|
|CVPR'23|[SAZS](https://openaccess.thecvf.com/content/CVPR2023/html/Liu_Delving_Into_Shape-Aware_Zero-Shot_Semantic_Segmentation_CVPR_2023_paper.html)|[Code](https://github.com/Liuxinyv/SAZS)|
|MM'23|[CEL](https://arxiv.org/abs/2301.07336)|N/A|
|CVPR'22|[ZegFormer](https://arxiv.org/abs/2112.07910)|[Code](https://github.com/dingjiansw101/ZegFormer)|
|NeurIPS'22|[ReCo](https://arxiv.org/abs/2206.07045)|[Project](https://www.robots.ox.ac.uk/~vgg/research/reco/)|
|arXiv'23|[SCAN](https://arxiv.org/abs/2312.04089)|N/A|
|ECCV'22|[ZSSeg](https://arxiv.org/abs/2112.14757)|[Code](https://github.com/MendelXu/zsseg.baseline)|
|ECCV'22|[MaskCLIP](https://arxiv.org/abs/2112.01071)|[Code](https://github.com/chongzhou96/MaskCLIP)|
|arXiv'23|[CLIP-DINOiser](https://arxiv.org/abs/2312.12359)|[Code](https://github.com/wysoczanska/clip_dinoiser)|
|PRCV'23|[MVP-SEG](https://arxiv.org/abs/2304.06957)|N/A|
|arXiv'23|[OVDiff](https://arxiv.org/abs/2306.09316)|[Project](https://www.robots.ox.ac.uk/~vgg/research/ovdiff/)|
|WACV'24|[FOSSIL](https://openaccess.thecvf.com/content/WACV2024/html/Barsellotti_FOSSIL_Free_Open-Vocabulary_Semantic_Segmentation_Through_Synthetic_References_Retrieval_WACV_2024_paper.html)|N/A|
|NeurIPS'24|[POMP](https://arxiv.org/abs/2304.04704)|[Code](https://github.com/amazon-science/prompt-pretraining)|
|NeurIPS'24|[AttrSeg](https://arxiv.org/abs/2309.00096)|N/A|
|arXiv'23|[PnP-OVSS](https://arxiv.org/abs/2311.17095)|[Code](https://github.com/letitiabanana/PnP-OVSS)|
|arXiv'23|[TagAlign](https://arxiv.org/abs/2312.14149)|[Project](https://qinying-liu.github.io/Tag-Align/)|
|arXiv'23|[SelfSeg](https://arxiv.org/abs/2312.04539)|N/A|
|CVPR'22|[DenseCLIP](https://openaccess.thecvf.com/content/CVPR2022/html/Rao_DenseCLIP_Language-Guided_Dense_Prediction_With_Context-Aware_Prompting_CVPR_2022_paper.html)|[Code](https://github.com/raoyongming/DenseCLIP)|
|CVPR'23|[OVSeg](https://arxiv.org/abs/2210.04150)|[Code](https://github.com/facebookresearch/ov-seg)|
|arXiv'23|[CAT-Seg](https://arxiv.org/abs/2303.11797)|[Code](https://github.com/KU-CVLAB/CAT-Seg)|
|arXiv'23|[SED](https://arxiv.org/abs/2311.15537)|[Code](https://github.com/xb534/SED)|
|NeurIPS'23|[MAFT](https://openreview.net/forum?id=K1Uzj8tuwd)|[Code](https://github.com/jiaosiyu1999/MAFT)|
|arXiv'23|[TagCLIP](https://arxiv.org/abs/2304.07547)|N/A|
|CVPR'23|[ZegCLIP](https://openaccess.thecvf.com/content/CVPR2023/html/Zhou_ZegCLIP_Towards_Adapting_CLIP_for_Zero-Shot_Semantic_Segmentation_CVPR_2023_paper.html)|[Code](https://github.com/ZiqinZhou66/ZegCLIP.git)|
|CVPR'22|[CLIPSeg](https://arxiv.org/abs/2112.10003)|[Code](https://github.com/timojl/clipseg)|
|CVPR'23|[SAN](https://arxiv.org/abs/2302.12242)|[Code](https://github.com/MendelXu/SAN)|
|arXiv'23|[CLIP Surgery](https://arxiv.org/abs/2304.05653)|[Code](https://github.com/xmed-lab/CLIP_Surgery)|
|arXiv'23|[CaR](https://arxiv.org/abs/2312.07661)|[Project](https://torrvision.com/clip_as_rnn/)|
|arXiv'24|[Cascade-CLIP](https://arxiv.org/abs/2406.00670)|[Code](https://github.com/HVision-NKU/Cascade-CLIP)|
|arXiv'24|[OpenDAS](https://arxiv.org/abs/2405.20141)|[Project](https://goncayilmaz.github.io/opendas/)|

<a id="ovis"></a>
### Open-Vocabulary Instance Segmentation

<a id="ovis-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ICCV'23|[CGG](https://arxiv.org/abs/2301.00805)|[Code](https://github.com/jianzongwu/betrayed-by-captions)|
|CVPR'23|[D2Zero](https://henghuiding.github.io/D2Zero/)|[Code](https://github.com/heshuting555/D2Zero)|

<a id="ovis-pl"></a>
#### Pseudo-Labeling

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'23|[XPM](https://arxiv.org/abs/2111.12698)|[Code](https://github.com/hbdat/cvpr22_cross_modal_pseudo_labeling)|
|CVPR'23|[Mask-free OVIS](https://arxiv.org/abs/2303.16891)|[Code](https://github.com/Vibashan/Maskfree-OVIS)|
|arXiv'23|[MosaicFusion](https://arxiv.org/abs/2309.13042)|[Code](https://github.com/Jiahao000/MosaicFusion)|

<a id="ovis-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|arXiv'24|[OV-SAM](https://arxiv.org/abs/2401.02955)|[Code](https://github.com/HarborYuan/ovsam)|

<a id="ovps"></a>
### Open-Vocabulary Panoptic Segmentation

<a id="ovps-rat"></a>
#### Region-Aware Training

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|arXiv'24|[Uni-OVSeg](https://arxiv.org/abs/2402.08960)|[Code](https://github.com/DerrickWang005/Uni-OVSeg.pytorch)|
|CVPR'23|[X-Decoder](https://arxiv.org/abs/2212.11270)|[Code](https://github.com/microsoft/X-Decoder/tree/main)|
|CVPR'24|[APE](https://arxiv.org/abs/2312.02153)|[Code](https://github.com/shenyunhang/APE)|

<a id="ovps-kd"></a>
#### Knowledge Distillation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'23|[PADing](https://henghuiding.github.io/PADing/)|[Code](https://github.com/heshuting555/PADing)|

<a id="ovps-tl"></a>
#### Transfer Learning

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|NeurIPS'23|[FC-CLIP](https://arxiv.org/abs/2308.02487)|[Code](https://github.com/bytedance/fc-clip)|
|CVPR'23|[FreeSeg](https://arxiv.org/abs/2303.17225)|[Project](https://freeseg.github.io/)|
|arXiv'24|[PosSAM](https://arxiv.org/abs/2403.09620)|[Project](https://vibashan.github.io/possam-web/)|
|ICCV'23|[MasQCLIP](https://openaccess.thecvf.com/content/ICCV2023/papers/Xu_MasQCLIP_for_Open-Vocabulary_Universal_Image_Segmentation_ICCV_2023_paper.pdf)|[Project](https://masqclip.github.io/)|
|CVPR'23|[OMG-Seg](https://arxiv.org/abs/2401.10229)| [Code](https://github.com/lxtGH/OMG-Seg)|
|arXiv'23|[Semantic-SAM](https://arxiv.org/abs/2307.04767)|[Code](https://github.com/UX-Decoder/Semantic-SAM)|
|CVPR'23|[ODISE](https://arxiv.org/abs/2303.04803)|[Code](https://github.com/NVlabs/ODISE)|
|NeurIPS'23|[HIPIE](https://arxiv.org/abs/2307.00764)|[Code](https://github.com/berkeley-hipie/HIPIE)|
|ICML'23|[MaskCLIP](https://arxiv.org/abs/2208.08984)|[Project](https://maskclip.github.io/)|
|ICCV'23|[OPSNet](https://arxiv.org/abs/2303.11324)|N/A|

<a id="ov3d"></a>
## Open-Vocabulary 3D Scene Understanding

<a id="ov3d-det"></a>
### Open-Vocabulary 3D Detection

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|CVPR'23|[OV-3DET](https://arxiv.org/abs/2304.00788v2)|[Code](https://github.com/lyhdet/OV-3DET)|
|AAAI'24|[FM-OV3D](https://arxiv.org/abs/2312.14465)|[Code](https://github.com/dmzhang0425/FM-OV3D)|
|arXiv'23|[OpenSight](https://arxiv.org/abs/2312.08876)|N/A|
|NeurIPS'23|[CoDA](https://arxiv.org/abs/2310.02960)|[Code](https://github.com/yangcaoai/CoDA_NeurIPS2023)|
|arXiv'23|[L3Det](https://arxiv.org/abs/2309.09456)|N/A|

<a id="ov3d-seg"></a>
### Open-Vocabulary 3D Segmentation

<a id="ov3d-seg-sem"></a>
#### Open-Vocabulary 3D Semantic Segmentation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|arXiv'21|[SeCondPoint](https://arxiv.org/abs/2107.00430)|N/A|
|3DV'21|[3DGenZ](https://arxiv.org/abs/2108.06230)|[Code](https://github.com/valeoai/3DGenZ)|
|CVPR'23|[OpenScene](https://arxiv.org/abs/2211.15654)|[Project](https://pengsongyou.github.io/openscene)|
|CVPR'23|[PLA](https://arxiv.org/abs/2211.16312)|[Code](https://dingry.github.io/projects/PLA)|
|arXiv'23|[RegionPLC](https://arxiv.org/abs/2304.00962)|[Project](https://jihanyang.github.io/projects/RegionPLC)|

<a id="ov3d-seg-ins"></a>
#### Open-Vocabulary 3D Instance Segmentation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|NeurIPS'23|[OpenMask3D](https://arxiv.org/abs/2306.13631)|[Project](https://openmask3d.github.io/)|
|CVPR'24|[MaskClustering](https://arxiv.org/abs/2401.07745)|[Project](https://pku-epic.github.io/MaskClustering/)|
|arXiv'23|[OpenIns3D](https://arxiv.org/abs/2309.00616)|[Project](https://zheninghuang.github.io/OpenIns3D/)|
|arXiv'23|[Open3DIS](https://arxiv.org/abs/2312.10671)|[Project](https://open3dis.github.io)|

<!-- |CVPR'23|[CLIP2Scene](https://arxiv.org/abs/2301.04926)|[Code](https://github.com/runnanchen/CLIP2Scene)|
|2023|ICCVW|[CLIP-FO3D](https://arxiv.org/abs/2303.04748)|N/A|
|arXiv'24|[UniM-OV3D](https://arxiv.org/abs/2401.11395)|[Code](https://github.com/hithqd/UniM-OV3D)|
|arXiv'22|[Open-Vocabulary 3D Detection via Image-level Class and Debiased Cross-modal Contrastive Learning](https://arxiv.org/abs/2207.01987)|N/A| -->

<a id="ov3d-nerf-3dgs"></a>
### NeRF and 3DGS based

NeRF ([Neural Radiance Field](https://dl.acm.org/doi/abs/10.1145/3503250)) and 3DGS ([3D Gaussian Splatting](https://arxiv.org/abs/2308.04079)) are hot topics for novel view synthesis in a holistic scene. They leverage multi-view consistency learning inherently imposed in the 3D model to help 2D image segmentation or directly perform 3D semantic segmentation over points (voxel or gaussian) in the scene.

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ICCV'21|[Semantic-NeRF](https://openaccess.thecvf.com/content/ICCV2021/html/Zhi_In-Place_Scene_Labelling_and_Understanding_With_Implicit_Scene_Representation_ICCV_2021_paper.html?ref=https://githubhelp.com)|[Code](https://github.com/Harry-Zhi/semantic_nerf)|
|NeurIPS'22|[FFD](https://proceedings.neurips.cc/paper_files/paper/2022/hash/93f250215e4889119807b6fac3a57aec-Abstract-Conference.html)|[Code](https://github.com/pfnet-research/distilled-feature-fields)|
|arXiv'23|[Gaussian Grouping](https://arxiv.org/abs/2312.00732)|[Code](https://github.com/lkeab/gaussian-grouping)|
|ICCV'23|[LERF](https://openaccess.thecvf.com/content/ICCV2023/html/Kerr_LERF_Language_Embedded_Radiance_Fields_ICCV_2023_paper.html?trk=public_post_comment-text)|[Project](https://lerf.io)|
|NeurIPS'23|[3DOVS](https://proceedings.neurips.cc/paper_files/paper/2023/hash/a76b693f36916a5ed84d6e5b39a0dc03-Abstract-Conference.html)|[Code](https://github.com/Kunhao-Liu/3D-OVS)|
|arXiv'24|[OpenGaussian](https://arxiv.org/abs/2406.02058)|[Project](https://3d-aigc.github.io/OpenGaussian/)|
|arXiv'24|[OV-NeRF](https://arxiv.org/abs/2402.04648)|[Code](https://github.com/pcl3dv/OV-NeRF)|
|arXiv'24|[Semantic Gaussians](https://arxiv.org/abs/2403.15624)|[Project](https://semantic-gaussians.github.io/)|
|arXiv'24|[FMGS](https://arxiv.org/abs/2401.01970)|[Project](https://xingxingzuo.github.io/fmgs/)|
|CVPR'24|[LEGaussians](https://openaccess.thecvf.com/content/CVPR2024/html/Shi_Language_Embedded_3D_Gaussians_for_Open-Vocabulary_Scene_Understanding_CVPR_2024_paper.html)|[Code](https://github.com/buaavrcg/LEGaussians)|
|CVPR'24|[LangSplat](https://openaccess.thecvf.com/content/CVPR2024/html/Qin_LangSplat_3D_Language_Gaussian_Splatting_CVPR_2024_paper.html)|[Project](https://langsplat.github.io/)|
|CVPR'24|[Feature 3DGS](https://openaccess.thecvf.com/content/CVPR2024/html/Zhou_Feature_3DGS_Supercharging_3D_Gaussian_Splatting_to_Enable_Distilled_Feature_CVPR_2024_paper.html)|[Code](https://github.com/ShijieZhou-UCLA/feature-3dgs)|

<a id="ovvu"></a>
## Open-Vocabulary Video Understanding

<a id="ovvu-seg-ins"></a>
### Open-Vocabulary Video Instance Segmentation

|Venue|Paper Abbr|Project|
|:-:|:-:|:-:|
|ICCV'23|[OV2Seg](https://arxiv.org/abs/2304.01715)|[Code](https://github.com/haochenheheda/LVVIS)|
|arXiv'23|[OpenVIS](https://arxiv.org/abs/2305.16835)|[Code](https://github.com/sennnnn/OpenVIS)|
|arXiv'24|[BriVIS](https://arxiv.org/abs/2401.09732)|[Code](https://github.com/sennnnn/OpenVIS)|

<!-- |arXiv'23|[Segment Everything Everywhere All at Once](https://arxiv.org/abs/2304.06718)|[Code](https://github.com/UX-Decoder/Segment-Everything-Everywhere-All-At-Once)|
|arXiv'23|[Exploring Open-Vocabulary Semantic Segmentation without Human Labels](https://arxiv.org/abs/2306.00450)|N/A|
|arXiv'23|[DaTaSeg](https://arxiv.org/abs/2306.01736)|N/A|
|ICCV'23|[Diffumask](https://arxiv.org/abs/2303.11681)|[Project](https://weijiawu.github.io/DiffusionMask/)|
|ICCV'23|[Guiding Text-to-Image Diffusion Model Towards Grounded Generation](https://arxiv.org/abs/2301.05221)|[Project](https://lipurple.github.io/Grounded_Diffusion/)|
|NeurIPS'23|[Uncovering Prototypical Knowledge for Weakly Open-Vocabulary Semantic Segmentation](https://arxiv.org/abs/2310.19001)|[Code](https://github.com/Ferenas/PGSeg)|
|arXiv'23|[Grounding Everything: Emerging Localization Properties in Vision-Language Transformers](https://arxiv.org/abs/2312.00878)|[Code](https://github.com/WalBouss/GEM)| -->

<a id="ack"></a>
## Acknowledgement

If you find our survey helpful, please consider citing our paper:

```bibtex
@article{survey-ovd-ovs,
  title={A survey on open-vocabulary detection and segmentation: Past, present, and future},
  author={Zhu, Chaoyang and Chen, Long},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  year={2024}
}
```
