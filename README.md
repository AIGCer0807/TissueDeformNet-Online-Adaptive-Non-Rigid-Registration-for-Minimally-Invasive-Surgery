# TissueDeformNet-Online-Adaptive-Non-Rigid-Registration-for-Minimally-Invasive-Surgery
A novel framework for non-rigid registration in minimally invasive surgery, leveraging overlap-aware hierarchical matching and online adaptation to handle significant tissue deformations and partial overlaps. The method achieves robust and accurate performance without additional training data, validated on both artificial and clinical datasets.

![image](https://github.com/AIGCer0807/TissueDeformNet-Online-Adaptive-Non-Rigid-Registration-for-Minimally-Invasive-Surgery/blob/main/picture/%E8%87%AA%E7%84%B6%E5%BD%A2%E5%8F%98%E9%87%8D%E5%8F%A0%E5%8C%BA%E5%9F%9F(%E5%8D%8E%E8%A5%BF)20241127.tif)


# Fig.1
![fig1](https://github.com/user-attachments/assets/67807296-623f-4c44-bad9-61ec0c7c8a3a)

Fig. 1. Visualization of tissue deformation and partial overlaps in minimally invasive surgery. Different frames from endoscopic video demonstrate significant non-rigid deformations and varying degrees of overlap caused by continuous laparoscope movement during surgical procedures.

# Fig.2
![fig2](https://github.com/user-attachments/assets/3f9b03ac-9dc1-4bcd-9eab-c227eb84935a)

Fig. 2. Overview of the proposed OANRM framework: (a) Workflow illustration showing the non-rigid registration process from source point cloud through warp function estimation to final registered result. (b) Two-phase framework architecture: Training phase - HMNet trained with three supervised losses, taking source and target point clouds as input to estimate overlapping regions (green: overlap, red: non-overlap) and predict correspondences. Inference phase -online fine-tuning with three unsupervised losses followed by TDDP module for predicting non-overlapping region deformation based on displacement vectors from overlapping areas

# Fig.3
![fig3](https://github.com/user-attachments/assets/199a0081-2020-43c5-b91e-2277ce34bb6e)

Fig. 3. Architecture of the HMNet: (a) Multi-level feature extraction and matching pipeline, showing PAConv feature extraction (blue), mask correspondence module (yellow), and upsampling mixing module (purple) to predict overlapping regions and correspondences. The numbers indicate feature dimensions at each level. (b) Mask correspondence module design for overlap detection and correspondence prediction using similarity matrices. (c) TopMLP component structure for similarity-based feature selection.

# Fig.4
![fig4](https://github.com/user-attachments/assets/c000b8c6-2be1-45c3-ae17-4b6020358bcf)

Fig. 4. Performance comparison on the Artificial Deformation Dataset: Models trained with different overlap ratios (75%, 80%, 85%, 90%, 95%, and mixed dataset) and evaluated on test sets with varying overlap ratios (75%-95%). The mixed training dataset consistently achieves the lowest EPE across all test scenarios.

# Fig.5
![fig5](https://github.com/user-attachments/assets/9facf0c0-2e12-4e5a-ab6a-2fde9cf227b5)

Fig. 5. Comparison of registration results with additional rigid transformations on the Artificial Deformation Dataset. The error maps are color-coded with blue indicating low registration error and red indicating high error (color bar range: 0-5.0mm). For each scenarios (a-c): Top row shows source, target, ground truth, and our OANRM results including intermediate HMNet predictions and final registration; Bottom row presents results from state-of-the-art methods (GBCPD, BiFlow, LNDP, FLOT, SyNoRiM, and NSFP). 

# Fig.6
![fig6](https://github.com/user-attachments/assets/f6ea724a-4e8b-4e2a-b9fd-e42e440a2dcf)

Fig. 6. Algorithm performance comparison under different conditions: (a) EPE vs. overlap ratios without rigid transformation, (b) EPE vs. overlap ratios with rigid transformation, (c) Accuracy vs. tolerance errors without rigid transformation (75% overlap), (d) Accuracy vs. tolerance errors with rigid transformation (75% overlap).

# Fig.7
![fig7](https://github.com/user-attachments/assets/f09156c8-4a52-4500-8b83-4c6eb116f612)

Fig. 7. Qualitative comparison on real surgical data from endoscopic videos. First row: registration results between frames 322-332; Second row: registration results between frames 200-207. Red boxes highlight regions with significant deformation and partial overlap. Our method better preserves anatomical structures and texture details compared to state-of-the-art approaches in these challenging surgical scenarios.

# Fig.8
![fig8](https://github.com/user-attachments/assets/31a8b6f8-0c08-4181-91a0-1e76326a0ac0)

Fig. 8. Registration results on the StereoMIS dataset captured by da Vinci Xi surgical system. First row: registration between frames 892-1269 showing liver tissue alignment; Second row: registration between frames 2167-2188 demonstrating preservation of anatomical structures. Red boxes highlight regions where our method achieves superior preservation of both geometric and texture details compared to state-of-the-art methods in these robotic-assisted surgical scenarios.



