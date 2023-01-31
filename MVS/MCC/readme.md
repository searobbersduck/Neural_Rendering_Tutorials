# [Multiview Compressive Coding for 3D Reconstruction](https://mcc3d.github.io/)

## Abstract

> MCC is a new approach for 3D reconstruction from a single RGB-D image.
> 
> A central goal of visual recognition is to understand objects and scenes from a single image. 2D recognition has witnessed tremendous progress thanks to large-scale learning and general-purpose representations. But, 3D poses new challenges stemming from occlusions not depicted in the image. Prior works try to overcome these by inferring from multiple views or rely on scarce CAD models and category-specific priors which hinder scaling to novel settings. In this work, we explore single-view 3D reconstruction by learning generalizable representations inspired by advances in self-supervised learning. We introduce a simple framework that operates on 3D points of single objects or whole scenes coupled with category-agnostic large-scale training from diverse RGB-D videos. Our model, Multiview Compressive Coding (MCC), learns to compress the input appearance and geometry to predict the 3D structure by querying a 3D-aware decoder. MCC's generality and efficiency allow it to learn from large-scale and diverse data sources with strong generalization to novel objects imagined by DALLE 2 or captured in-the-wild with an iPhone.
>
> 视觉识别的一个中心目标是从单个图像中理解物体和场景。 由于大规模学习和通用表示，二维识别取得了巨大进步。 但是，3D 带来了新的挑战，这些挑战源于图像中未描绘的遮挡。 先前的工作试图通过从多个视图进行推断或依赖稀缺的 CAD 模型和特定类别的先验来克服这些问题，这些先验阻碍了扩展到新的设置。 在这项工作中，我们通过学习受自监督学习进步启发的可泛化表示来探索单视图 3D 重建。 我们介绍了一个简单的框架，该框架对单个对象或整个场景的 3D 点进行操作，并结合来自不同 RGB-D 视频的类别不可知的大规模训练。 我们的模型，多视图压缩编码 (MCC)，通过查询 3D 感知解码器来学习压缩输入外观和几何形状以预测 3D 结构。 MCC 的通用性和效率使其能够从大规模和多样化的数据源中学习，对 DALLE 2 想象的或用 iPhone 在野外捕获的新对象具有很强的泛化能力。

## Approch

> MCC adopts a simple encoder-decoder architecture. The input RGB-D image is fed to the encoder to produce an input encoding. The decoder inputs a query 3D point, along with the input encoding, to predict its occupancy probability and RGB color. This is illustrated in the figure below. MCC requires only points for supervision. This means that we can learn from large RGB-D datasets. The input channel D is read from depth sensors, as in iPhones, or computed by off-the-shelf depth models, e.g. MiDas, or computed by COLMAP in the case of multiview video streams.
>
> MCC 采用简单的编码器-解码器架构。 输入的 RGB-D 图像被馈送到编码器以产生输入编码。 解码器输入一个查询 3D 点以及输入编码，以预测其占用概率和 RGB 颜色。 下图对此进行了说明。 MCC只需要监管点。 这意味着我们可以从大型 RGB-D 数据集中学习。 输入通道 D 从深度传感器读取，如在 iPhone 中，或由现成的深度模型计算，例如 MiDas，或在多视图视频流的情况下由 COLMAP 计算。


## Results

