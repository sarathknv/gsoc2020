# GSoC 2020 Final Code Submission

Project link — [MRI Registration using Deep Learning and Implementation of Thin-Plate Splines](https://summerofcode.withgoogle.com/projects/#6582514342166528)  
Organization — [INCF](https://www.incf.org/) and [DIPY](https://www.dipy.org/)

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
  
- Evaluation 1 Week
   - Tested the VoxelMorph model on a few T2-weighted volumes from the OASIS dataset.

- Week 5
  - Tried the VoxelMorph model for cross-modality registration (T1w static image and T2w moving images). Results weren't good.
 
- Week 6
  - Retrained the cross-modality registration model with better brain segmented T2 images. The brain mask was obtained using T1s insterad of T2s. So I rigid registered T1s with T2s and got the brain masks using T1s. Still the results were bad.
  - Implemented thin-plate splines. [GitHub repo](https://github.com/sarathknv/tps)

- Week 7
  - Read and understood the N3 paper. ([A Nonparametric Method for Automatic Correction
of Intensity Nonuniformity in MRI Data](https://www.nitrc.org/docman/view.php/6/880/sled.pdf))


- Week 8 + Evaluation 2 Week + Week 9
  - Tried the [SyN algorithm](https://www.dipy.org/documentation/1.1.1./examples_built/syn_registration_3d/#example-syn-registration-3d) for cross-modality registration. Results looked good but the ventricular regions were expanding.
  - Discussed doubts in N3 paper


- Week 10 and 11
  - Implemented N3 paper. But yet to be tested
  - Refashioned and cleaned the PR https://github.com/dipy/dipy/pull/2137
  - Tried the SyN algorithm with more iterations. Results got worse.

- Week 12
  - Blogs and codes
  - Documenting the whole work


## Blogs
- [Deep-learning-based 2D Deformable Image Registration with MNIST](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Deep-learning-based%202D%20Deformable%20Image%20Registration%20with%20MNIST.md)
- [Deep-learning-based 2D and 3D Affine Registration](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Deep-learning-based%202D%20and%203D%20Affine%20Registration.md)
- [Deep-learning-based 3D Deformable Registration of T1-weighted images](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Deep-learning-based%203D%20Deformable%20Registration%20of%20T1-weighted%20images.md)
- [DIPY NN Registration API](https://github.com/sarathknv/gsoc2020/blob/master/blogs/DIPY%20NN%20Registration%20API.md)
- [Deep-learning-based 3D Deformable Registration of T2-weighted images](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Deep-learning-based%203D%20Deformable%20Registration%20of%20T2-weighted%20Images.md)
- [Deep-learning-based 3D Cross-modality Registration](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Deep-learning-based%203D%20Cross-modality%20Registration.md)
- [Thin-plate Splines](https://github.com/sarathknv/gsoc2020/blob/master/blogs/Thin-Plate%20Splines.md)


## Codes
- Thin-plate splines - https://github.com/sarathknv/tps
- 3D Deformable Image Registration (VoxelMorph) - https://github.com/sarathknv/voxelmorph
- 2D Deformable Image Registration - https://github.com/dipy/dipy/pull/2137
- N3 Bias Field Correction - https://colab.research.google.com/drive/1eHAkHgMPDK4tlxihgMfK73FnaiQpdAR4?usp=sharing
