## Readme

>源代码运行：直接跑last-code.ipynb文件即可



### 与SOTA的比较

SOTA最好的评分是Private Score: 0.88336 Public Score: 0.87813

![](.\image\private.png)

![](.\image\public.png)

从数据方面来看：SOTA的方法不仅仅使用了cutmix，还使用了mosaic数据增强方法来增加训练时的样本多样性；SOTA中将图片resize到了384x576，而我们的样本是resize到384x256.

从训练策略来看：同样的采用了5-折交叉验证，但是冠军方案中没有使用warm-up，而是使用了余弦退火的学习率衰减策略。SOTA的方案中还在最后几个循环加入了样本权重(没有具体说明)，并且还使用了软标签的策略。

从模型结构来看：SOTA仅仅使用了两个模型融合(resnet50+resnext50_32x4d)，但是没有给出具体的模型ensemble的方案，可能是软投票，也可能是模型的融合。