
# Snapture - A Novel Neural Architecture for Combined Static and Dynamic Hand Gesture Recognition
This repository contains the source code used for developing the experiments of the paper titled: 
[Snapture - A Novel Neural Architecture for Combined Static and Dynamic Hand Gesture Recognition](https://arxiv.org/abs/2205.15862) (pre-print) by Hassan Ali, Doreen Jirak and Stefan Wermter. The study was conducted in the Knowledge Technology (WTM) group at the University of Hamburg.


## Datasets
### GRIT Robot Commands Dataset
This dataset was recorded at the Knowledge Technology (WTM) group at the University of Hamburg and can be requested [here](https://www.inf.uni-hamburg.de/en/inst/ab/wtm/research/corpora.html).

### Montalbano Co-Speech Dataset
This dataset was recorded as part of the ChaLearn Looking at People Challenge and can be downloaded from [here](https://chalearnlap.cvc.uab.cat/dataset/12/description/).

## Usage
Script `1) create_sequence_frames` converts the video source of the Montalbano dataset into frames and requires the following parameters:
```Parameters
path: the path to Montalbano dataset in the video source format (.mp4 only)
target_path: an existing folder in which the extracted frames can be stored
```
Script `2) create_montalbano_segments` creates gesture isolated sequences for the Montalbano dataset and requires the following parameters:
```Parameters
path: the path to Montalbano dataset in the frames format (as extracted in step #1)
```

Script `3) create_differential_images` applies the differential images algorithm to the isolated gesture sequences for the Montalbano and GRIT datasets and requires the following parameters:
```Parameters
path: the path to isolated gesture sequences
target_path: an existing folder in which the differential images output frames can be stored
```

Script `4) extract_kendon_stroke` extracts the Kendon stroke from the isolated gesture and requires the following parameters:
```Parameters
path: the path to frame seuqnces (output of step #1)
target_path: an existing folder in which the output frames can be stored
```

Script `5) extract_skin` extracts the hand pose for each gesture sequence and requires the following parameters:
```Parameters
kendon_path: the path to frame extracted kendon strokes (output of step #4)
frame_path: the path to the dataset in the frame format (output of step #2)
```

Script `6) grit_experiment` runs the GRIT dataset experiment and requires the following parameters:
```Parameters
path: the path to output of the differential images algorithm (output of step #3)
kendon_path: the path to frame extracted kendon strokes (output of step #4)
```

Script `7) montalbano_experiment` runs the GRIT dataset experiment and requires the following parameters:
```Parameters
path: the path to output of the differential images algorithm (output of step #3)
kendon_path: the path to frame extracted kendon strokes (output of step #4)
training_labels.csv: training labels of the Montalbano dataset
validation_labels.csv: validation labels of the Montalbano dataset
test_labels.csv: test labels of the Montalbano dataset
```

## Citation
To cite our paper, you can copy the following into your `.bib` file
```BibTeX
@Article{ali2022,
author = {Ali, Hassan and Jirak, Doreen and Wermter, Stefan},
year = {2022},
month = {05},
title = {Snapture -- A Novel Neural Architecture for Combined Static and Dynamic Hand Gesture Recognition},
doi = {10.48550/arXiv.2205.15862}
}
```

## Contact
Hassan Ali hassan.bi.ali1@gmail.com

