
# Eigendecomposition-free Training of Deep Networks with Zero Eigenvalue-based Losses (ECCV 2018)

This repository is a reference implementation for Z. Dang, K. Yi, Y. Hu,
F. Wang, M. Salzmann, and P. Fua, "Eigendecomposition-free Training of Deep Networks with Zero Eigenvalue-based Losses ",
ECCV 2018. If you use this code in your research,
please cite the paper.

This repo contains the code for PnP task, for Keypoint Matching task pls check [Eig-Free-Keypoint-Matching-realse](https://github.com/Dangzheng/Eig-Free-Keypoint-Matching-release)

# Installation

This code base is based on Python3. For more details on the required libraries,
see `requirements.txt`. You can also easily prepare this by doing

```
pip install -r requirements.txt
```

# Preparing data
This repo only provide the way to create the PnP dataset.
Find the file pnp_outliers_dataset.ipynb in the folder datasets. Run it. You will find the dataset in the `./datasets` which contains data for training, testing and validation.

# Training

While we also provide our trained models, you can also easily train your own
models. Simply run:

```
python main.py --run_mode=train
```

See `config.py` for more options in running the software. Try it
yourself. Nearly all parameters that we changed in the paper should be
there. 

The default place to store the results is `./res/logs`. To change this, use
`res_dir` to set the base directory, `log_dir` for the suffix for the training
configurations. `test_log_dir` is used to if you want to change the suffix for
storing results. For example, `log_dir` can store the training configuration,
and `test_log_dir` can store which training configuration is used on which
testing dataset.

# Testing

Again, testing is quite simple. After training is done, run:

```
./main.py --run_mode=test
```

You could find our the model which trained by us in the folder `./model_best`. You have to move these two files to the dir `./res/logs/`.

P.S. I changed the experiment setting, fix the number of matches to be 200 in the training process, for the reason that we found this will give us better result. The parameter what we are using is `alpha=10., beta=5.e-3`.



