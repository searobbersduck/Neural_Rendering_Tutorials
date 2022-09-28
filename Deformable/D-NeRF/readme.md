# D-NeRF: Neural Radiance Fields for Dynamic Scenes

这篇文章是2020年的一篇文章，这里只是简单的做个介绍。主要从几张图来看这篇文章。

首先，正文的第一张图。

![f1-abstract](./images/f1-abstract.JPG)

这张图说了什么内容呢？

这张图是说，本文提出了D-NeRF的方法，这个方法能够针对<font color='red'>包含复杂的非刚性几何体（物体）的场景</font>进行新视角的合成，并且能够合成<font color='red'>任意时间点</font>的新视角。这里利用一组稀疏的<font color='red'>单目图像</font>就能优化一个<font color='red'>underlying deformable volumetric function</font>，并且<font color='red'>不需要真实的几何和多视角图像</font>。(什么意思呢？就是说D-NeRF的输入就是最简单的单目视频，不需要额外的mesh或立体视觉作为输入)。这张图展示了两个场景，都是时间点和视角可变的场景。

仔细看这张图，你会发现一个问题，这里用到的图像都是合成图像，并且是没有背景的。所以这里说是能解决动态可形变场景的重建其实有点言过其实了。因为采用的是合成图像，那么在利用NeRF类方法进行重建过程中，必须的相机位姿参数就比较容易获取了（因为是合成图像，所以位姿参数是已知的）。但在真实场景中，形变物体的位姿参数相对来说，比较难准确获取，具体怎么获取会在之后的文章中介绍。

所以看了这张图之后，我们就也能了解到本文的局限性了，很难具体应用到实际的生产实践当中，那么接下来就简单的介绍下本文的方法思路。


![f2-problem-definition](./images/f2-problem-definition.JPG)

