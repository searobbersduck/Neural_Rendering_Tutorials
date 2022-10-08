# Deformable Neural Rendering

这个部分讲解deformable的场景的重建。

<br><br>
***

### [D-NeRF: Neural Radiance Fields for Dynamic Scenes](https://arxiv.org/abs/2011.13961)

paper: [D-NeRF: Neural Radiance Fields for Dynamic Scenes](https://arxiv.org/abs/2011.13961)

github: [albertpumarola/D-NeRF](https://github.com/albertpumarola/D-NeRF)

youtube: [D-NeRF: Neural Radiance Fields for Dynamic Scenes](https://youtu.be/lSgzmgi2JPw)

这篇文章是2020年的一篇文章。

<br><br>
***
<br><br>

## 常见问题

* ### 论文中常出现的SE(3)是个什么东西？
   * [SE(3) 和 se(3)](https://zhuanlan.zhihu.com/p/88771394)
     
     * SE(3)代表的是旋转加上位移


* ### 拓扑结构
  * Nerfies中提到对于拓扑改变的场景，重建效果很差。所谓拓扑改变的场景，不如嘴巴的开合，在嘴巴的位置，产生了不连续，嘴巴由闭到张开的过程中，嘴巴上的一个点变成了不连续的两个点，是个不连续的过程，即所谓拓扑发生了改变。
  * [现象与本质：生活中的拓扑](https://www.bilibili.com/video/BV17s41167HN/?spm_id_from=autoNext&vd_source=2ef7e92f2d522c31939f486aea77a19e)
  * [想科普一下拓扑学，发现太难了，终于明白了李永乐老师为什么会被怼](https://www.bilibili.com/video/BV1wA41177HJ/?vd_source=2ef7e92f2d522c31939f486aea77a19e)
  

* ### Inverse transformation sampling
  * [逆变换采样](https://www.cnblogs.com/emanlee/p/12369485.html)
  * [逆变换采样 (inverse transform sampling) 的原理](https://blog.csdn.net/itnerd/article/details/105968943)
  * [Inverse transform sampling反变换采样法](https://blog.csdn.net/Eric2016_Lv/article/details/81191430)
  
