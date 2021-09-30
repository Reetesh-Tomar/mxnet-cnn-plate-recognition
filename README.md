﻿# 基于CNN的OCR车牌识别

------

- 本项目地址：https://github.com/huxiaoman7/mxnet-cnn-plate-recognition.git
- 车牌识别包含两部分：车牌检测和车牌识别。本模型主要用于车牌的识别。


------
### 所需环境

> * Python2.7
> pyhton 2.9 is latest
> * Mxnet
> Hi
> * Numpy
> * Opencv

------

### 操作步骤
#### 1.生成车牌sample[^code]
```
python genPlate.py 100 /Users/shelter/plate_100

参数1：生成车牌的数量
参数2：生成车牌存放的地址
```

#### 2.训练CNN模型[^code]
```
python train.py 
```

#### 3.预测车牌准确率
```
#随机生成100张车牌图片
python genPlate.py 100 /Users/shelter/test

#批量预测测试图片准确率
python test.py /Users/shelter/test

##输出结果示例
output:
预测车牌号码为:津 K 4 2 R M Y
输入图片数量:100
输入图片行准确率:0.72
输入图片列准确率:0.86
```

------
### 参考资料
```
1.http://blog.csdn.net/relocy/article/details/52174198
2.https://github.com/szad670401/learning-dl/tree/master/mxnet/ocr

```

------
### 新增功能@11.8
```
1.增加生成黄色车牌功能 genYellowPlate.py
 - 黄色车牌包括大车、农用车、教练车、摩托车、试验车，目前只能生成正常车牌（教练车、一行、7位数），摩托车、大车暂时还未开发，明天开发@11.9
2.增加生成绿色车牌功能 gen GreenPlate.py
 - 绿色车牌主要是新能源车牌，背景图片与蓝色车牌有区别，位数为8位，与传统的7位蓝色车牌不同。当然，绿底的车牌也包括几种：小型新能源车号牌（非纯电动、纯电动）、大型新能源车号牌（非纯电动、纯电动），前者底色为全绿，上部会有少许白色，后者全绿色，左边两个字符的底色为黄色。目前只开发了前者的车牌生成，后者还未找到合适的背景图。

```

------
### 待开发功能
```
1.最近做了个yolov3的车牌检测的项目，上周跑了个demo，这周针对性优化开发了三天，准确率为99.25%，还有不少的优化空间。过段时间把检测+识别一体化，端到端输出
2.白底车牌和黑底车牌的检测和识别也有待增加。目前数据集太少，也得生成一些比较真实的数据集，可以尝试用GAN的方法生成更加逼真的车牌

```

