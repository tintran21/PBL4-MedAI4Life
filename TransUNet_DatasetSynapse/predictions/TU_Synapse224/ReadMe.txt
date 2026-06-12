### 📁 Directory Structure & Relationship

During the lifecycle of this project, two main directories are utilized. The testing phase directly depends on the outputs generated during the training phase.

* **`/model/` (Training Checkpoints)**
* **Contents:** This directory stores the trained weights (the "brain") of the TransUNet models. It contains very large checkpoint files, such as `best_model.pth` and various `epoch_x.pth` files. It also includes a `log` folder to track training progress.
* **Relationship:** The files stored here act as the source. The testing script calls and loads a specific `.pth` file from this folder to perform inference on unseen data.


* **`/predictions/` (Test Outputs)**
* **Contents:** This directory stores the final inference results generated after evaluating the model. It contains volumetric medical data saved in the `.nii.gz` format. Specifically, it holds the original input images (`_img.nii.gz`), the ground truth masks (`_gt.nii.gz`), and the actual predictions made by the model (`_pred.nii.gz`).
* **Relationship:** This folder is the destination. The files inside are actively generated *by using* the pre-trained weights fetched from the `/model/` directory.