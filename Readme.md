## ASAP: Adaptive Structure Aware Pooling for Learning Hierarchical Graph Representations

[![Conference](http://img.shields.io/badge/AAAI-2020-4b44ce.svg)](https://aaai.org/Conferences/AAAI-20/) [![Paper](http://img.shields.io/badge/paper-arxiv.1911.07979-B31B1B.svg)](https://arxiv.org/abs/1911.07979)

Source code for [AAAI 2020](https://aaai.org/Conferences/AAAI-20/) paper: [**ASAP: Adaptive Structure Aware Pooling for Learning Hierarchical Graph Representation**](https://arxiv.org/abs/1911.07979)

![](https://github.com/ekagra-ranjan/ASAP-code/blob/master/clean2/ASAP-overview.png)

**Overview of ASAP:** *ASAP initially considers all possible local clusters with a fixed receptive field for a given input graph. It then computes the cluster membership of the nodes using an attention mechanism. These clusters are then scored using a GNN. Further, a fraction of the top scoring clusters are selected as nodes in the pooled graph and new edge weights are computed between neighboring clusters. Please refer to Section 4 of the paper for details.*

### File Descriptions
* `main.py` - contains the driver code for the whole project
* `asap_pool.py` - source code for ASAP pooling operator proposed in the paper
* `asap_pool_model.py` - a network which uses ASAP pooling as pooling operator
* `le_conv.py` - source code for LEConv GNN used in the paper
* `requirements.txt` - contains the required libraries used in this project

### Dependencies

- Compatible with PyTorch 1.0 and Python 3.x.
- Dependencies can be installed using `requirements.txt`.

Can be installed using the following command:
```
pip install -r requirements.txt
```

### Training a model from scratch

Example for PROTEINS dataset:
```
python main.py -data PROTEINS -batch 128 -hid_dim 64 -dropout_att 0.1 -lr 0.01
```

### Hyperparameters to reproduce reported scores in the paper

| Dataset | Batch Size | Hidden Dimension | Dropout | Learning rate (lr) |
|---|---|---|---|---|
| PROTEINS | 128 | 64 | 0.1| 0.01 |
| FRANKENSTEIN | 128 | 32 | 0 | 0.001 |
| NCI1 | 128 | 128 | 0 | 0.01 |
| NCI109 | 128 | 128 | 0 | 0.01 |
| DD | 64 | 16 | 0.3 | 0.01 |

### Citation:
Please cite the following paper if you found it useful in your work.


```bibtex
@article{ranjan2019asap,
  title={ASAP: Adaptive Structure Aware Pooling for Learning Hierarchical Graph Representations},
  author={Ranjan, Ekagra and Sanyal, Soumya and Talukdar, Partha Pratim},
  journal={arXiv preprint arXiv:1911.07979},
  year={2019}
}
```
For any clarification, comments, or suggestions please create an issue or contact [Ekagra](mailto:ekagra.ranjan@gmail.com).