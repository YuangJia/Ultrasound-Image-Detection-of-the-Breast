# 一.赛题背景

乳腺超声图像分类和乳腺特征识别具有广泛的应用场景，主要包括以下几个方面：可用于乳腺肿瘤的早期诊断和鉴别；可以进行乳腺疾病的筛查和预防工作；基于乳腺超声图像分类和特征识别的分析结果，可以为患者制定个性化的治疗方案。同时，通过定期跟踪乳腺病变的变化，可以评估治疗效果，指导后续治疗方案的调整；也可以为临床医生提供辅助决策支持。

然而，对乳腺癌的超声图像进行分类面临着诸多挑战性问题。

（1）图像质量和解剖结构复杂性：超声图像的质量受到多种因素的影响，如声波穿透深度、乳腺密度、声束散射等。乳腺组织的解剖结构复杂，包括脂肪、腺体、纤维等，这种复杂性可能导致图像中出现阴影、伪影以及结构不清晰等问题，使得肿瘤的检测和定位变得困难。

（2）肿瘤的大小和形态多样性：乳腺肿瘤的大小和形态各异，有的肿瘤可能非常小且形状不规则，有的可能与周围组织密集相似，这增加了在超声图像中准确检测和定位肿瘤的难度。

（3）良恶性肿瘤的特征相似性：有时候良性和恶性乳腺肿瘤在超声图像上的形态特征相似，如边界清晰、内部回声均匀等，这增加了区分良恶性肿瘤的挑战。

（4）噪声和伪影：超声图像可能受到多种因素的干扰，如仪器噪声、伪影和运动伪影等，这可能导致误检或漏检。

![img](https://publicqn.saikr.com/2024/05/24/882_66505357788ad.png)

而对超声乳腺影像BIRADS分类及对乳腺特征进行有效识别，可以提升乳腺肿瘤分类的准确性，减少误诊和漏诊。同时采用人工智能（AI）算法，实现自动化和标准化的BIRADS分类，可以减少人为误差，提高诊断一致性。通过高效的AI算法，可以更好地分配医疗资源，尤其在医疗资源有限的地区，显著提升乳腺癌筛查和诊断能力。



# 二. 赛题任务

​	本赛题聚焦于利用Ai算法提高超声乳腺影像中BIRADS分类和特征识别的准确性。BIRADS（乳腺影像报告和数据系统）分类是一种评估乳腺健康状况的重要手段，通过对超声影像的特征进行详细识别和分析，医生能够判断乳腺病变的性质并进行相应的治疗建议。

任务描述

​	参赛选手需设计一个AI算法，该算法能够高效处理超声乳腺影像，通过图像识别技术识别乳腺影像中的关键特征，并根据这些特征自动分类BIRADS等级以及相关特征识别。



任务说明

输入：经预处理的乳腺超声影像数据集，包含图片及其ID号和图片对应的标签。

输出：对于每幅影像，输出其ID对应的BIRADS分类结果，以及影像中关键特征的识别结果。

# 三、评价方式

根据参赛队伍提供的预测结果文件，计算准确率、特征预测准确率、灵敏度、特异性和F1分数的平均得分，综合算法速度计算综合评分。

评价指标：

准确率（Accuracy）：

计算模型预测肿瘤分类（良性或恶性）的准确率。

![img](https://publicqn.saikr.com/2024/05/24/781_665055eabf350.png)

 特征预测准确率：

 分别计算模型对方位、边缘、钙化和形状四个特征的预测准确率。

![img](https://publicqn.saikr.com/2024/05/24/627_665055f6e31a0.png)

计算每一种特征的预测准确率，将四种特征准确率相加取平均得到特征预测准确率。

灵敏度和特异性：

灵敏度：测量模型识别恶性肿瘤的能力。

![img](https://publicqn.saikr.com/2024/05/24/352_66505600a62cb.png)

特异性：测量模型正确识别良性肿瘤的能力。

![img](https://publicqn.saikr.com/2024/05/24/280_6650560c1989a.png)

F1分数：

考虑精确率和召回率，评估模型在不平衡数据集上的性能。

 

![img](https://publicqn.saikr.com/2024/05/24/721_66505657a6c4c.png)

交叉验证得分：

考虑到乳腺肿瘤大小形态差别较大，使用交叉验证方法来评估模型在不同数据子集上的表现，增强评估的稳定性和可靠性。

算法速度（Speed）：

评估算法处理整个测试集所需的时间（秒），较短的执行时间表示较高的算法效率。

综合评分计算：

计算公式为

![img](https://publicqn.saikr.com/2024/05/24/12_6650567583d2b.png)

A 表示算法性能得分，综合准确率、特征预测准确率、灵敏度、特异性和F1分数的平均得分。计算公式为

![img](https://publicqn.saikr.com/2024/05/24/331_665056b97e9bf.png)

 

T 表示所设计算法的运行时间得分。所有参赛队伍设计的算法的运行时间记为集合![img](https://publicqn.saikr.com/2024/05/24/33_665056eca91e0.png)，选手的运行时间![img](https://publicqn.saikr.com/2024/05/24/227_665056ff7e086.png)，

则

![img](https://publicqn.saikr.com/2024/05/24/634_665057368b015.png)

其他考虑因素：

资源使用率和能耗：评估模型在数据处理时的资源消耗，包括CPU和内存使用，以及能源消耗。

评分加权调整与惩罚机制：根据比赛的重点调整评分权重，对模型中存在的不合理之处或重大缺陷设置惩罚分。

说明：

1、为确保评价的全面性，算法性能和速度将同时考虑，以准确率和执行时间的加权得分作为最终评价标准。

2、如果算法存在不合理之处或重大缺陷，其综合评分将受到影响，可能为0。

# 四. 我们的模型

**图像分类任务：YOLO11，目前开发UI中**

![](https://agent-demo-leo.oss-cn-chengdu.aliyuncs.com/yolo.png)

**特征识别任务：**

![image-20241029171744413](https://cdn.jsdelivr.net/gh/LeonardoMESSI/Picgo/img/image-20241029171744413.png)

我们用ResNet-50提取图像全局特征。并用自己训练的分割模型对病灶处周围提取关键信息，并用CNN进行编码。这里我们为了简便起见，将全局特征和局部特征concat到一起，继续前向传播。在最后，我们为每个特征设计了分类头。为了进一步提高模型检测特征的能力（尤其是钙化），我们将增强对比度的图像与原图像进行差分(以突出图像中的白斑部分),并将这个差分向量加上主干网络的向量一起进行分类。



**Demo：**

我们提供了权重文件，请下载：

[特征分类-SegResNet](https://drive.google.com/file/d/1cKapyY3htjBlu1o_lNI63mfejHnaN_JH/view?usp=drive_link)

[图像分类-YOLOV11](https://drive.google.com/file/d/12lxfLsdbyVwvb9xnZmjpvuS0g5RVBAy3/view?usp=drive_link)

并将他们放入本项目目录下的checkpoint文件夹下。

此外我们提供了Demo版本的测试集TestB，可以直接使用。



完成这两项后，使用下面的脚本开始Demo(为了不引起歧义，请使用绝对路径)：

```shell
cd project
python run.py python run.py  --feature_dir "Path/to/TestB/fea" --cla_dir "Path/to/TestB/cla" --fea_model_path "Path/to/project/checkpoint/segresnet_best_model.pth" --cla_model_path "Path/to/project/checkpoint/yolo_best_model.pt"
```

