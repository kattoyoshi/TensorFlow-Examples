# Tensorflow Examples
This repository shows basic code examples of the tensorflow.  
It includes basic operations, MLP and CNN.

## 1. Tensorflow Basic
Although this section is explained in tf1, most of the concepts are the same in tf2.

- Overview and Tensors [[ipynb]](notebooks_tf1/1_TensorflowBasic/1_Overview_and_Tensors.ipynb)
- Basic Operations (Low Level API) [[ipynb]](notebooks_tf1/1_TensorflowBasic/2_BasicOperation.ipynb)
- Basic Operations (Eager Execution) [[ipynb]](notebooks_tf1/1_TensorflowBasic/3_BasicOperation_Eager.ipynb)
- Scope [[ipynb]](notebooks_tf1/1_TensorflowBasic/4_Scope.ipynb)
- Dataset API [[ipynb]](notebooks_tf1/1_TensorflowBasic/5_DatasetAPI.ipynb)
- TFRecord [[ipynb]](notebooks_tf1/1_TensorflowBasic/6_TFRecord.ipynb)

## 2. Neural Network
__MNIST Classification with MLP__
- tf1
  - Low Level API (tf.nn API) [[ipynb]](notebooks_tf1/2_NeuralNetwork/1_LowLevelAPI.ipynb)
  - High Level API (tf.layers API) [[ipynb]](notebooks_tf1/2_NeuralNetwork/2_LayersAPI.ipynb)
  - High Level API (tf.keras API w/ Eager) [[ipynb]](notebooks_tf1/2_NeuralNetwork/2_KerasWithEager.ipynb)
- tf2
  - Built-in training/eval loops [[ipynb]](notebooks_tf2/2_NeuralNetwork/1_BuiltInTrainingLoops.ipynb)
  - Customized setp-by-step loops [[ipynb]](notebooks_tf2/2_NeuralNetwork/2_CustomizedTrainingLoops.ipynb)
  - Training/eval loops from scratch [[ipynb]](notebooks_tf2/2_NeuralNetwork/3_TrainingLoopsFromScratch.ipynb)

## 3. Convolutional Neural Network
__MNIST Classification with CNN__
- tf1
  - Low Level API (tf.nn API) [[ipynb]](notebooks_tf1/3_ConvolutionalNetwork/1_LowLevelAPI.ipynb)
  - High Level API (tf.layers API) [[ipynb]](notebooks_tf1/3_ConvolutionalNetwork/2_LayersAPI.ipynb)
  - High Level API (tf.keras API w/ Eager) [[ipynb]](notebooks_tf1/3_ConvolutionalNetwork/2_KerasWithEager.ipynb)
- tf2
  - Built-in training/eval loops [[ipynb]](notebooks_tf2/3_ConvolutionalNetwork/1_BuiltInTrainingLoops.ipynb)
  - Customized setp-by-step loops [[ipynb]](notebooks_tf2/3_ConvolutionalNetwork/2_CustomizedTrainingLoops.ipynb)
  - Training/eval loops from scratch [[ipynb]](notebooks_tf2/3_ConvolutionalNetwork/3_TrainingLoopsFromScratch.ipynb)

## 4. Environments
- Install Docker and Nvidia Docker to your host
- Case: tf1
  - Use `environments/tf1/Dockerfile` to build a docker image
- Case: tf2
  - Use `environments/tf2/Dockerfile` to build a docker image

```bash
$ cd Docker

# {image_name}, {tag_name} and {container_name} shoule be define by yourself
$ docker build -t {image_name}:{tag_name} .
```
If you want to use a container as jupyter notebook server, run the container like bellow.

```bash
# Docker (<19.03) with NVIDIA Docker v2
$ docker run --runtime=nvidia -it --rm -p 8888:8888 --name {conteiner_name} -v {host_dir}:{docker_dir} {image_name}:{tag_name} /bin/bash

# Docker (>=19.03) with nvidia-container-toolkit
$ docker run --gpus 1 -it --rm -p 8888:8888 --name {conteiner_name} -v {host_dir}:{docker_dir} {image_name}:{tag_name} /bin/bash

# If you want to use jupyter notebook, run command bellow
$ jupyter notebook --ip=0.0.0.0 --allow-root
```

If you want to use a container as tensorboard server, run the container like bellow.

```bash
$ docker run -it --rm -p 6006:6006 --name {conteiner_name} -v {host_dir}:{docker_dir} {image_name}:{tag_name} /bin/bash
```
