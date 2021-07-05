# Code Summarization with Strcuture-induced Transformer

This repo serves as the official implementation of ACL 2021 findings paper "[Code Summarization with Strcuture-induced Transformer](https://arxiv.org/pdf/2012.14710.pdf)".

The implementation is based on https://github.com/wasiahmad/NeuralCodeSum.

If you have any questions, free to email me.

## Dependency

```bash
pip install -r requirements.txt
```



## Data

For Python, we follow the pipline in https://github.com/wanyao1992/code_summarization_public.

For Java, we fetch from https://github.com/xing-hu/TL-CodeSum.

In the paper, we write the scripts on our own to parse code into AST. But it is a tough task. We are trying to find a nice way to do so and then experiment under SiT. For just reproducing the results, you can download the data we used directly from [here](https://drive.google.com/file/d/1iVR0WsEs3v9NLKEjBmQnaLuqccK2pyl5/view?usp=sharing) and put both `python` and `java` in the `data` directory.

The `adjacency` is too large to load on my personal server. So I allocate a guid for each code snippet in `.guid` and retrieve them one by one. What you need to do is:

```bash
cd sit3
unzip adjacency.zip
```



## Quick Start

**Training**

```bash
cd main
python train.py --dataset_name python --model_name YOUR_MODEL_NAME
```

See the log through:

```bash
vi ../modelx/YOUR_MODEL_NAME.txt
```

In the paper, we run SiT for 150 epochs. For example in Java:

```txt
01/18/2021 01:12:25 PM: [ dev valid official: Epoch = 150 | bleu = 44.89 | rouge_l = 55.25 | Precision = 61.14 | Recall = 57.81 | F1 = 56.95 | examples = 8714 | valid time = 58.93 (s) ]
```



**Testing**

```bash
python test.py --dataset_name python --beam_size 5 --model_name YOUR_MODEL_NAME
```



## Citation

```latex
@inproceedings{hongqiu2021summarization,
 author = {Hongqiu, Wu and Hai, Zhao and Min, Zhang},
 booktitle = {Proceedings of the 59th Annual Meeting of the Association for Computational Linguistics (ACL)},
 title = {Code summarization with structure-induced transformer},
 year = {2021}
}
```

