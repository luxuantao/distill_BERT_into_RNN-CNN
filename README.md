# distill_BERT_into_RNN-CNN
复现论文《Distilling Task-Specific Knowledge from BERT into Simple Neural Networks》

代码参考自： https://github.com/qiangsiwei/bert_distill ，但是该代码中有部分bug，且年久失修，所以我进行了整理和修正

## 所用库版本

+ transformers 4.6
+ pytorch 1.8
+ keras 2.3

## 结果

在情感2分类hotel的数据集上结果如下：

 - 小模型（textcnn & bilstm）准确率在 0.78+

 - BERT模型 准确率在 0.91+

 - 蒸馏模型 准确率在 0.89+

## 运行

先解压word2vec.zip

开始finetune BERT

```bash
python ptbert.py
```

把BERT的知识蒸馏到小模型里

```bash
python distill.py
```

调整文件中的`use_aug`及以下的参数可以使用论文中提到的其中两种数据增强方式(masking, n-gram sampling)，不过实测下来准确率没有啥变化