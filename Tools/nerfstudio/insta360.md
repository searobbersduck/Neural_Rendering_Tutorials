# Insta360数据重建

## Insta360数据处理

insta 360 数据处理，生成相机位姿, ref:[360 Data (Equirectangular)](https://docs.nerf.studio/en/latest/quickstart/custom_dataset.html#data-equirectangular)：

```
ns-process-data images --camera-type equirectangular --images-per-equirect 8 --crop-factor 0.0 0.2 0.utput-dir /workspace/data/insta360/processed_images
```

## 训练

ref: [Train and run viewer](https://docs.nerf.studio/en/latest/quickstart/first_nerf.html#train-and-run-viewer)

```

```