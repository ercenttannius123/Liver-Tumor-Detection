## Automatic Liver & Tumor Segmentation on CT Scan Images 

📋 Overview 


This project develops an automated liver and tumor segmentation system from abdominal CT scan images using the U-Net deep learning architecture. The model is trained on the publicly available LiTS (Liver Tumor Segmentation) dataset and evaluated using standard medical image segmentation metrics.


Manual segmentation of liver tumors by radiologists is time-consuming, labor-intensive, and subject to inter-observer variability. This study proposes an automated deep learning approach to assist clinical decision-making by accurately delineating liver and tumor regions from CT scans. 


📊 Results 
  
  
Accuracy        : 0.9939


Precision       : 0.9433


Recall          : 0.9630

Specificity     : 0.9960

Dice Score      : 0.9531  

Jaccard Index   : 0.9104


Preprocessing Pipeline


Raw NIfTI (.nii)

     
      ↓
      
Extract 2D axial slices (nibabel)
     
      
      ↓

      
HU Windowing → clip [-150, +250] HU
     
      
      ↓

      
Normalize → [0, 1]
     
      
      ↓

      
Mask Binarization → label > 0 = 1 (liver + tumor)
     
      
      ↓

      
Resize → 128 × 128 pixels
     
      
      ↓

      
Tensor (1, 128, 128) → PyTorch model input
