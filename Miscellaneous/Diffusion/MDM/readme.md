# MDM: Human Motion Diffusion Model

home page: https://guytevet.github.io/mdm-page/

video link: https://youtu.be/rVkIDj5wgjs

## Abstract

> Natural and expressive human motion generation is the holy grail of computer animation. It is a challenging task, due to the diversity of possible motion, human perceptual sensitivity to it, and the difficulty of accurately describing it. Therefore, current generative solutions are either low-quality or limited in expressiveness. Diffusion models, which have already shown remarkable generative capabilities in other domains, are promising candidates for human motion due to their many-to-many nature, but they tend to be resource hungry and hard to control. In this paper, we introduce Motion Diffusion Model (MDM), a carefully adapted classifier-free diffusion-based generative model for the human motion domain. MDM is transformer-based, combining insights from motion generation literature. A notable design-choice is the prediction of the sample, rather than the noise, in each diffusion step. This facilitates the use of established geometric losses on the locations and velocities of the motion, such as the foot contact loss. As we demonstrate, MDM is a generic approach, enabling different modes of conditioning, and different generation tasks. We show that our model is trained with lightweight resources and yet achieves state-of-the-art results on leading benchmarks for text-to-motion and action-to-motion.

> 自然而富有表现力的人体动作生成是计算机动画的圣杯。
> 
> 这是一项具有挑战性的任务，因为可能的运动的多样性、人类对其的感知敏感性以及准确描述它的难度。
> 
> 因此，当前的生成解决方案要么质量低下，要么表达能力有限。扩散模型已经在其他领域表现出显着的生成能力，由于其多对多的性质，它们很有希望成为人体运动的候选者，但它们往往资源匮乏且难以控制。
> 
> 在本文中，我们介绍了运动扩散模型 (MDM)，这是一种经过精心调整的基于无分类器扩散的人体运动域生成模型。 
> 
> MDM 是基于转换器的，结合了来自运动生成文献的见解。一个值得注意的设计选择是在每个扩散步骤中对样本的预测，而不是对噪声的预测。这有助于在运动的位置和速度上使用已建立的几何损失，例如脚接触损失。正如我们所展示的，MDM 是一种通用方法，支持不同的调节模式和不同的生成任务。
> 
> 我们展示了我们的模型使用轻量级资源进行训练，并且在文本到动作和动作到动作的领先基准上取得了最先进的结果。