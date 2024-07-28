# Leaf Instance Segmentation and Counting Challenge

## Introduction

The advancement in imaging and computer vision methods has facilitated non-invasive plant trait quantification, a key component of Precision Agriculture. The majority of plant traits are primarily derived from leaf-level analysis of plant images, underlining the importance of leaf instance segmentation tasks in Precision Agriculture. In this challenge, we propose a novel plant image dataset with leaf-level annotations to facilitate the development of accurate computer vision-based methods for leaf instance segmentation.

## Challenge Description

Recent datasets comprise model plants (such as Arabidopsis thaliana, maize, and sorghum) because of their brief life cycle and compact dimensions. In contrast, classical plants such as rice and wheat exhibit high inter-class and intra-class variances in leaf shape, size, etc. Current computer vision-based methods do not adequately address research on classical plants with complex growth patterns.

We see this as an opportunity and propose a large classical plant dataset with leaf-level annotations to bridge the gap. Unlike common target objects such as tables and chairs, leaves exhibit stochasticity with respect to their shapes, structures, and appearances corresponding to different plant species. The novel dataset in this challenge, along with the algorithms, will facilitate computer vision research on non-rigid objects with a high degree of self-similarity and self-occlusions.

## Dataset

The dataset is split into two distinct plant species: rice image data and wheat image data. These images were collected at the phenomics facility of the Indian Agricultural Research Institute. The dataset comprises top-view single plant images acquired at different growth stages. These images have been manually annotated to generate masks for leaf instances, both non-occluded and occluded.

For each plant image, the leaf count is provided in a CSV file. These annotations have been manually assessed by a plant scientist at the Indian Agricultural Research Institute.

To download the dataset, first register for the challenge and upload the signed EULA form. We will send the details to access the dataset.

## Tasks & Evaluation Metrics

### Leaf Instance Segmentation

This task involves generating leaf instances automatically for plant images. Participants have to submit a zip file containing predicted leaf instances for the test dataset. The metric used to rank the submissions is Symmetric Best Dice (SBD).

### Leaf Counting

In this task, participants are asked to regress leaf counts directly from plant images without instance segmentation. The regression results will be evaluated with the Difference in Count (DiC) metric, which denotes the absolute value of the difference between the predicted and ground truth leaf counts.

## Result Submission

To submit the predicted results for evaluation, result reproduction, and ranking, participants need to send an email that includes all the following items to [leafinspect@gmail.com](mailto:leafinspect@gmail.com):

1. A link to their GitHub repository containing all the codes to reproduce the proposed algorithm(s).
2. Clear instructions to reproduce the computing environment and run their model. This should take the shape of a script that only requires changing the path to the testing data to be executed.
3. A description of the methods used to produce the submitted results.

The submission format for the tasks is outlined below:

### Leaf Instance Segmentation Task

- A zip file containing results (predicted label images) for the test data. 
- In the predicted label image, the labels should be consecutive numbers, with the lowest label as background (same for ground truth labeled images).

### Leaf Counting Task

- A CSV file listing test image names and the number of leaves.

## Instructions for Running the Code

### Prerequisites

- Python 3.10.0
- OpenCV 4.10.0.82
- Matplotlib 3.7.5
- NumPy 1.26.4
- Pandas 2.2.2
- Pillow 9.5.0
- TQDM 4.66.4
- PyTorch 2.1.2
- Torchvision 0.16.2
- Scikit-learn 1.2.2
- Segmentation Models PyTorch 0.3.3
- Albumentations 1.4.0

### Installation

1. Clone the repository:
    ```bash
    go to the folder where my challenge details are there.
    git clone ---My github link is https://github.com/shravankoninti/ICPR_2024_Leaf_Inspect
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

### Training and Evaluation

1. Update the paths in the `CFG` class in the provided scripts to match your data locations.
2. Run the leaf instance segmentation training script:
    ```bash
    Leaf_Instance_Segmentation_Task.ipynb

    This code gives the all images predictions in predictions folder
    ```
3. Run the leaf counting training script:
    ```bash
    Leaf_Counting_Task.ipynb
    ```
4. Predict leaf counts on the test set:
    ```bash
    Leaf_Counting_Task.ipynb  - this code gives the predictions file
    ```

### Result Evaluation

1. Predictions for the test set will be saved in the `predictions` folder.
2. For leaf counting, the results will be saved in `leaf_count_predictions.csv`.

### Example Submission

For the leaf instance segmentation task, create a zip file of the `predictions` folder and email it to [leafinspect@gmail.com](mailto:leafinspect@gmail.com).

For the leaf counting task, send the `leaf_count_predictions.csv` file along with your GitHub repository link and the description of your methods.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We would like to thank the Indian Agricultural Research Institute for providing the dataset and annotations.

For any queries or issues, please contact [leafinspect@gmail.com](mailto:leafinspect@gmail.com).
