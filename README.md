# DecisionTree(决策树ID3的实现)
## ID3决策树的算法步骤总结如下：
### 1.计算给定数据集的香农熵：
<a href="https://www.codecogs.com/eqnedit.php?latex=$$Ent(D)=-\sum_{i=1}^{n}{p(x_i)*log_2p(x_i)}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$Ent(D)=-\sum_{i=1}^{n}{p(x_i)*log_2p(x_i)}$$" title="$$Ent(D)=-\sum_{i=1}^{n}{p(x_i)*log_2p(x_i)}$$" /></a>
### 2.对数据集进行划分：
数据集的其中某一维数据满足某个值，则去除该维数据
### 3.选择最好的数据集划分方式：
* 计算每种划分方式的信息增益，信息增益越大，选择按照该维数据进行划分数据集
* 信息增益的计算公式为：

<a href="https://www.codecogs.com/eqnedit.php?latex=$$Gain(D,a)=Ent(D)-\sum_{v=1}^{V}{\frac{|D^v|}{|D|}Ent(D^v)}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$Gain(D,a)=Ent(D)-\sum_{v=1}^{V}{\frac{|D^v|}{|D|}Ent(D^v)}$$" title="$$Gain(D,a)=Ent(D)-\sum_{v=1}^{V}{\frac{|D^v|}{|D|}Ent(D^v)}$$" /></a>

其中，<a href="https://www.codecogs.com/eqnedit.php?latex=$D^v$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$D^v$" title="$D^v$" /></a>是划分的一个子集
### 4.递归构建决策树
* 每次构造决策树时，选择最好的数据划分方式，然后递归，当程序遍历完所有划分数据集的属性或者每个分支下的所有实例都是相同的分类的时候，递归结束
### 5.验证数据集
* 当新的数据集产生时，让数据集根据构造的决策树进行判断。注意：决策树的判断特征要和数据集对应的特征一致才能进行比较。比如：假设决策树第一个判断的对象是“work”，那么数据集便要找到其对应“work”的索引值和该决策树的第一个判断条件比较。

### 6.注意：程序当中有部分是和画决策树的图有关，现在还没有看，这部分代码对程序影响不大。后面再研究
