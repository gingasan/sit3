# Code Summarization with Strcuture-induced Transformer

This repo serves as the official implementation of ACL 2021 findings paper "[Code Summarization with Strcuture-induced Transformer](https://arxiv.org/pdf/2012.14710.pdf)".

The implementation is based on https://github.com/wasiahmad/NeuralCodeSum.



## Dependency

```bash
pip install -r requirements.txt
```



## Run

**Training**

```bash
cd main
python train.py --dataset_name python
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

