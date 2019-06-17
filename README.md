<h1
 align="center">Stanford Cars with Fast.ai</h3>

## 📝 Table of Contents

- [TL; DR](#tldr)
- [What I did](#what_i_did)

## 🏃‍ TL; DR on how to run the code <a name = "tldr"></a>

- If you're **not** logged into kaggle via CLI, please download: https://www.kaggle.com/jutrera/stanford-car-dataset-by-classes-folder
- Put the zipped folder inside the directory 'data-kaggle' provided and unzip it (including cars_data.zip)
- Open 'Stanford-Cars-50-SM' and run each cell until the end
- The results will be provided on the last cell `learn.validate(data_test.train_dl)`
- If you're logged in into kaggle via CLI, run command `kaggle datasets download jutrera/stanford-car-dataset-by-classes-folder` to download the zipped file and unzip both the file and cars_data.zip
- Thank you for the judges!

## 🤔 What I did<a name = "what_i_did"></a>

**✔️ Here's what I did and worked:**

- Used the fast.ai library built on top of pytorch
- Implemented 1-cycle training policy for fitting pre-unfreezing, so only the last layer gets trained
- Cropped train images using the bounding box
- Created multiple crops of the same image in different parts (left, middle, right) to enhance accuracy due to limited data
- Implemented mixup
- Implemented dropout of .1
- Implemented AdamW optimizer, in replacement of Adam
- Image transformation to further add data (flip, rotate)
- Implemented test-time augmentation every time 1-cycle fitting finished
- Building up image sizes over time, starting from **224px x 224px** to **280px x 280px** to **336px x 336px** and finally **400px x 400px**
- Testing on images that are higher in resolution helped boosting accuracy **460px \* 460 px**

**❌ Here's what failed for me:**

- Dropout of .5 and over
- Image resize without squishing
- **244px x 244px** image size for training
- Warp image transformation

