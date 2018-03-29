深度学习识别验证码
=========

本项目致力于使用神经网络来识别各种验证码。

特性
===
- __端到端，不需要做更多的图片预处理（比如图片字符切割、图片尺寸归一化、图片字符标记、字符图片特征提取）__
- __验证码包括数字、大写字母、小写__
- __采用自己生成的验证码来作为神经网络的训练集合、测试集合、预测集合__
- __纯四位数字，验证码识别率高达 99.9999 %__
- __四位数字 + 大写字符，验证码识别率约 90 %__
- __深度学习框架pytorch + 验证码生成器ImageCaptcha__


原理
===

- __训练集合生成__

    使用常用的 Python 验证码生成库 ImageCaptcha，生成 6w 个验证码，并且都自动标记好;
    如果需要识别其他的验证码也同样的道理，寻找对应的验证码生成算法自动生成已经标记好的训练集合或者手动对标记，需要上万级别的数量，纯手工需要一定的时间，再或者可以借助一些网络的打码平台进行标记

- __训练卷积神经网络__
    构建一个多层的卷积网络，进行多标签分类模型的训练
    标记的每个字符都做 one-hot 编码
    批量输入图片集合和标记数据，大概10个Epoch后，准确率已经达到 90% 以上


验证码识别率展示
========
![](https://raw.githubusercontent.com/dee1024/pytorch-captcha-recognition/master/docs/number.png)
![](https://raw.githubusercontent.com/dee1024/pytorch-captcha-recognition/master/docs/number2.png)


快速开始
====
- __步骤一：10分钟环境安装__

    Python2.7+ 、ImageCaptcha库(pip install captcha)、 Pytorch(参考官网http://pytorch.org)

- __步骤二：生成验证码__
    ```bash
    python captcha-gen.py
    ```
    会在目录下生成几张验证码图片，目录位置为 dataset/predict/1

- __步骤三：识别验证码__
    ```bash
    python captcha-predict.py
    ```
    可以在控制台，看到输出的结果

贡献
===
我们期待你的 pull requests !

作者
===
* __Dee Qiu__ <coolcooldee@gmail.com>

其它
===
* __Github项目交流QQ群__ 570997546


声明
===
本项目仅用于交流学习