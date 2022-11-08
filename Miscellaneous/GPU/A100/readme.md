## Introduction

在现代云数据中心运行的计算密集型应用程序的多样性推动了 NVIDIA GPU 加速云计算的爆炸式增长。 此类密集型应用包括 AI 深度学习训练和推理、数据分析、科学计算、基因组学、边缘视频分析和 5G 服务、图形渲染、云游戏等等。 从扩展 AI 训练和科学计算，到扩展推理应用程序，再到启用实时对话式 AI，NVIDIA GPU 提供了必要的马力来加速在当今云数据中心运行的众多复杂且不可预测的工作负载。

<br><br>
## 常见问题

<br>

* BF16是什么数据格式？
  * [BF16格式数据](https://blog.csdn.net/sunmingyang1987/article/details/115362809)
    * BF16的指数位比FP16多，跟FP32一样，不过小数位比较少。这样设计说明了设计者希望在16bits的空间中，通过降低精度（比FP16的精度还低）的方式，来获得更大的数值空间（Dynamic Range）
    * 这种数据格式就是BF16，使用BF16算法的预测精度与FP32相似，但不如FP32精确（谷歌曾说过，这是因为神经网络对指数的大小比尾数敏感得多）。对于大多数应用程序，尤其是计算机视觉和语音方面，这种折衷是可以接受的
  * [BF16是为深度学习而优化的新数字格式 预测精度的降低幅度最小](https://blog.csdn.net/yaoyutian/article/details/114458750)
    * BF16，有时也被称为BFloat16或Brain Float16，是一种针对人工智能／深度学习应用程序进行优化的新数字格式。它在谷歌Brain上获得了广泛的应用，包括谷歌、英特尔、Arm和许多其他公司的人工智能加速器。
    * BF16背后的想法是通过降低数字的精度来减少计算能力和将张量相乘所需的能源消耗。张量是一个三维的数字矩阵；张量的乘法是计算人工智能所需的关键数学运算。
    * 现在大多数人工智能训练都使用FP32， 32位浮点数。虽然这意味着计算非常准确，但它需要强大的硬件和大量的电力。推理通常使用INT8， 8位整数（整数）。虽然使用诸如INT8这样的较低精度的数字系统可以在相同的硬件上提供更高的吞吐量，从而节省电力，但是计算（预测）的结果却不那么准确。
    * BF16的目的是优化精度和预测精度之间的权衡，以增加吞吐量。
  * [bfloat16 数值格式](https://cloud.google.com/tpu/docs/bfloat16?hl=zh-cn)
    * 使用降低精确率的浮点数是一种缩短收敛时间而不会损失准确率的常用方法。TPU 在执行矩阵运算时使用 bfloat16 数字格式。矩阵乘法运算是针对 bfloat16 值执行，而累积是针对 IEEE float32 值执行。
  * bfloat16与fp32能够表征一样的范围（指数位数相同），精度会略有下降（位数7vs23）,但在视觉和语音方面，神经网络对指数的大小比尾数敏感的多。
    * ![](./images/bf16_arch.JPG)

<br>

* Fine grained structured sparsity是什么 ?
  * [细粒度结构化稀疏剪枝(Fine-grained Structural Sparse Pruning)](https://zhuanlan.zhihu.com/p/381279197)


<br>

* PCIE 3.0 * 16 是什么意思？
  * [请问PCIe 3.0 x 16（x4）是什么意思？](https://www.zhihu.com/question/391716892)
    * PCIe 3.0*16（*4）是指那个插槽是全长槽（*16长度），但有效带宽只有*4长度。
    * 物理接口尺寸全长（x16）,其实只有x4的布线，也就是无论接什么硬件上限都是x4
    * ![](./images/pcie-3x16.JPG)
  
<br>

* ddr4 gddr6 hbm2的区别是什么?
  * [GDDR6 vs DDR4 vs HBM2?为什么CPU还不用GDDR？异构内存的未来在哪里？](https://zhuanlan.zhihu.com/p/83935084)
    * 如果引入HBM在内存系统中，加上DIMM类型的傲腾内存，我们就可能有三种内存共存的情况，每种内存都有自己的好处：HBM快，但是少；DDR内存多些，居中；傲腾内存最慢，但是容量大，而且内容不会丢失。三种内存可以形成互相cache的关系，也可以都报告给操作系统，让操作系统根据它们的特性和任务的特性，来主动选择具体存在哪里。如此，就形成了异构内存系统，这是内存发展的方向。


<br>

* tensor core是什么？
  * [深入理解混合精度训练：从 Tensor Core 到 CUDA 编程](https://aijishu.com/a/1060000000286803)
    * 混合精度是指在底层硬件算子层面，使用半精度（FP16）作为输入和输出，使用全精度（FP32）进行中间结果计算从而不损失过多精度的技术，而不是网络层面既有 FP16 又有 FP32。这个底层硬件层面其实指的就是 Tensor Core，所以 GPU 上有 Tensor Core 是使用混合精度训练加速的必要条件。
  * [NVIDIA深度学习Tensor Core性能解析（上）](https://wujianming110117.blog.csdn.net/article/details/106442850?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-106442850-blog-106442372.pc_relevant_3mothn_strategy_recovery&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-106442850-blog-106442372.pc_relevant_3mothn_strategy_recovery&utm_relevant_index=2)
    * 首先进行的是GEMM测试，利用某些深度学习应用程序（DeepSpeech、Speaker ID和Language Modeling）中的内核进行GEMM操作，测出的性能比在cuBLAS中运行纯矩阵-矩阵乘法更有代表性。
    * 测试的结果在意料之内，启用Tensor Core可以大幅提升性能。深入研究细节可以发现，Tensor Core对于特定类型的矩阵-矩阵乘法会有特别的影响。
  * [Tensor Core技术解析（下）](https://blog.csdn.net/wujianing_110117/article/details/106442372)
    * 并没太看懂其中的内容


<br>

* tf32 vs fp32
  * [TensorFloat-32 in the A100 GPU Accelerates AI Training, HPC up to 20x](https://blogs.nvidia.com/blog/2020/05/14/tensorfloat-32-precision-format/)



<br>

* Fine grained structured sparsity  是什么?
  * [细粒度结构化稀疏剪枝(Fine-grained Structural Sparse Pruning)](https://zhuanlan.zhihu.com/p/381279197)
    * 以Nvidia A100 GPU为例子，通过新的2：4稀疏矩阵，即每4个连续权重中允许两个非零值。由于矩阵的定义明确，一来可以对其进行有效压缩，将内存存储量和带宽减少近2倍。二来因为保存了非零值权重索引，所以只需要计算非零值的乘累加，计算速度加倍。
    * 如下图，Sparse Tensor Core通过indices挑选对应的acts与weights进行乘累加运算，实现计算加速。
    * ![](./images/fine_grained_structured_sparsity_arch.JPG)