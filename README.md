# SAFER Activities Dataset Code Repository

This repository includes scripts for preprocessing videos to generate pickle files and training.

Download the wheelchair keypoints dataset for human pose estimation through [this link](https://huggingface.co/datasets/SAFER-Activities/SAFER-Activities/blob/main/wheelchair_keypoints/wheelchair_keypoints_dataset.zip).

Download the pickle files for training models using keypoint information through [this link](https://huggingface.co/datasets/SAFER-Activities/SAFER-Activities/blob/main/pose_bboxes/3d_keypoints_pickle_ntu_format.zip).

## Repository Structure

- `preprocessing/` — Generate pickle files with 2D keypoints from raw videos (YOLOv8x + ViTPose-H)
- `preprocessing/3d_pose_lifting/` — Lift 2D keypoints to 3D using MotionAGFormer
- `keypoints_train/` — Train and evaluate skeleton-based models (1D-CNN)
- `inference/pyskl/` — Train and evaluate GCN-based skeleton models (DG-STGCN, MSG3D, STGCN++, PoseC3D) with 2D and 3D pose
- `rgb/feature_extraction/` — Extract bbox-cropped clips and frozen CLIP, DINOv3, and VideoMAE features
- `rgb/training/` — Train and evaluate RGB-only and multimodal fusion models (5 fusion strategies x 3 backbones)
- `rgb/external_eval/` — Cross-dataset evaluation on ImViA fall detection dataset (RGB & fusion models)
- `inference/` — Sliding-window inference and evaluation on the SAFER-Activities test sets, including external fall datasets
- `docker/` — Dockerfile and container run scripts

## License

This dataset is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).
This means you can share and adapt the material for any non-commercial purpose as long as you provide appropriate credit, include a link to the license, and indicate if changes were made. You must also share any adaptations under the same license.
