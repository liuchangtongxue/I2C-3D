# Inclusive Interactive Collisions for Multi-View Consistent Compositional 3D Generation

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/ECCV-2026-blue"></a>
  <a href="#"><img src="https://img.shields.io/badge/Project-Page-lightgrey"></a>
  <a href="#"><img src="https://img.shields.io/badge/arXiv-coming_soon-b31b1b"></a>
  <a href="#"><img src="https://img.shields.io/badge/License-TBD-lightgrey"></a>
</p>

This repository contains the official implementation of **I<sup>2</sup>C-3D**, an optimization-based framework for generating multi-view consistent compositional 3D assets with physically plausible object interactions.

> **Inclusive Interactive Collisions for Multi-View Consistent Compositional 3D Generation**  
> Chang Liu<sup>1,2</sup>, Mingwen Shao<sup>2,3*</sup>, Xiang Lv<sup>2</sup>, Xinyuan Chen<sup>2</sup>, Lingzhuang Meng<sup>2</sup>, Qiao Zhang<sup>2</sup>, Zhengyi Gong<sup>2</sup>, Jinghao Hu<sup>4</sup>  
> <sup>1</sup>Fudan University
> <sup>2</sup>China University of Petroleum (East China)  
> <sup>3</sup>Shenzhen University of Advanced Technology  
> <sup>4</sup>Northwest University  
> <sup>*</sup>Corresponding author

## News 💡

- **2026.06**: I<sup>2</sup>C-3D is accepted to ECCV 2026 .
- Code cleanup and additional examples are in progress, because i'm busy with new works 💻.




## Installation

The code has been tested with Python 3.9 and PyTorch 2.0.1.

```bash
conda create -n i2c3d python=3.9
conda activate i2c3d
pip install -r requirements.txt
```

Install PyTorch3D following the official instructions:

```bash
git clone --branch stable https://github.com/facebookresearch/pytorch3d.git
cd pytorch3d
FORCE_CUDA=1 pip install .
cd ..
```

Optional but recommended:

```bash
pip install ninja
```

Build the Gaussian Splatting CUDA extension:

```bash
cd gs
./build.sh
cd ..
```

Some configurations use Shape-E or Point-E initialization. If your run requires these modules, install or place the corresponding packages so that Python can import `shap_e` and `point_e`.

## Quick Start

Run one of the provided configuration files:

```bash
python main.py --config-name=test
```

Other available examples are located in `conf/`.

For example:

```bash
python main.py --config-name=pillow
```

To resume from a checkpoint:

```bash
python main.py --config-name=pillow +ckpt=/path/to/step_XXXX.pt
```

To enable Weights & Biases logging:

```bash
python main.py --config-name=pillow wandb=true
```

## Layout Generation with LLMs

The repository includes a program-aided layout planning script:

```bash
python generate_layouts_PAL.py 
```





Before using the LLM planner, configure your API endpoint and token in `generate_layouts_PAL.py`.


## 💐 Acknowledgements

This codebase builds on excellent open-source 3D generation projects, including **SemanticSDS** and **GSGEN**. We thank the authors for releasing their code and inspiring this implementation.

## 🖊️ Citation

If you find this project useful, please consider citing:

```bibtex
@misc{liu2026inclusiveinteractivecollisionsmultiview,
      title={Inclusive Interactive Collisions for Multi-View Consistent Compositional 3D Generation}, 
      author={Chang Liu and Mingwen Shao and Xiang Lv and Xinyuan Chen and Lingzhuang Meng and Qiao Zhang and Zhengyi Gong and Jinghao Hu},
      year={2026},
      eprint={2606.24206},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2606.24206}, 
}
```

