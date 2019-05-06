# Tensorflow Examples
This repository shows basic code examples of the tensorflow.

## Table of contents
### 1. Tensorflow Basic
- Overview and Tensors [[ipynb]](notebooks/1_TensorflowBasic/1_Overview_and_Tensors.ipynb)
- Basic Operations (Low Level API) [[ipynb]](notebooks/1_TensorflowBasic/2_BasicOperation.ipynb)
- Basic Operations (Eager Execution) [[ipynb]](notebooks/1_TensorflowBasic/3_BasicOperation_Eager.ipynb)
- Scope [[ipynb]](notebooks/1_TensorflowBasic/4_Scope.ipynb)
- Dataset API [[ipynb]](notebooks/1_TensorflowBasic/5_DatasetAPI.ipynb)
- TFRecord [[ipynb]](notebooks/1_TensorflowBasic/6_TFRecord.ipynb)

### 2. Neural Network
__MNIST Classification with Dropout__
- Low Level API (tf.nn API) [[ipynb]](notebooks/2_NeuralNetwork/1_LowLevelAPI.ipynb)
- High Level API (tf.layers API) [[ipynb]](notebooks/2_NeuralNetwork/2_HighLevelAPI_1.ipynb)
- High Level API (tf.keras API w/ Eager) [[ipynb]](notebooks/2_NeuralNetwork/2_HighLevelAPI_2.ipynb)

### 3. Convolutional Neural Network
__MNIST Classification with Batch Normalization__
- Low Level API (tf.nn API) [[ipynb]](notebooks/3_ConvolutionalNetwork/1_LowLevelAPI.ipynb)
- High Level API (tf.layers API) [[ipynb]](notebooks/3_ConvolutionalNetwork/2_HighLevelAPI_1.ipynb)
- High Level API (tf.keras API w/ Eager) [[ipynb]](notebooks/3_ConvolutionalNetwork/2_HighLevelAPI_2.ipynb)

### 4. Sequence Model
__Simple Text Generation using RNN__
- Low Level API (tf.nn API) [[ipynb]](notebooks/4_SequenceModel/1-1_LowLevelAPI.ipynb)
- High Level API (tf.keras w/ Eager) [[ipynb]](notebooks/4_SequenceModel/1-2_HighLevelAPI.ipynb)

__Sequence Text Generation using LSTM__
- Low Level API (tf.nn API) [[ipynb]](notebooks/4_SequenceModel/2-1_LowLevelAPI.ipynb)
- High Level API (tf.keras w/ Eager) [[ipynb]](notebooks/4_SequenceModel/2-2_HighLevelAPI.ipynb)

### 5. Transfer Learning
__Dog Breed Clasification__
- Tensorflow Hub [[ipynb]](notebooks/5_TransferLearning/1_TensorflowHub.ipynb)
- tf.keras.Application [[ipynb]](notebooks/5_TransferLearning/2_KerasApplication.ipynb)

### 6. Data Augmentation
__Dog / Cat Classification__
- Data Augmentation (tf.keras) [[ipynb]](notebooks/6_DataAugmentation/1_UsingKeras.ipynb)
- Data Augmentation (tf.image) [[ipynb]](notebooks/6_DataAugmentation/2_UsingTF.ipynb)

### 7. Other Topcs
- Tensor Board [[ipynb]](notebooks/7_OtherTopics/1_TensorBoard.ipynb)
- Save and Load Models [[ipynb]](notebooks/7_OtherTopics/2_SaveAndLoadModels.ipynb)

## Requirements
- CUDA
  - CUDA 10.0
  - cuDNN 7.5
- Python Packages
  - tensorflow-gpu == 1.13.1
  - tensorflow-hub
  - etc.

### Anaconda
- Install Anaconda
- Use [yaml file](environments/requirements.yaml) to create environment

```bash
$ cd {path/to/yamlfile/parent}

$ conda env create -f requirements.yaml
```

### Docker
- Install Docker and Nvidia Docker to your host
- Use the [Dockerfile](environments/Dockerfile) to build a docker image

```bash
$ cd {path/to/Dockerfile/parent}

# {image_name}, {tag_name} and {container_name} shoule be define by yourself
$ docker build -t {image_name}/{tag_name} .
```
If you want to use a container as jupyter notebook server, run the container like bellow.

```bash
$ docker run --runtime=nvidia -it -p 8888:8888 --name {conteiner_name} {image_name}/{tag_name}
# If you want to use jupyter notebook, run command bellow
$ jupyter notebook --ip=0.0.0.0 --allow-root
```

If you want to use a container as tensorboard server, run the container like bellow.

```bash
$ docker run --runtime=nvidia -it -p 6006:6006 --name {conteiner_name} {image_name}/{tag_name}
```
