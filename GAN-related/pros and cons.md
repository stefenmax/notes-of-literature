1的流程图  
![image not found](https://github.com/stefenmax/notes-of-literature/blob/master/source/gan_1.png)
**pros and cons**  
+ 将Radon变换融入cGan里 直接通过sino图用生成器产生重建图
+ 总体无什么创新


2的流程图  
![image not found](https://github.com/stefenmax/notes-of-literature/blob/master/source/gan_2.png)  
**pros and cons**
+ 增加感知损失 利用imagenet预训练好的VGG进行实现  
+ 考虑稀疏性全面（少视图+少光子） 少光子这里利用朗伯比尔定律和加泊松噪声实现  
+ d 是个超参数 需要根据不同图像进行处理

3的流程图
![image](https://github.com/stefenmax/notes-of-literature/blob/master/source/gan_3.png)  
框架图
![image](https://github.com/stefenmax/notes-of-literature/blob/master/source/1.png)
![image](https://github.com/stefenmax/notes-of-literature/blob/master/source/2.png)  

**pros and cons**  
+ 发生器使用DenseNet,DenseNet在图像分类表示很好因为reusing the densely skip connection and feature map of the convolutional layer
不同于上篇文章 这篇文章发现VGG在Image-net预训练的感知损失不太好，不如L1L2,这里显示L1损失好于L2损失  
+ 生成器中包括四个DenseBlock,每个Block里包括四个卷积层和三个elementwise layer  
需要注意的是在每个elementwise 层后增加了一个**reduction block ？？** 目的是为不同的Denseblock提供相同的输入尺寸  
+ 鉴别器使用标准的CNN分类模型 类似SRGAN 包括8个卷积层 并具有BatchNorm层和Leaky Relu激活功能  



