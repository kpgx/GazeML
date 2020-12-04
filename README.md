# GazeML

### parent :https://github.com/swook/GazeML

A deep learning framework based on Tensorflow for the training of high performance gaze estimation.

*Please note that though this framework may work on various platforms, it has only been tested on an Ubuntu 16.04 system.*

*All implementations are re-implementations of published algorithms and thus provided models should not be considered as reference.*

This framework currently integrates the following models:

## ELG

Eye region Landmarks based Gaze Estimation.

> Seonwook Park, Xucong Zhang, Andreas Bulling, and Otmar Hilliges. "Learning to find eye region landmarks for remote gaze estimation in unconstrained settings." In Proceedings of the 2018 ACM Symposium on Eye Tracking Research & Applications, p. 21. ACM, 2018.

- Project page: https://ait.ethz.ch/projects/2018/landmarks-gaze/
- Video: https://youtu.be/cLUHKYfZN5s

## DPG

Deep Pictorial Gaze Estimation

> Seonwook Park, Adrian Spurr, and Otmar Hilliges. "Deep Pictorial Gaze Estimation". In European Conference on Computer Vision. 2018

- Project page: https://ait.ethz.ch/projects/2018/pictorial-gaze

*To download the MPIIGaze training data, please run `bash get_mpiigaze_hdf.bash`*

*Note: This reimplementation differs from the original proposed implementation and reaches 4.63 degrees in the within-MPIIGaze setting. The changes were made to attain comparable performance and results in a leaner model.*

## Installing dependencies

#### Note
this is based on tensorflow 1 library, which only supported until python 3.7
So best way to install this is create a python 3.7 env with conda and follow the instructions.

```
create a python 3.7 env with conda
activate the conda envirenment
pip install tensorflow==1.15.4
python3 setup.py install
```

## Getting pre-trained weights
To acquire the pre-trained weights provided with this repository, please run:
```
    bash get_trained_weights.bash
```

## Running the demo
To run the webcam demo, perform the following:
```
    cd src
    python3 elg_demo.py
```

To see available options, please run `python3 elg_demo.py --help` instead.

## Structure

* `datasets/` - all data sources required for training/validation/testing.
* `outputs/` - any output for a model will be placed here, including logs, summaries, and checkpoints.
* `src/` - all source code.
    * `core/` - base classes
    * `datasources/` - routines for reading and preprocessing entries for training and testing
    * `models/` - neural network definitions
    * `util/` - utility methods
