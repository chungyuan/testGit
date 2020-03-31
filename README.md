# Hard skill detail reports
According to the BC relational model, we calculate the similarity score between job and resume in each field to generate hard skill detail reports.
根據所建立的BC關聯模型, 計算job和resume的內容相似程度, 並產生各項細節報表.  
## Getting started
Behavior_embedding.ipynb: 
Category_parameters_setting_local.ipynb:
Function_utility_research.ipynb
Hard_skill_detail_reports.ipynb:
### step1:

data/B_invite_C_dataportal.txt
目的：抓取在某一段時間區間內B對C有任合行為(包含邀約儲存、轉寄)的資料.
時間區間:本次實驗為兩個月的行為資料量, 如20190401~20190531 大約為475W筆

Behavior_embedding.ipynb
目的：透過基於B對C的行為建立各field的關聯(graph), 產生random walk結果後利用fastText學習此關聯(embedding), 如圖1所示. 
如B比較喜歡具有哪些skill, tool, cert等的履歷.
關聯model: 
note:有些B對C產生了大量的行為數, 職類大部分為 
在本次實驗使用當B行為數大於3倍的B行為數的標準差再加上B行為數的平均, 即濾除, 公式如下.
invite_th = std * 3 + mean
