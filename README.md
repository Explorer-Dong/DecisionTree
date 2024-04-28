## 手搓决策树

### 一、数据预处理

#### 1.1 数据集简介

本项目使用的 [Adult](https://archive.ics.uci.edu/dataset/2/adult) 数据集共 14 个属性，2 个类别。在开始之前我们有必要了解一下数据集的详细情况：

14 个属性信息罗列如下：共 6 个连续型属性，8 个离散型属性

age: continuous.
workclass: Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
fnlwgt: continuous.
education: Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
education-num: continuous.
marital-status: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
occupation: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
relationship: Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
race: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
sex: Female, Male.
capital-gain: continuous.
capital-loss: continuous.
hours-per-week: continuous.
native-country: United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.

|  属性名   | 类别 | 含义 |
| :-------: | :--: | :--: |
|    age    |      |      |
| workclass |      |      |
|  fnlwgt   |      |      |
| education |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |
|           |      |      |

2 个类别信息罗列如下：

| 类名  |       含义        |
| :---: | :---------------: |
| >50K  |   年收入大于50K   |
| <=50K | 年收入小于等于50K |

#### 1.2 数据缺失值处理

#### 1.3 连续型数据处理

#### 1.4 离散型数据处理

### 二、模型训练

#### 2.1 模型简介

#### 2.2 细节处理

### 三、模型测试与评估

#### 3.1 信息增益处理结果

#### 3.2 信息率处理结果

#### 3.3 基尼指数处理结果

### 四、项目总结