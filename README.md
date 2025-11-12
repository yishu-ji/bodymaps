# Emotion and Body
## Advanced Psychological Statistics (Tsinghua University, 23 Fall)

This is a **naive demo** of a course project for **Advanced Psychological Statistics**. This source code is provided as a reference for my peer classmates who have little experience in Python to preprocess the large-scale datasets. Should you have any questions, please feel free to contact me. My email in use could be found in my profile.

This demo perform **dimensionality reduction based on mapping pixels to body parts**. It mainly uses rectangular segmentation and clustering of pixels in an image.

The main files include:

1. **mask_coordinate.py**
2. **coordinate_transform.py**
3. **dim_reduction.py**
4. **in_mask.csv** (source: generated from MATLAB code provided by the TA)
5. **Emotion.csv** (source: the original downloaded dataset; here, *Anger.csv* is used as an example)
6. **Example segmentation method.jpg**

The main steps are as follows:

1. Run **mask_coordinate.py**.

   * Hover the mouse over any point in the image to display its *x* and *y* coordinates.
   * Click on a point to print its *x–y coordinates*, *mask_index* (from 1 to 522×171), and *data_index* (from 1 to 50,364) in the terminal.
2. Run **coordinate_transform.py**.

   * Remember to replace the initial **Emotion** with the **corresponding emotion word**.
   * This step classifies pixels based on their coordinates (refer to *Example segmentation method.jpg*).
   * You may *adjust the classification criteria based on your understanding and the coordinate information obtained in Step 1*.
   * After completion, a new file **modified_in_mask.csv** will be generated, which stores the label (e.g., arms, legs, etc.) corresponding to each pixel.
3. Run **dim_reduction.py**.

   * Based on the labels from Step 2, this script finds the corresponding pixels in the original data file (**Emotion.csv**) and computes their arithmetic mean.
   * After completion, a new file **Emotion_reduced.csv** will be created. Each row corresponds to one participant (ordered from top to bottom as Subject 1, 2, 3, ...).
   * The first column is the emotion, and the following columns are the averaged values for each body part label.
   * The resulting file format can be directly opened and analyzed in SPSS.
   * This step may take some time—please be patient.


这是一个为**清华大学“高级心理统计”课程**专题大作业搭建的**数据处理管道**。我将这份源代码开源分享，旨在帮助对 Python 经验较少的同学进行大规模数据集的预处理。如果您有任何问题，欢迎随时联系我。我的常用邮箱可以在个人主页中找到
本管道*根据像素对应的身体部位进行数据降维*，主要是用矩形在图片上进行像素的分割和聚类

主要包括文件：
    1. mask_coordinate.py
    2. coordinate_transform.py
    3. dim_reduction.py
    4. in_mask.csv（来源：助教提供的matlab代码生成）
    5. Emotion.csv（来源：原始下载数据，这里只以Anger.csv为例）
    6. 本样例的划分方式.jpg

主要步骤如下：
    1. 运行**mask_coordinate.py**文件，鼠标停留图片某点，会显示该点的x和y坐标；或者点击图片上某一点，会在终端输出该点的xy坐标，mask_index（1到522乘以171）和data_index（1到50364）
    2. 运行**coordinate_transform.py**文件，请记得把最开始的**Emotion**换成**对应的情绪词**，这里会根据坐标位置对像素点进行归类（请参考**本样例的划分方式.jpg**）。这里可以*根据你自己的理解和1.中看到的坐标信息调整分类标准*。这一步完成后会新增一个**modified_in_mask.csv**文件，保存了各个像素点对应的部位label（arms，legs...）
    3. 运行**dim_reduction.py**文件，这里会根据2.中的label，在原始的数据文件(**Emotion.csv**)找到对应的像素点，求取它们的算术平均值。这一步完成后会新增一个**Emotion_reduced.csv**文件，这个文件每一行为每个被试的数据(从上到下被试编号1，2，3...)，第一列为情绪，后几列为部位label对应的数值。这样的输出结果的格式支持直接在spss里打开并进行分析。这一步可能要花一些时间，不要着急～
