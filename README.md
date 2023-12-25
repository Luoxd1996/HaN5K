# <div align=center>HaN5K (data and labels are ready, looking for collaborators and funding support)</div>
<div align=center>HaN5K: A project to develop foundation models for structure delineation in head and neck radiotherapy based on 5K CT scans and 10K clinical volumetric organs</div>

# Details
* The goal of this repo is to build a very large-scale dataset (more than 5k 3D CT volumes with more than 45 organs-at-risk annotations) for automatic head and neck structure segmentation from contrast-enhanced or no-contrast radiotherapy CT scans.
 
* In the recent stage, we have collected 2000+ patients' CT scans and clinical radiotherapy planning structures (more than 10k+ 3D organ annotations). Then, we trained a [nnUNet](https://github.com/MIC-DKFZ/nnUNet) through partial label learning using the above image and labels to produce pseudo labels for the largest-scale publicly available head and neck cancer dataset ([RADCURE](https://www.cancerimagingarchive.net/collection/radcure/)). The clinical assessment results have shown the automatic delineation is clinically applicable with no and minor revisions for low-risk and several high-risk structures. Recently, the foundational model with massive labelled data has achieved very encouraging results in many natural and medical fields. But for head and neck structure segmentation, the progress is still slow, maybe due to a lack of high-quality data. Here, we first released the pseudo labels of [RADCURE](https://www.cancerimagingarchive.net/collection/radcure/) dataset to boost this topic research, where **3346 patients with 50 structure predictions** can be downloaded now.
  
* Note that this is a second development project based on the raw dataset, the copyright and license should be preserved by the raw [RADCURE](https://www.cancerimagingarchive.net/collection/radcure/) dataset. **In addition, this project is an extension of our previous work, [SegRap2023](https://segrap2023.grand-challenge.org/), so if you used our released structure predictions in your research, please cite the [SegRap2023](https://segrap2023.grand-challenge.org/) challenge report.** Moreover, this version of structure annotations was produced by [nnUNet](https://github.com/MIC-DKFZ/nnUNet) without further revision by radiation oncologists, so the quality is not good enough compared with the annotation of [SegRap2023](https://segrap2023.grand-challenge.org/), if you want to use it, please consider them as noisy labels. We are working hard to revise these predictions and attempt to release our collected multi-centre clinical radiotherapy structure planning. Please keep tuned.

* OARs names: 'Aorta', 'BrachialPlex_L', 'BrachialPlex_R', 'BronchialTree', 'Cochlea_L', 'Cochlea_R', 'ETbone_L', 'ETbone_R', 'Hippocampus_L', 'Hippocampus_R', 'IAC_L', 'IAC_R', 'Larynx', 'Mastoid_L', 'Mastoid_R', 'OralCavity', 'Submandibular_L', 'Submandibular_R', 'Thyroid', 'TympanicCavity_L', 'TympanicCavity_R', 'VestibulSemi_L', 'VestibulSemi_R', "EyeL", "EyeR", "LenL", "LenR", "OpticNerveL", "OpticNerveR", "OpticChiasm", "Pituitary", "BrainStem", "TemporalLobe_L", "TemporalLobe_R", "Cord_HaN", "ParotidL", "ParotidR", "MiddleEar_L", "MiddleEar_R", "TMJL", "TMJR", "MandibleL", "MandibleR", "Esophagus_HaN", "Trachea_HaN", "OralCavity_no_Gum", 'PharynxConst_S', 'PharynxConst_M', 'PharynxConst_I', Brain. Details can be found [here](https://segrap2023.grand-challenge.org/dataset/)                                      

* Pre-trained models based on our collected dataset can be downloaded here (Goole Driven](https://drive.google.com/file/d/1RRbM9ZuSbIUpvqJdC7v01FfAiP4eDJpM/view?usp=drive_link), [BaiduPan](https://pan.baidu.com/s/1kNaabCcZsnIRwYMV9Iw3gQ?pwd=uu2f)). These models were based on [nnUNetV1](https://github.com/MIC-DKFZ/nnUNet/tree/nnunetv1). Quick inference shell ```CUDA_VISIBLE_DEVICES=XXX nnUNet_predict -i "image_folder_path" -o "predict_folder_path" -t 301/302 -m 3d_fullres -f all --disable_tta```.
  
# DataSet
* Firstly, the raw dataset can be downloaded from [RADCURE](https://www.cancerimagingarchive.net/collection/radcure/) after accessing the download permission.
* Then, please contact Xiangde (luoxd1996 AT gmail DOT com) for the pseudo-label. Two steps are needed to download and access the pseudo-label: **1) using your google email to apply for the download permission ([Goole Driven](https://drive.google.com/file/d/1eQNk3dKaCDEfRYyDsR-cPTDyUrJlGrT4/view?usp=sharing), [BaiduPan](https://pan.baidu.com/s/1kJNjJ7s2svh9KK-94FY4HA?pwd=2023))**; **2) using your affiliation email to get the unzip password/BaiduPan access code**. We will get back to you within **two days**, **so please don't send them multiple times**. We just handle the **real-name email** and **your email suffix must match your affiliation**. The email should contain the following information:

```
    Name/Homepage/Google Scholar: (Tell us who you are.)
    Primary Affiliation: (The name of your institution or university, etc.)
    Job Title: (E.g., Professor, Associate Professor, Ph.D., etc.)
    Affiliation Email: (the password will be sent to this email, we just reply to the email which is the end of "edu".)
    How to use: (Only for academic research, not for commercial use or clinical application development.)
```
    
In addition, this work is still ongoing, the dataset will be extended to larger and more diverse (more patients, more organs, and more modalities, more clinical hospitals' data and MR Images will be considered to include future), any **suggestion**, **comment**, **collaboration**, and **GPUs sponsor** are welcome. 

# Acknowledgment and Statement
* This pseudo labels' copyright belongs to the **Healthcare Intelligence Laboratory** at **University of Electronic Science and Technology of China** and is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html), the raw CT data information please refer to [RADCURE](https://www.cancerimagingarchive.net/collection/radcure/).
* This project and dataset were designed for **open-available** academic research, **not** for clinical, commercial or other use. In addition, if you used it for your academic research, you are encouraged to release the code and the pre-trained model.

# Citation
It would be highly appreciated if you cite the following papers when using the pseudo-label:
```
@article{luo2023segrap2023,
  title={SegRap2023: A Benchmark of Organs-at-Risk and Gross Tumor Volume Segmentation for Radiotherapy Planning of Nasopharyngeal Carcinoma},
  author={Luo, Xiangde and Fu, Jia and Zhong, Yunxin and Liu, Shuolin and Han, Bing and Astaraki, Mehdi and Bendazzoli, Simone and Toma-Dasu, Iuliana and Ye, Yiwen and Chen, Ziyang and others},
  journal={arXiv preprint arXiv:2312.09576},
  year={2023}
}

@article{kazmierski2023multi,
  title={Multi-institutional prognostic modelling in head and neck cancer: evaluating impact and generalizability of deep learning and radiomics},
  author={Kazmierski, Michal and Welch, Mattea and Kim, Sejin and McIntosh, Chris and Rey-McIntyre, Katrina and Huang, Shao Hui and Patel, Tirth and Tadic, Tony and Milosevic, Michael and Liu, Fei-Fei and others},
  journal={Cancer Research Communications},
  pages={CRC--22},
  year={2023},
  publisher={AACR}
}
```
