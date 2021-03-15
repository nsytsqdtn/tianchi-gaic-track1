## 天池人工智能创新赛赛道1周星星分享——nsytsqdtn
#### 大家好，我是来自重庆邮电大学的nsytsqdtn,很荣幸能够拿到第一周的周星星。
----

### 方案分享
- 关于赛题的数据，数据量很小，都是短文本，并且一共只有几百个单词，所以没有重新预训练BERT，而是直接使用了传统的分类模型，把多标签分类任务转化成17个二分类任务。
- 关于词向量，我尝试了直接随机词向量、word2vec词向量，fasttext词向量，glove词向量以及各种词向量拼接，最后还是word2vec和glove的词向量拼接效果比较好。
- 关于模型，我目前的主力模型是textrnn+attention和DPCNN两个模型，经过Kfold加上一些简单的技巧，成绩就能达到0.909+。最后经过简单的加权融合，就到达了我现在的线上分数。textrcnn也有听别人说效果挺好的，不过目前我用起来线上成绩一般，就没有再考虑进一步研究。
- 关于我自己的一些操作技巧，我尝试过伪标签，但在我的模型上表现非常差，可能也是我的操作有一点问题。数据增强在我的模型上有半个百分点的提升，增强方式可以考虑把原来的文本随机shuffle，或者反转文本顺序以及随机mask掉一些词语，数据增强的随机概率对结果影响比较大，大家有兴趣可以自己试验一下。另外在embedding层后面加上spatial dropout相比原来的dropout也有一些提升。

----
#### 目前我也只是NLP的新手，希望可以和大家一起进步。
