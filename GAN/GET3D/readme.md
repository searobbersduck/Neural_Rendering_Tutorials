# GET3D

大家好今天来给大家讲解一篇文章Get 3D ，这篇文章的全称是 A generative model of High quality 3D textured shapes learned from images 。这篇文章是发表在new IPS twenty twenty two的一篇文章 。文章的作者主要来自英伟达团队 。

## Abstract

> As several industries are moving towards modeling massive 3D virtual worlds, the need for content creation tools that can scale in terms of the quantity, quality, and diversity of 3D content is becoming evident. In our work, we aim to train performant 3D generative models that synthesize textured meshes which can be directly consumed by 3D rendering engines, thus immediately usable in downstream applications. Prior works on 3D generative modeling either lack geometric details, are limited in the mesh topology they can produce, typically do not support textures, or utilize neural renderers in the synthesis process, which makes their use in common 3D software non-trivial. In this work, we introduce GET3D, a Generative model that directly generates Explicit Textured 3D meshes with complex topology, rich geometric details, and high fidelity textures. We bridge recent success in the differentiable surface modeling, differentiable rendering as well as 2D Generative Adversarial Networks to train our model from 2D image collections. GET3D is able to generate high-quality 3D textured meshes, ranging from cars, chairs, animals, motorbikes and human characters to buildings, achieving significant improvements over previous methods.


> 随着多个行业朝着对大型 3D 虚拟世界建模的方向发展，对能够根据 3D 内容的数量、质量和多样性进行扩展的内容创建工具的需求变得越来越旺盛。

> 在我们的工作中，我们的目标是去训练 能够合成带有纹理的网格的高性能3D生成模型，这些带纹理的网格mesh可以直接被 3D 渲染引擎使用，因此可以立即用于下游应用程序。

> 先前关于 3D 生成建模的工作要么受限于它们可以生成的网格拓扑通常不支持纹理而缺乏几何细节，要么在合成过程中使用神经渲染器，这使得它们在通常的 3D 软件中的使用变得更加复杂。

> 在这项工作中，我们介绍了 GET3D，这是一种生成模型，可直接生成具有复杂拓扑、丰富几何细节和高保真纹理的 Explicit Textured 3D Mesh。

> 我们将最近在可微表面建模、可微渲染以及 2D 生成对抗网络方面的成功结合起来，从 2D 图像集合中训练我们的模型。 GET3D 能够生成高质量的 3D 纹理网格( textured meshes)，可生成的种类范围从汽车、椅子、动物、摩托车和人物角色到建筑物，与以前的方法相比取得了显着改进。


<br><br>
## Introduction
<br>


> In this work, we introduce a novel approach that aims to tackle all the requirements of a practically useful 3D generative model. Specifically, we propose GET3D, a Generative model for 3D shapes that directly outputs Explicit Textured 3D meshes with high geometric and texture detail and arbitrary mesh topology. In the heart of our approach is a generative process that utilizes a differentiable explicit surface extraction method [60] and a differentiable rendering technique [47, 37]. The former enables us to directly optimize and output textured 3D meshes with arbitrary topology, while the latter allows us to train our model with 2D images, thus leveraging powerful and mature discriminators developed for 2D image synthesis. Since our model directly generates meshes and uses a highly efficient (differentiable) graphics renderer, we can easily scale up our model to train with image resolution as high as 1024 × 1024, allowing us to learn high quality geometric and texture details.

> 在这项工作中，我们介绍了一种新颖的方法，旨在解决实际有用的3D生成模型的所有要求。 具体来说，我们提出了GET3D，这是一种3D形状的生成模型，它直接输出具有高几何和纹理细节以及任意网格拓扑的显式的带纹理的3D网格。 我们方法的核心是利用可微显式表面提取方法和可微渲染技术的生成过程。 前者使我们能够直接优化和输出具有任意拓扑的带纹理的3D网格，而后者使我们能够用2D图像训练我们的模型，从而利用为2D图像合成开发的强大而成熟的鉴别器。由于我们的模型直接生成网格并使用高效（可微分）图形渲染器，我们可以轻松扩展模型以训练高达 1024 × 1024 的图像分辨率，从而学习高质量的几何和纹理细节。


<br><br>

*** 

## Related Work

<br>

### 3D Generative Models

这一部分提出了之前生成类方法的局限：
* 将 2D CNN 生成器直接扩展到 3D 体素网格，但是 3D 卷积的高内存占用和计算复杂性阻碍了高分辨率的生成过程。
* 点云、隐式或八叉树表示，这些方法主要集中在生成几何图形而忽略了外观。 它们的输出表示也需要进行后处理，以使其与标准图形引擎兼容。
* Textured3DGAN 和 DIBR 生成带纹理的 3D 网格，但它们将生成公式化为模板网格的变形，这阻碍了它们生成复杂的拓扑结构或具有不同属的形状，而我们的方法可以做到这一点。
* PolyGen 和 SurfGen 可以生成具有任意拓扑的网格，但不能合成纹理。

<br>

### 3D-Aware Generative Image Synthesis

这一部分