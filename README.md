# GSoC 2020 Final Code Submission

## Weekly Progress  

- Community Bonding + Week 1
  - Developed a POC for non-rigid image registration using the MNIST dataset. [Colab notebook](https://colab.research.google.com/drive/1fTzz1aT2sb8oAXRO1-dr6O_IR6dof36e?usp=sharing)  
  - Made a pull request for the same. PR: https://github.com/dipy/dipy/pull/2137
  - Cleaned the code and refashioned the dipy.nn.registration API
  - Added docstrings and comments.

- Week 2
  - Implemented the VoxelMorph model (CVPR 2018). But yet to be trained. [Paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Balakrishnan_An_Unsupervised_Learning_CVPR_2018_paper.pdf)  
   - Implemented and trained 2D and 3D deep learning models for unsupervised affine registration. Similar to [AIRNet](https://arxiv.org/abs/1810.02583) but trained in an unsupervised fashion like the VoxelMorph model.

- Week 3
  - Tested the [VoxelMorph model](https://openaccess.thecvf.com/content_cvpr_2018/papers/Balakrishnan_An_Unsupervised_Learning_CVPR_2018_paper.pdf) on the sample data (150 T1-weighted images) that was provided. The results were very good.  
  - Cleaned the code and tested the new dipy.nn.registration API that was refashioned in the first week. [Colab notebook](https://colab.research.google.com/drive/1YnGZX43_UzrtWnqI8ZkzLjvprc2kDGk9?usp=sharing)  

- Week 4  
  - Added tests and tutorial to the PR. https://github.com/dipy/dipy/pull/2137
  
- First Evaluation Week
   - Tested the VoxelMorph model on a few T2-weighted volumes from the OASIS dataset.

- Week 5
  - Tried the VoxelMorph model for cross-modality registration (T1w static image and T2w moving images).
 
- Week 6


- Week 7


- Week 8


- Week 9


- Week 10


- Week 11

- Week 12


## Blogs
- Deep-learning-based 2D Deformable Image Registration with MNIST
- Deep-learning-based 2D and 3D Affine Registration
- Deep-learning-based 3D Deformable Registration with T1-weighted images
- DIPY Registration API
- Deep-learning-based 3D Deformable Registration with T2-weighted images
- Deep-learning-based 3D Cross-modality Registration
- Thin-plate Splines
- Cross-modality Registration using SyN Algorithm
- N3 Bias Field Correction

## Colab Notebooks


## Codes
Thin-plate splines
