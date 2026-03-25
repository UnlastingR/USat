# USat: A Unified Self-Supervised Encoder for Multi-Sensor Satellite Imagery

> [**USat: A Unified Self-Supervised Encoder for Multi-Sensor Satellite Imagery**](TBD)<br>
> [Jeremy Irvin*](jirvin16.github.io), [Lucas Tao*](https://www.linkedin.com/in/lucas-tao-612026134), [Joanne Zhou](https://www.linkedin.com/in/joanneyoushanzhou), [Yuntao Ma](https://www.linkedin.com/in/yuntaoma0402), [Langston Nashold](https://www.linkedin.com/in/langston-nashold), [Benjamin Liu](https://profiles.stanford.edu/benjamin-liu), [Andrew Y. Ng](https://www.andrewng.org/)

*Equal contribution

Official implementation of the paper "[USat: A Unified Self-Supervised Encoder for Multi-Sensor Satellite Imagery](TBD)".

## Highlights
USat introduces a unified Masked Autoencoder (MAE) framework for learning continuous representations from multi-sensor satellite imagery. It supports variable spatial resolutions, spectral bands, and imaging modalities (e.g., optical Sentinel-2, SAR Sentinel-1) via a novel unified architecture.

## Checkpoints
Pre-trained model checkpoints are available to download:
- [USat-Base Checkpoint (Google Drive / Hugging Face Link - TBD)](#)

## Data Downloading
The dataset implementations (found in `usat/data/`) expect standard formats. We primarily evaluate our work on datasets including:
- [BigEarthNet](http://bigearth.net/)
- EuroSAT
- SpaceNet v2

Update the `base_path` arguments in your specific configuration YAML files (e.g. `configurations/pretrain.yaml`) to point to your local dataset directories.

## Environment Set-up
Perform the following steps in the `USat` directory.
1. Create a Python 3.9 conda environment:
```bash
conda create -n usat python=3.9 -y
conda activate usat
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Editable install the project code:
```bash
pip install --no-deps -e ./
```

## Data Preprocessing
Data augmentations and preprocessing logic are handled dynamically in the `usat/data` and `usat/utils/transform.py` scripts. If any specific offline generation steps are required, they will be described here.

## Model Training

The training process uses PyTorch Lightning. Configurations are managed via YAML files in the `configurations/` directory.

### Pre-training
To run pre-training (e.g., USatMAE), edit `configurations/pretrain.yaml` with your dataset paths and run:
```bash
python main.py train configurations/pretrain.yaml
```

### Fine-tuning
For fine-tuning on downstream tasks (e.g., classification), configure your weights path in `configurations/finetune.yaml` and run:
```bash
python main.py train configurations/finetune.yaml
```

## Model Evaluation
To evaluate a fine-tuned model checkpoint on a specific task's test set:
```bash
python main.py test configurations/finetune.yaml
```

## Citation
If you use this codebase or our pre-trained models, please cite:
```bibtex
@article{irvin2023usat,
  title={USat: A Unified Self-Supervised Encoder for Multi-Sensor Satellite Imagery},
  author={Irvin, Jeremy and Tao, Lucas and Zhou, Joanne and Ma, Yuntao and Nashold, Langston and Liu, Benjamin and Ng, Andrew Y.},
  journal={arXiv preprint arXiv:TBD},
  year={2023}
}
```

## Contact
If you have any questions, please open an issue or reach out to us at [Email/Contact TBD].
