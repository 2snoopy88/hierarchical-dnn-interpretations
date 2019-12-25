Official code for using / reproducing ACD from the paper "[Hierarchical interpretations for neural network predictions](https://openreview.net/pdf?id=SkEqro0ctQ)" (ICLR 2019). This code produces hierarchical interpretations for a single prediction made by a neural network.

*Note: this repo is actively maintained. For any questions please file an issue.*

![](reproduce_figs/figs/intro.png)



# examples/documentation

- **installation**: `pip install git+https://github.com/csinva/hierarchical-dnn-interpretations`
- **examples**: the [reproduce_figs](reproduce_figs) folder has notebooks with many demos
- **api**: the [api](https://csinva.github.io/hierarchical-dnn-interpretations/docs/acd/) gives a list of available functions
- **src**: the [acd](acd) folder contains the source for the method implementation
- allows for different types of interpretations by changing hyperparameters (explained in examples)
- tested with python3 and pytorch >1.0 with/without gpu 
- all required data/models/code for reproducing are included in the [dsets](dsets) folder

| Inspecting NLP sentiment models    | Detecting adversarial examples      | Analyzing imagenet models           |
| ---------------------------------- | ----------------------------------- | ----------------------------------- |
| ![](reproduce_figs/figs/fig_2.png) | ![](reproduce_figs/figs/fig_s3.png) | ![](reproduce_figs/figs/fig_s2.png) |


# notes on using ACD on your own data
- the current CD implementation doesn't always work for all types of networks. If you are getting an error inside of `cd.py`, you may need to write a custom function that iterates through the layers of your network (for examples see `cd.py`). Should work out-of-the-box for many common layers though, including antyhing in alexnet, vgg, or resnet.
- to use baselines such build-up and occlusion, replace the pred_ims function by a function, which gets predictions from your model given a batch of examples.


# related work

- this work is part of an overarching project on interpretable machine learning, guided by the [PDR framework](https://arxiv.org/abs/1901.04592)
- see the [github repo](https://github.com/laura-rieger/deep-explanation-penalization) for [CDEP](https://arxiv.org/abs/1909.13584), which penalizes these scores to improve models during training
- see the [github repo](https://github.com/csinva/disentangled-attribution-curves) for [disentangled attribution curves](https://arxiv.org/abs/1905.07631) for ideas on extending disentangled interpretations to random forests
- the file scores/score_funcs.py also contains simple pytorch implementations of [integrated gradients](https://arxiv.org/abs/1703.01365) and the simple interpration technique gradient * input

# reference

- feel free to use/share this code openly
- if you find this code useful for your research, please cite the following:

  ```c
    @inproceedings{
    singh2018hierarchical,
    title={Hierarchical interpretations for neural network predictions},
    author={Chandan Singh and W. James Murdoch and Bin Yu},
    booktitle={International Conference on Learning Representations},
    year={2019},
    url={https://openreview.net/forum?id=SkEqro0ctQ},
    }
  ```

  
