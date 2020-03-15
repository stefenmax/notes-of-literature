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
文章简介:去除OCT中的斑点噪声  
**pros and cons**  
+ 对抗训练中自动提取低噪声OCT图像特征,并将其编码到manifold space(流形空间**？？**)以减少低噪图像与高噪图像之间的感知差异
+ 将频率损失添加到loss function中从而抑制高频噪声保留低频细节  
+ 生成器高效 参数少 The generator is improved by adding the context-encoding module （context-encoding**？？**）  
+ 监督学习一般用L1和L2损失（会导致**过度平滑**）   
GAN提供了一种基于**感知**的损失函数 can measure the difference in data distribution of the manifold  
+ 发生器使用DenseNet


