### 题目  
Model-Based Iterative Reconstruction for Propagation-Based Phase-Contrast X-ray CT including   
Models for the Source and the Detector
### 主要内容
> #### 全文梗概
> #### 知识点
> #### 创新点
> #### 可用在自己课题中部分
## 正文
#### 1.全文梗概

#### 2.知识点
算法流程：先用生成器把输入的sino图转成重建图。然后用radon变换把得到一个model sino图 然后由鉴别器对输入sino图和model sino图进行比较  
sino图到重建图可以由一个全连接层直接得到 (Paschaliset al., 2004) 可以通过增加层和节点数目提高精度，但会带来更多的参数 容易欠拟合
#### 3.创新点
貌似没有 只是用GAN来学习自己生成的sino 图

#### 4.可用在自己课题中部分 or 自己的思考
这也可以发文章？？
