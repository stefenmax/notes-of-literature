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
+ 生成器中包括四个DenseBlock,每个Block里包括四个卷积层和三个elementwise layer  
需要注意的是在每个elementwise 层后增加了一个**reduction block ？？** 目的是为不同的Denseblock提供相同的输入尺寸  
+ 鉴别器使用标准的CNN分类模型 类似SRGAN 包括8个卷积层 并具有BatchNorm层和Leaky Relu激活功能  
文章简介:去除OCT中的斑点噪声  
**pros and cons**  
+ 对抗训练中自动提取低噪声OCT图像特征,并将其编码到manifold space(流形空间**？？**)以减少低噪图像与高噪图像之间的感知差异
+ 将频率损失添加到loss function中从而抑制高频噪声保留低频细节  
+ 生成器高效 参数少 The generator is improved by adding the context-encoding module （context-encoding**？？**）  
+ 监督学习一般用L1和L2损失（会导致**过度平滑**）   
GAN提供了一种基于**感知**的损失函数 can measure the difference in data distribution of the manifold  
+ 发生器使用DenseNet,DenseNet在图像分类表示很好因为reusing the densely skip connection and feature map of the convolutional layer
+ loss function 设计包括两个部分内容损失和感知损失  
内容损失为pixel-wise and frequence domain L1 losses  
感知损失【REF:Photo-realistic single image super-resolution using a generative adversarial network】是
计算数据分布【REF:GOOD FELLOW大佬的原始文献】的差异  
不同于上篇文章 这篇文章发现VGG在Image-net预训练的感知损失不太好，不如L1L2,这里显示L1损失好于L2损失  
+ 训练参数和设置 卷积层都是3×3 使用ADAM优化器 学习率为10的-4次方  
+ 对比算法 SRResNet GAN-Resnet[REF:23] DCSRN[REF:24] GAN-UNet[REF:25]
+ 知识点：频域中参考图像和去噪图像的之间的均方差 为**FBE**(frequency-based error) 自己和背景比**CNR**(contrast-to-noise ratio)


