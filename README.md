---
tags:
- image-classification
library_name: coreml
license: other
license_name: apple-ascl
license_link: LICENSE
datasets:
- imagenet-1k
---

# FastViT: A Fast Hybrid Vision Transformer using Structural Reparameterization

Please observe [original license](https://github.com/apple/ml-fastvit/blob/8af5928238cab99c45f64fc3e4e7b1516b8224ba/LICENSE).

## Model Details

- **Model Type:** Image classification / feature backbone
- **Model Stats:**
  - Params (M): 4.0
  - GMACs: 0.7
  - Activations (M): 8.6
  - Image size: 256 x 256
- **Papers:**
  - FastViT: A Fast Hybrid Vision Transformer using Structural Reparameterization: https://arxiv.org/abs/2303.14189
- **Original:** https://github.com/apple/ml-fastvit
- **Dataset:** ImageNet-1k

## Evaluation - Variants

| Variant                                                 | Parameters | Size (MB) | Weight precision | Act. precision | Δ Pytorch acc |
| ------------------------------------------------------- | ---------: | --------: | ---------------- | -------------- | ------------- |
| [T8](https://huggingface.co/apple/FastViTT8F16.mlpackage)     |      3.6M  |       7.8 | Float16          | Float16        |  -0.9%        |
| [MA36](https://huggingface.co/apple/FastViTMA36F16.mlpackage) |      42.7M |        84 | Float16          | Float16        | -0.06%        |

## Evaluation - Inference time

| Variant | Device               | OS   | Inference time (ms) | Dominant compute unit |
| ------- | -------------------- | ---- | ------------------: | --------------------- |
|    T8   | iPhone 12 Pro Max    | 17.5 |                0.79 | Neural Engine         |
|    T8   | M3 Max               | 14.4 |                0.62 | Neural Engine         |
|   MA36  | iPhone 12 Pro Max    | 18.0 |                4.50 | Neural Engine         |
|   MA36  | M3 Max               | 15.0 |                2.99 | Neural Engine         |

## Download

Install `huggingface-cli`

```bash
brew install huggingface-cli
```

To download one of the `.mlpackage` folders to the `models` directory:

```bash
huggingface-cli download \
  --local-dir models --local-dir-use-symlinks False \
  apple/coreml-FastViT-T8 
```

## Integrate in Swift apps

The [`huggingface/coreml-examples`](https://github.com/huggingface/coreml-examples/blob/main/depth-anything-example/README.md) repository contains sample Swift code for `coreml-FastViT-T8` and other models. See [the instructions there](https://github.com/huggingface/coreml-examples/tree/main/FastViTSample) to build the demo app, which shows how to use the model in your own Swift apps.

## Citation

```bibtex
@inproceedings{vasufastvit2023,
  author = {Pavan Kumar Anasosalu Vasu and James Gabriel and Jeff Zhu and Oncel Tuzel and Anurag Ranjan},
  title = {FastViT:  A Fast Hybrid Vision Transformer using Structural Reparameterization},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  year = {2023}
}
```
