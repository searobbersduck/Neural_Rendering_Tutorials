# DeVRF: Fast Deformable Voxel Radiance Fields for Dynamic Scenes

home page:  [DeVRF: Fast Deformable Voxel Radiance Fields for Dynamic Scenes](https://jia-wei-liu.github.io/DeVRF/)

video link: https://youtu.be/Z8m3JSTk5lI

<br><br>

## Abstract

> Modeling dynamic scenes is important for many applications such as virtual reality and telepresence. Despite achieving unprecedented fidelity for novel view synthesis in dynamic scenes, existing methods based on Neural Radiance Fields (NeRF) suffer from slow convergence (i.e., model training time measured in days).

> In this paper, we present DeVRF, a novel representation to accelerate learning dynamic radiance fields. The core of DeVRF is to model both the 3D canonical space and 4D deformation field of a dynamic, non-rigid scene with explicit and discrete voxel-based representations. However, it is quite challenging to train such a representation which has a large number of model parameters, often resulting in overfitting issues. To overcome this challenge, we devise a novel static-to-dynamic learning paradigm together with a new data capture setup that is convenient to deploy in practice. This paradigm unlocks efficient learning of deformable radiance fields via utilizing the 3D volumetric canonical space learnt from multi-view static images to ease the learning of 4D voxel deformation field with only few-view dynamic sequences. To further improve the efficiency of our DeVRF and its synthesized novel view's quality, we conduct thorough explorations and identify a set of strategies.

> We evaluate DeVRF on both synthetic and real-world dynamic scenes with different types of deformation. Experiments demonstrate that DeVRF achieves two orders of magnitude speedup (100x faster) with on-par high-fidelity results compared to the previous state-of-the-art approaches.

> 动态场景建模对于虚拟现实和远程呈现等许多应用都很重要。 尽管在动态场景的新视图合成达到了前所未有的保真度，但现有的基于神经辐射场 (NeRF) 的方法收敛缓慢（即，模型训练时间以天为单位）。

> 在本文中，我们提出了DeVRF，一种用于加速学习动态辐射场的新的表征方式。DeVRF的核心是对动态非刚性场景的3D规范空间和4D形变场进行建模，它使用显示和离散体素的表征方式。然而，训练这种具有大量模型参数的表征，非常具有挑战性，通常会导致过拟合问题。为了应对这一挑战，我们设计了一种新颖的静态到动态的学习范式以及一种便于在实践中部署的新数据捕获装置。该范例通过利用从多视图静态图像中学习到的3D规范体空间来解锁可形变辐射场的有效学习，从而简化了仅使用少量动态视图序列的4D体素形变场的学习。
> 为了进一步提高DeVRF的效率及其合成新视图的质量，我们进行了深入的探索并确定了一套策略。

> 我们在具有不同类型形变的合成和真实动态场景上评估DeVRF。 实验表明，与以前的最先进方法相比，DeVRF 实现了两个数量级的加速（快 100 倍），并具有同等的高保真结果。