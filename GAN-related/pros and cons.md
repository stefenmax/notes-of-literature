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
