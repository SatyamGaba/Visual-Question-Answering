# basic_vqa
Pytorch implementation of the paper - VQA: Visual Question Answering (https://arxiv.org/pdf/1505.00468.pdf).

![model](./png/basic_model.png)

## Directory and File Structure
```
.
+-- COCO-2015/
|   +-- images/ (link of /dataset/COCO2015 from server (using ln -s))
|       +-- train2014/
|       +-- ...
|   +-- resized_images/
|       +-- train2014/
|       +-- ...
|       +-- Questions/
|       +-- Annotations/
|       +-- train.npy
|       +-- ...
|       +-- vocab_questions.txt
|       +-- vocab_answers.txt
|   +-- <questions>.json
|   +-- <annotations>.json
+-- basic_vqa
|   +-- .git
|   +-- README.md
```


## Usage 

#### 1. Clone the repositories.
```bash
$ git clone https://github.com/tbmoon/basic_vqa.git
```

#### 2. Download and unzip the dataset from official url of VQA: https://visualqa.org/download.html.

```bash
$ cd basic_vqa/utils
$ chmod +x download_and_unzip_datasets.csh
$ ./download_and_unzip_datasets.csh
```

#### 3. Preproccess input data for (images, questions and answers).

```bash
$ python resize_images.py --input_dir='../datasets/Images' --output_dir='../datasets/Resized_Images'  
$ python make_vacabs_for_questions_answers.py --input_dir='../datasets'
$ python build_vqa_inputs.py --input_dir='../datasets' --output_dir='../datasets'
```

#### 4. Train model for VQA task.

```bash
$ cd ..
$ python train.py
```

## References
* Paper implementation
  + Keywords: Visual Question Answering ; Simple Attention; Stacked Attention; Top-Down Attention;
    
* Baseline Model
  + Github: https://github.com/tbmoon/basic_vqa
