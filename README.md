# inception-retrain
Standalone version of Tensorflow Inception Retrain. Google Codelabs can be found [here](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets).

This example downloads a pre-trained version of the inception model and re-trains the last layers to recognize custom categories of images. 

In particular we will use pictures of Ramūnas Karbauskis and Aurelijus Veryga

## Steps

### 0. Install tensorflow

```$ pip install tensorflow```
or
```$ conda install tensorflow```

### 1. Retrain Inception

Run the following command (edit paths and training steps as you please)
```
python ./retrain.py \
--bottleneck_dir=./tf_files/bottlenecks \
--how_many_training_steps 500 \
--model_dir=./tf_files/inception \
--output_graph=./tf_files/retrained_graph.pb \
--output_labels=./tf_files/retrained_labels.txt \
--image_dir ./tf_files/zali
```

read more about their content [here](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets).


### 2. Predict the label of an image using Inception

Let's test the re-training on a karbauskis image:
```
python ./label_image.py ./tf_files/ar_tikrai_ramunas.jpg
```

you should get something like:
```
karbakrauskis (score = 0.93071)
veryga (score = 0.00595)
```
