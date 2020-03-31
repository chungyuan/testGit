# Hard skill detail reports
根據所建立的B邀約C關聯模型, 計算job和resume的內容相似程度, 並產生各項細節報表.
## 各程式碼及其描述分別如下：
### Behavior_embedding.ipynb: 主要將B邀約C的資料進行前處理並轉換為fastText的輸入格式
### Fasttext_model.ipynb: 將各field corpus透過Fasttext訓練
### Hard_skill_detail_reports.ipynb:計算職缺和履歷各field的相似程度, 並產生相關細節資訊. 
### Category_parameters_setting_local.ipynb: 建立結構化編號和中文對應表
### Function_utility_research.ipynb:
一些共用的function
## Getting started
Step1:
利用data/B_invite_C_dataportal.txt語法, 抓取在某一段時間區間內B對C有任合行為(包含邀約儲存、轉寄)的資料.
時間區間:本次實驗為兩個月的行為資料量, 如20190401~20190531
Step2:
執行Behavior_embedding.ipynb
目的：透過基於B對C的行為(邀約)建立職缺對履歷各field的內容關聯(graph), 產生random walk結果後利用fastText學習此關聯(embedding), 如圖1所示. 
Step3:
### 
執行Fasttext_model.ipynb
Step4:
執行Hard_skill_detail_reports.ipynb
將已tag完成的jobs(如hardskill_detail_job_{}.dat)和resumes(如hardskill_detail_idnos_message_{}.dat)透過訓練好的關聯模型計算各class的相似程度, 並紀錄resumes對jobs來說, 哪些是已具備的要求條件(精準組＆相似組)以及不具備的要求條件(不符合組)

四大類別
skill class (技能類別)
get_skill_detail_report(...)
language_detail(...)
skill_detail(...)
Experience class(經驗類別)
get_experience_detail_report(...)
work_exp_detail(...)
Education class (學歷類)
get_education_detail_report(...)
major_detail(...)
Expectation class (期望類)
get_expectation_detail_report(...)
expect_job_detail(...)





Hard_skill_detail_reports.ipynb: 

### step1:




如B比較喜歡具有哪些skill, tool, cert等的履歷.
關聯model: 
note:有些B對C產生了大量的行為數, 職類大部分為 
在本次實驗使用當B行為數>3*B行為數的標準差+B行為數的平均, 即濾除, 公式如下.
invite_th = std * 3 + mean
