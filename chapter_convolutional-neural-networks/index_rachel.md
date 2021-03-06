# 卷积神经网络
:label:`chap_cnn`

在前面的章节中，我们讨论过图像数据。对于图像数据，每个示例都由一个二维像素网格组成。无论我们处理的是黑白图像还是彩色图像，每个像素可能与一个或多个数值相关。到目前为止，我们处理二维结构的方式还十分有限：先将每个图像的空间结构展平成一维向量，再放入一个多层感知机中。由于这些网络相对于特征元素的顺序不变，所以无论我们是否保持二维像素空间结构相对应的顺序，还是在拟合多层感知机的参数之前对设计矩阵的列进行置换，我们都可以得到相似的结果。而最优情况是利用模型的先验知识，即附近的像素通的相互关联性，从而建立从图像数据中学习的有效模型。

本章介绍卷积神经网络（convolutional neural network，简称CNN）是一类强大的神经网络，正是为处理图像数据而设计的。基于卷积神经网络的体系结构的模型现在在计算机视觉领域中无处不在，并且已经占主导地位，以至于今天几乎所有开发商业应用程序或参与与图像识别、对象检测或语义分割相关的竞争都以这种方法为基础。

现代卷积神经网络，其设计得益于生物学、群论和大量的实验研究。现代卷积神经网络能获得精确模型方面，不但采样效率高，在计算上也是高效的。这是因为卷积神经网络需要的参数比多层感知机少，而且卷积神经网络很容易在GPU内核之间并行运算。因此，实践者经常尽可能地应用卷积神经网络，即使是在一维序列结构的任务上（例如音频、文本和时间序列分析），使用卷积也更加流行。在这些任务中，递归神经网络是经常使用的。卷积神经网络的一些巧妙微调也使它们在图结构数据和推荐系统中发挥作用。

首先，我们将介绍构成所有卷积网络主干的基本元素，包括卷积层本身，填充层和步幅层，用于在相邻空间区域聚集信息的池化层，在每一层使用的多个通道（multiple channels），以及对现代卷积网络结构的仔细讨论。在本章的最后，我们将以一个完整的工作实例来结束这一章，这是早在现代深度学习兴起之前就成功应用的第一个卷积网络。在下一章中，我们将深入研究一些流行的和相对较新的卷积网络架构，这些架构的设计是现代实践者常用大多数技术的代表。

```toc
:maxdepth: 2

why-conv
conv-layer
padding-and-strides
channels
pooling
lenet
```

