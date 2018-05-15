# Generative Grasping CNN (GG-CNN)

The GG-CNN is a lightweight, fully-convolutional network which predicts the quality and pose of antipodal grasps at every pixel in an input depth image.  The lightweight and single-pass generative nature of GG-CNN allows for fast execution and closed-loop control, enabling accurate grasping in dynamic environments where objects are moved during the grasp attempt.

This repository contains the implementation of the Generative Grasping Convolutional Neural Network (GG-CNN)from the paper:

**Closing the Loop for Robotic Grasping: A Real-time, Generative Grasp Synthesis Approach**

*[Douglas Morrison](http://dougsm.com), [Jürgen Leitner](http://juxi.net), [Peter Corke](http://petercorke.com)*

Robotics: Science and Systems (RSS) 2018

[arXiv](https://arxiv.org/abs/1804.05172) | [Video](https://www.youtube.com/watch?v=7nOoxuGEcxA)

If you use this work, please cite:

```text
@article{morrison2018closing, 
	title={Closing the Loop for Robotic Grasping: A Real-time, Generative Grasp Synthesis Approach}, 
	author={Morrison, Douglas and Leitner, Jürgen and Corke, Peter}, 
	booktitle={Robotics: Science and Systems (RSS)}, 
	year={2018} 
}
```

**Contact**

Any questions or comments contact [Doug Morrison](mailto:douglas.morrison@hdr.qut.edu.au).

## Installation

This code was developed with Python 2.7 on Ubuntu 16.04.  Python requirements can be found in `requirements.txt`.

## Pre-trained Model

The pre-trained Keras model used in the RSS paper can be downloaded by running `download_pretrained_ggcnn.sh` in the `data` folder.

## Training

To train your own GG-CNN:

1. Download the [Cornell Grasping Dataset](http://pr.cs.cornell.edu/grasping/rect_data/data.php) by running `download_cornell.sh` in the `data` folder.
2. Run `generate_dataset.py` to generate the manipulated dataset.  Dataset creation settings can be specified in `generate_dataset.py`.
3. Specify the path to the  `INPUT_DATASET` in `train_ggcnn.py`.
4. Run `train_ggcnn.py`. 
5. You can visualise the detected grasp outputs and evaluate against the ground-truth grasps of the Cornell Grasping Dataset by running `evaluate.py`

## Running on a Robot

Our ROS implementation for running the grasping system on a Kinva Mico arm can be found in the repository [https://github.com/dougsm/ggcnn_kinova_grasping](https://github.com/dougsm/ggcnn_kinova_grasping).