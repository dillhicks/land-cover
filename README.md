# Large Scale High-Resolution Land Cover Mapping with Multi-Resolution Data

Repo accompanying the CVPR 2019 paper "Large Scale High-Resolution Land Cover Mapping with Multi-Resolution Data".


## Data

The dataset and its documentation can be found at [LILA.science](http://lila.science/datasets/chesapeakelandcover). The `download_all.sh` script will download and unzip a copy of this dataset to the `./chesapeake_data/` directory. Note: this script assumes that the `azcopy` program is on your PATH; `azcopy` can be downloaded [here](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10).

## Requirements

Pre-trained keras models were generated with Python 3.6. See `requirements.txt` for the library versions that we used when developing. Generally, these libraries are needed:

- numpy
- pandas
- tensorflow-gpu
- Keras
- segmentation-models
- shapely
- rasterio

## References

Please cite the following papers if you use this work:

```
@inproceedings{robinson2019large,
  title={Large Scale High-Resolution Land Cover Mapping With Multi-Resolution Data},
  author={Robinson, Caleb and Hou, Le and Malkin, Kolya and Soobitsky, Rachel and Czawlytko, Jacob and Dilkina, Bistra and Jojic, Nebojsa},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2019},
  url={http://openaccess.thecvf.com/content_CVPR_2019/html/Robinson_Large_Scale_High-Resolution_Land_Cover_Mapping_With_Multi-Resolution_Data_CVPR_2019_paper.html}
}

@inproceedings{malkin2018label,
  title={Label super-resolution networks},
  author={Malkin, Kolya and Robinson, Caleb and Hou, Le and Soobitsky, Rachel and Czawlytko, Jacob and Samaras, Dimitris and Saltz, Joel and Joppa, Lucas and Jojic, Nebojsa},
  booktitle={International Conference on Learning Representations (ICLR)},
  year={2019},
  url={https://openreview.net/forum?id=rkxwShA9Ym},
}
```

## Todo

- Change `train_model_landcover.py` to save models without the superres loss, jaccard loss, or Lambda layers as these can cause problems with saving/loading in different versions.
- Re-write `eval_landcover_results.sh` in Python.
- Create a test script that computes accuracy on the fly without saving model results.
- Make it easy to target other label sets (e.g instead of 4-class classification).