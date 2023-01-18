# Diffusion


## 常见问题

<br>

* classifier guided和classifier-free guided的区别？
  * [浅谈扩散模型的有分类器引导和无分类器引导](https://zhuanlan.zhihu.com/p/582880086)
    * classifier guided
    * classifier-free guided: 隐式的分类器引导。
      * 使用隐式分类器引导的最终解析式要求我们只需要训练两个梯度预估模型，其中一个是无条件生成的梯度预估模型（例如常规的DDPM），另一个是基于条件的梯度预估模型。而我们甚至可以使用同一个模型同时表示两者，区别只在于无条件生成时将条件向量置为零即可！