## 使用 numpy 实现 Decision Tree

### 一、数据预处理

#### 1.1 数据集简介

本项目使用的 [Adult](https://archive.ics.uci.edu/dataset/2/adult) 数据集共 14 个属性，2 个标签。14 个属性中，共 6 个连续型属性，8 个离散型属性；2 个标签中，分别是年收入的高低情况。并且数据集已经帮我们划分好了训练集 `adult.data` 和测试集 `adult.test`。我们的任务就是训练一个决策树来对未知数据进行二分类。

#### 1.2 数据缺失值处理

可以看到数据集中有部分数据缺失的样本，我们需要解决这一部分的数据缺失，经过统计，发现有属性缺失的样本数量在训练集和测试集中的占比均不到 $8\%$，因此我们考虑直接删除训练集和测试集中有属性缺失的样本。

#### 1.3 连续型数据处理

由于决策树在进行结点生成时，需要依据当前结点的属性列举所有可能的测试属性，这要求属性的取值是可列的，但是连续型数据的属性值是不可列的，这要求我们对连续型数据进行离散化处理。

### 二、模型实现细节

本项目使用 numpy、pandas 等科学计算库，利用 adult 数据集，模拟实现了决策树 $\text{(Decision Tree Classifier)}$ 分类模型。而训练学习的根本是构建一棵决策树并且为每一个叶子结点打上关于 $\text{income}$​ 的标签，因此我们需要合理设计树的结点。我们从算法流程出发，进行数据结构的设计，以**信息增益**模型为例。

**考虑最优划分决策**。在选择最优属性时，我们需要计算出当前结点的所有可选的属性对应的每一个信息增益。

- 可选属性列表是什么？我们知道决策树每向下一层都会少一个属性，并且同层的结点含有的属性列表相同，因此我们不需要在树的结点中存储真实的属性列表，只需要存储属性列表的索引 `feat_idx` 即可。
- 如何计算信息熵？我们根据信息熵的计算公式 $\text{Ent(D)}=-\sum_{i=1}^tp_i\log(p_i)$ 可知，我们需要知道当前结点对应到数据集中的哪些数据 $D$，同样我们只需要知道 $D$ 的索引 `data_idx` 即可。$t$ 表示类别数量，肯定只有两个分别为高收入和低收入，因此不需要存储。于是就可以计算 $\text{Ent(D)}$ 了
- 如何计算信息增益？我们需要计算所有划分出来的结点信息熵之和 $\sum_{i=1}^V\text{Ent}(D^i)$​，其中 V 是当前属性的属性值取值个数。离散型的属性值可取值个数很容易计算，连续型的进行离散化即可，不再赘述。因此我们需要存储每一个属性对应的属性值可取列表，我们可以直接将属性列表扩展为二维，每一维再存储属性值可取列表即可。于是信息增益就可以计算了

**考虑递归终止条件**。在不断递归的过程中，只需要不断计算信息增益并且传递上述的两个参数即可。

- 递归终止以后需要做什么？我们直到递归终止表明当前结点是叶子结点，我们需要标记当前叶子结点对应的类别，于是我们增加结点的一个字段 `label` 用来标记类别
- 什么时候递归终止？这涉及到决策树 $\text{ID3}$ 算法的实现

### 三、模型测试与评估

#### 3.1 纵向对比测试

依据划分策略，本项目实现了信息增益、信息率和基尼指数三种方法，经过测试有以下性能趋势。

#### 3.2 纵向对比测试

利用 sk-learn 包的 [`DecisionTreeClassifier`](https://scikit-learn.org.cn/view/784.html) 分类器进行对照。

### 四、项目总结