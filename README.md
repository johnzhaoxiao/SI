# SI
take a chance about SI
#### 声纹识别分为说话人辨认（Speaker identification） 和说话人确认（Speaker vertification）两种。
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

声纹识别的评价指标主要为EER，叫作等错误率。由错误接受率（不是真人的声音，但是却接受了）和错误拒绝率（是真人声音但拒绝了）构成。取两者绘图的曲线交点值作为评价指标， 此值越少，说明模型越好
#### 等错误率EER:
R_fa = Number of False Acceptance / Number of impostors accesses     接受假冒者而造成的错误率  
R_fr = Number of False Rejection / Number of target accesses         拒绝真实的说话人而造成的错误率  
EER : R_fa = R_fr

#### 计算函数：
```
def calculate_eer_auc_ap(label,distance):
    fpr, tpr, thresholds = metrics.roc_curve(label, distance, pos_label=1)
    # Calculating EER
    intersect_x = fpr[np.abs(fpr - (1 - tpr)).argmin(0)]
    EER = intersect_x
    return EER,fpr, tpr
```
##### fpr 假阳率（False Position Rate）:
  其含义是检测出来的假阳性样本除以所有真实阴性样本数
##### tpr 真阳率（True Position Rate）:
  其含义是检测出来的真阳性样本数除以所有真实阳性样本数
##### 因此：
```
R_fa = fpr
R_fr = 1-tpr
```
