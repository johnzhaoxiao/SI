# SI
take a chance about SI
#### 声纹识别氛围说话人辨认（Speaker identification） 和说话人确认（Speaker vertification）两种。
#### 前者为多选一，SI用于判断某一语音材料是由若干发音者中哪一个人所说，是属于‘多选一’的匹配查找识别。
#### 后者为一对一，SV用于确定某一语音材料是否由指定的某个人所说，属于‘一对一’的确认识别。

#### 从音频到图特征最常用的方法是 MFCC/FTT(傅里叶变换) /filterBank
#### 特征： 
- MFCC./PLP/FBank
- D-vecter(谷歌2014年提出)
- Deep feature/Bottleneck feature/Tandem feature (三者不是并行关系)
- BNF特征
- GMM_VBM
- ivecter+PLDA/CDS
- GMM+SVM
- d-vecter
#### 
声纹识别的评价指标主要为EER，叫作等错误率
