# 『ギャル百合で聞く論文ポッドキャスト』
## 第17話台本
## *What Truly Matters in Trajectory Prediction for Autonomous Driving?*
### ほんのり百合・抑制版 / 構造化脚本

---

## 0. オープニング

**A**：  
きょうは、trajectory prediction の評価にケンカを売る論文。  
かなり好き。  

**B**：  
タイトルは、**“What Truly Matters in Trajectory Prediction for Autonomous Driving?”**。  
fixed dataset 上の prediction accuracy と、  
実際の driving performance が一致しない理由を掘る論文です。  

**A**：  
ADE と FDE が良ければ偉い。  
その雑な空気を、ちゃんと壊しにきてる。  

---

## 1. 何が問題なのか

**B**：  
この論文の中心問題は、  
trajectory prediction の評価が、  
**static evaluation に偏っている**ことです。  

**A**：  
つまり、固定 dataset 上で未来軌跡を当てる。  
でも実運転では、ego が動けば周りも変わる。  
そこが抜ける。  

**B**：  
はい。  
論文では、  
prediction algorithm が ego vehicle の behavior を変え、  
その ego の behavior が周囲の vehicles の future behaviors を変えることで、  
**predictor-specific dynamics** が生じると述べています。  

**A**：  
なのに fixed dataset だと、  
他車の未来は録画済み。  
だから、その相互作用が消える。  

**B**：  
このズレを、論文は **dynamics gap** と呼んでいます。  

---

## 2. 論文の主張

**A**：  
主張はかなり明快。  
**interactive, task-driven evaluation が必要**。  

**B**：  
その通りです。  
ADE や FDE のような dataset accuracy だけでは、  
実際の autonomous driving system 内での有効性を十分に表せない。  

**A**：  
prediction は単体で閉じたモジュールじゃない。  
downstream の control や planning に食い込む。  
だから評価も、その文脈で見ろってことね。  

**B**：  
はい。  
論文は dynamics gap だけでなく、  
**prediction accuracy と computational efficiency の trade-off** も重要だと述べています。  

**A**：  
精度が高くても重すぎたら、  
システム全体の driving performance で負けることがある。  
そのへん、だいぶ現実的。  

---

## 3. 何を見落としていたのか

**B**：  
この論文が鋭いのは、  
trajectory prediction 評価で見落とされていたものを、  
ちゃんと言語化している点です。  

**A**：  
予測器の良し悪しって、  
当てた軌跡の距離誤差だけじゃ決まらない。  
ego がどう振る舞い、周りがどう反応し、  
全体としてどう運転になるかまで含む。  

**B**：  
ええ。  
つまり、predictor は passive observer ではなく、  
system behavior を変える active component です。  

**A**：  
この視点が入ると、  
prediction benchmark の作り方そのものが変わる。  

**B**：  
はい。  
fixed dataset の ranking を、そのまま downstream performance の ranking だと思うのは危険だ、  
という強いメッセージがあります。  

---

## 4. 何に効く論文か

**A**：  
これ、prediction の論文だけど、  
評価設計全般にも効くよね。  

**B**：  
その通りです。  
特に、自動運転や mobile robotics で、  
あるモジュールが system behavior を変える場合、  
**module-level metric と system-level outcome のズレ**を疑うべきだと教えてくれます。  

**A**：  
prediction accuracy が高い。  
でも運転は下手。  
その逆もある。  
その可能性を真面目に見る。  

**B**：  
ええ。  
だから、この論文は  
trajectory prediction に閉じず、  
closed-loop evaluation の価値を考える材料になります。  

---

## 5. 含意と限界

**B**：  
この論文の含意は、  
trajectory prediction benchmark を、  
**interactive system evaluation へ近づける必要**があるという点です。  

**A**：  
静的 metric を全部捨てろ、ではない。  
でも、それだけ信じるな、ってこと。  

**B**：  
はい。  
ADE、FDE のような metric には依然として意味がありますが、  
それだけでは不十分です。  

**A**：  
だから、読み方としては、  
既存 metric の否定というより、  
system-level evaluation を足せって提案。  

**B**：  
その理解が適切です。  

---

## 6. クロージング

**A**：  
この論文、  
prediction を「当てる問題」から、  
「システムをどう変えるかの問題」に戻してた。  

**B**：  
ええ。  
fixed dataset 上の prediction accuracy と実運転性能の間にある dynamics gap を示し、  
interactive, task-driven evaluation の必要性を強く主張した論文です。  

**A**：  
数字がきれいでも、  
運転がきれいとは限らない。  
そこ、忘れたくない。  

**B**：  
はい。  
かなり重要な視点転換だと思います。  
