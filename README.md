# Eluvio-ML-challenge
Eluvio DS/ML challenge 2021

# Task
Optimize the scene segmentation given features for each shot, the scene transition ground truth, and preliminary scene transition predictions

# Approach
Using the vectors given for the place, cast, action and audio, we compute the pairwise distances. Then, we take the mean of all the distances matrices. Shots within the same scene should have low distance value, and shots in different scene would have higher values.

# Results for baseline code.
```
$ python evaluate_sceneseg.py ../data
number of IMDB IDs: 64
Scores: {
    "AP": 0.4418872028438688,
    "mAP": 0.45644015956781614,
    "Miou": 0.4541480053002174,
    "Precision": 0.2761656092479825,
    "Recall": 0.7473442326299846,
    "F1": 0.39309552999275693
}
```

Results with the approach to consider pairwise distances.
```
$ python evaluate_sceneseg.py ../output/
number of IMDB IDs: 64
Scores: {
    "AP": 0.43432948488202827,
    "mAP": 0.456352123550865,
    "Miou": 0.46784292015853995,
    "Precision": 0.5318621161859483,
    "Recall": 0.35784778487868607,
    "F1": 0.4101209096486932
```
