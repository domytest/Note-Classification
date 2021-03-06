### **代码说明**
#### **create_vocab.py**
对短信进行分词并消重,获得词库,做为特征属性。

获得的词库写入'dataSet/vocab.txt'

#### **feature_select.py**
进行特征选择， 排除在所有输入样本的垃圾短信中特征取值都是0的特征属性。

特征选择后新的词库写入'dataSet/new_vocab.txt'

#### **training_bayes.py**
训练朴素贝叶斯分类器

学习过程产生的数据保存在'classifier'

学习的结果保存在'classifier/done'

#### **classifier.py**
将训练完成的分类器，对短信进行分类，并获得评分。

结果保存在'dataSet/result_predict.txt'

评分 = 0.7 × (0.65 × 垃圾短信准确率 + 0.35 × 垃圾短信查全率） + 0.3 × （0.65 × 普通短信准确率 + 0.35 × 普通短信查全率）

----------------------------

### **运行结果**
#### **构建词库**
对8万条短信进行构建词库，共获得102328个词， 运行时间为：15.36s

#### **特征选取**
对原有的102328个词进行特征选取， 选取结束后获得29542个词， 运行时间为： 464.14s

#### **训练贝叶斯分类器**
将8万条短信，分成8个部分分别训练，运行时间为： 511.01s

#### **分类预测**
对2万条短信进行分类预测， 运行时间为： 597.79s

    预测结果评判：
    垃圾短信准确率: 0.985493230174
    垃圾短信查全率: 0.948789571695
    普通短信准确率: 0.993865714923
    普通短信查全率: 0.998319516021
    评分: 0.979480228387

