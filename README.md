## Comparing SimpleCNN, SimpleSegNet, and U-Net for Liver and Tumor Segmentation in CT Scan Images

📋 Overview 


This project develops an automated liver and tumor segmentation system from abdominal CT scan images using the U-Net deep learning architecture. The model is trained on the publicly available LiTS (Liver Tumor Segmentation) dataset and evaluated using standard medical image segmentation metrics.


Manual segmentation of liver tumors by radiologists is time-consuming, labor-intensive, and subject to inter-observer variability. This study proposes an automated deep learning approach to assist clinical decision-making by accurately delineating liver and tumor regions from CT scans. 


📊 Results 
  
  
Accuracy        : 0.998155


Precision       : 0.984693


Recall          : 0.987404

Specificity     : 0.998915

Dice Score      : 0.986047  

Jaccard Index   : 0.972478


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
