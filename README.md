# Automated Fact-Checking Resources

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/Cartus/Automated-Fact-Checking-Literature)
[![Last Commit](https://img.shields.io/github/last-commit/Cartus/Automated-Fact-Checking-Literature)](https://github.com/Cartus/Automated-Fact-Checking-Literature)
[![Contribution_welcome](https://img.shields.io/badge/Contributions-welcome-blue)](https://github.com/Cartus/Automated-Fact-Checking-Literature/blob/main/contribute.md)


## Overview

This repo contains references from our survey paper "A Survey on Automated Fact-Checking". In this survey, we present a comprehensive and up-to-date survey of automated fact-checking, unifying various components and definitions developed in previous research into a common framework.  

- [Task Definition](#task-definition)
- [Dataset](#datasets)
  - [Claim Detection](#claim-detection-dataset)
  - [Factual Verification](#factual-verification-dataset)
    - [Natural Claims](#natural-claims)
    - [Artificial Claims](#artificial-claims)
- [Shared Tasks](#shared-tasks)
- [Model](#model)
  - [Claim Detection](#claim-detection)
  - [Factual Verification](#factual-verification)
  - [Justification Generation](#justification-generation)
- [Surveys](#surveys)
- [Related Tasks](#related-task)
- [Tutorials](#tutorials)


## Task Definition
Figure below shows a NLP framework for automated fact-checking consisting of three stages:  
1. Claim detection to identify claims that require verification; 
2. Evidence retrievalto find sources supporting or refuting the claim; 
3. Claim verification to assess the veracity of the claim based on the retrieved evidence. 

![Framework](Figures/framework.png)

Evidence retrieval and claim verification are sometimes tackled as a single task referred to asfactual verification, while claim detection is often tackled separately. Claim verificationcan be decomposed into two parts that can be tackled separately or jointly: verdict prediction, where claims are assigned truthfulness labels, and justification generation, where explanations for verdicts must be produced.

## Datasets
### Claim Detection Dataset
* CREDBANK: A Large-Scale Social Media Corpus with Associated Credibility Annotations (Mitra and Gilbert, 2015).
[[Paper](http://eegilbert.org/papers/icwsm15.credbank.mitra.pdf)]
[[Dataset](https://github.com/compsocial/CREDBANK-data)]
* Detecting Rumors from Microblogs with Recurrent Neural Networks (Ma et al., 2016)
[[Paper](https://www.ijcai.org/Proceedings/16/Papers/537.pdf)]
[[Dataset](https://www.dropbox.com/s/46r50ctrfa0ur1o/rumdect.zip?dl=0)]
* Analysing How People Orient to and Spread Rumours in Social Media by Looking at Conversational Threads (Zubiaga et al., 2016).
[[Paper](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0150989)]
[[Dataset](https://figshare.com/articles/PHEME_rumour_scheme_dataset_journalism_use_case/2068650)]
* SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours (Derczynski et al., 2017).
[[Paper](https://www.aclweb.org/anthology/S17-2006.pdf)]
[[Dataset](https://alt.qcri.org/semeval2017/task8/index.php?id=data-and-tools)]
* SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours (Gorrell et al., 2019).
[[Paper](https://www.aclweb.org/anthology/S19-2147.pdf)]
[[Dataset](https://competitions.codalab.org/competitions/19938)]
* Joint Rumour Stance and Veracity
[[Paper](https://aclanthology.org/W19-6122.pdf)]
[[Dataset](https://figshare.com/articles/dataset/RumourEval_2019_data/8845580)]
* Separating Facts from Fiction: Linguistic Models to Classify Suspicious and Trusted News Posts on Twitter
[[Paper](https://aclanthology.org/P17-2102.pdf)]
[[Dataset](https://aclanthology.org/attachments/P17-2102.Datasets.zip)]
* Overview of CheckThat! 2020: Automatic Identification and Verification of Claims in Social Media
[[Paper](https://link.springer.com/chapter/10.1007%2F978-3-030-58219-7_17)]
[[Dataset](https://sites.google.com/view/clef2020-checkthat/datasets-tools)]
* The CLEF-2021 CheckThat! Lab on Detecting Check-Worthy Claims, Previously Fact-Checked Claims, and Fake News
[[Paper](https://link.springer.com/chapter/10.1007%2F978-3-030-72240-1_75)]
[[Dataset](https://sites.google.com/view/clef2021-checkthat/tasks/task-1-check-worthiness-estimation)]
* Detecting Check-worthy Factual Claims in Presidential Debates
[[Paper](https://idir.uta.edu/~naeemul/file/factchecking-cikm15-hassan-cameraready.pdf)]
* A Context-Aware Approach for Detecting Worth-Checking Claims in Political Debates
[[Paper](https://www.acl-bg.org/proceedings/2017/RANLP%202017/pdf/RANLP037.pdf)]
[[Dataset](https://github.com/apepa/claim-rank)]
* Overview of the CLEF-2018 CheckThat! Lab on Automatic Identification and Verification of Political Claims. Task 1: Check-Worthiness
[[Paper](http://ceur-ws.org/Vol-2125/invited_paper_13.pdf)]

### Factual Verification Dataset
#### Natural Claims
* Truth of Varying Shades: Analyzing Language in Fake News and Political Fact-Checking (Rashkin et al., 2017).
[[Paper](https://www.aclweb.org/anthology/D17-1317.pdf)]
[[Dataset](https://hrashkin.github.io/factcheck.html)]
* “Liar, Liar Pants on Fire”: A New Benchmark Dataset for Fake News Detection (Wang, 2017).
[[Paper](https://www.aclweb.org/anthology/P17-2067.pdf)]
[[Dataset](https://sites.cs.ucsb.edu/~william/software.html)]
* Integrating Stance Detection and Fact Checking in a Unified Corpus (Baly et al., 2018).
[[Paper](https://www.aclweb.org/anthology/N18-2004.pdf)]
[[Dataset](https://alt.qcri.org/resources/arabic-fact-checking-and-stance-detection-corpus/)]
* A Richly Annotated Corpus for Different Tasks in Automated Fact-Checking (Hanselowski et al., 2019).
[[Paper](https://www.aclweb.org/anthology/K19-1046.pdf)]
[[Code](https://github.com/UKPLab/conll2019-snopes-crawling)]
[[Dataset](https://tudatalib.ulb.tu-darmstadt.de/handle/tudatalib/2081)]
* MultiFC: A Real-World Multi-Domain Dataset for Evidence-Based Fact Checking of Claims (Augenstein et al., 2019).
[[Paper](https://www.aclweb.org/anthology/D19-1475.pdf)]
[[Dataset](https://competitions.codalab.org/competitions/21163)]  
* Fact or Fiction: Verifying Scientific Claims (Wadden et al., EMNLP 2020).
[[Paper](https://www.aclweb.org/anthology/2020.emnlp-main.609.pdf)]
[[Dataset](https://github.com/allenai/scifact)]
* Explainable Automated Fact-Checking for Public Health Claims (Kotonya and Toni, 2020). 
[[Paper](https://arxiv.org/abs/2010.09926)]
[[Dataset](https://github.com/neemakot/Health-Fact-Checking)]
* FakeNewsNet: A Data Repository with News Content, Social Context and Spatialtemporal Information for Studying Fake News on Social Media (Shu et al., 2018).
[[Paper](https://arxiv.org/pdf/1809.01286.pdf)]
[[Dataset](https://github.com/KaiDMML/FakeNewsNet)]
* FakeCovid-- A Multilingual Cross-domain Fact Check News Dataset for COVID-19 (Shahi and Nandini, 2020). 
[[Paper](https://arxiv.org/pdf/2006.11343.pdf)]
[[Dataset](https://gautamshahi.github.io/FakeCovid/)]
* r/Fakeddit: A New Multimodal Benchmark Dataset for Fine-grained Fake News Detection (Nakamura et al., 2020).
[[Paper](https://www.aclweb.org/anthology/2020.lrec-1.755.pdf)]
[[Dataset](https://github.com/entitize/fakeddit)]


#### Artifical Claims
* FEVER: a Large-scale Dataset for Fact Extraction and VERification (Thorne et al., 2018).
[[Paper](https://www.aclweb.org/anthology/N18-1074.pdf)] 
[[Dataset](https://fever.ai/resources.html)] 
* Automated Fact-Checking of Claims from Wikipedia (Sathe et al., 2020).
[[Paper](https://www.aclweb.org/anthology/2020.lrec-1.849.pdf)] 
[[Dataset](https://github.com/wikifactcheck-english/wikifactcheck-english)]
* TabFact: A Large-scale Dataset for Table-based Fact Verification (Chen et al., 2020). 
[[Paper](https://openreview.net/pdf?id=rkeJRhNYDH)]
[[Dataset](https://github.com/wenhuchen/Table-Fact-Checking)]
* FEVEROUS: Fact Extraction and VERification Over Unstructured and Structured information (Aly et al., 2021)  
[[Paper](https://arxiv.org/abs/2106.05707)] 
[[Dataset](https://fever.ai/resources.html)]
[[Code](https://github.com/Raldir/FEVEROUS)]


## Shared Tasks
* The Fact Extraction and VERification (FEVER) Shared Task [[4th FEVER Workshop](https://fever.ai/)] The shared task is ongoing!
* Statement Verification and Evidence Finding with Tables (SEM-TAB-FACT) [[Wang et al., 2021](https://competitions.codalab.org/competitions/27748)] 
* SciFact Claim Verifiation [[Wadden et al., 2020](https://sdproc.org/2021/sharedtasks.html#sciver)]
* Fakeddit Multimodal Fake News Detection Challenge [[Nakamura et al., 2020](https://competitions.codalab.org/competitions/25337#learn_the_details)]
* SemEval-2019 Task 7: RumourEval, Determining Rumour Veracity and Support for Rumours [[Gorrell et al., 2019](https://www.aclweb.org/anthology/S19-2147/)]
* SemEval-2019 Task 8: Fact Checking in Community Question Answering Forums [[Mihaylova et al., 2019](https://www.aclweb.org/anthology/S19-2149/)]
* The Fake News Challenge (FNC-1) [[Pomerleau and Rao, 2017](http://www.fakenewschallenge.org/)]
* A Retrospective Analysis of the Fake News Challenge Stance-Detection Task [[Hanselowski et al., 2018](https://www.aclweb.org/anthology/C18-1158/)]
* The Fact Extraction and VERification (FEVER) Shared Task [[Thorne et al., 2018](https://www.aclweb.org/anthology/W18-5501/)]
* SemEval-2017 Task 8: RumourEval: Determining rumour veracity and support for rumours [[Derczynski et al., 2017](https://www.aclweb.org/anthology/S17-2006/)]
* The Fake News Challenge (Pomerleau and Rao, 2017) 
[[Dataset](https://github.com/FakeNewsChallenge/fnc-1)]


## Model
* [FEVER 1.0 Baseline](https://github.com/sheffieldnlp/fever-naacl-2018)
* Combining Fact Extraction and Verification with Neural Semantic Matching Networks (Nie et al., 2019).
  [[Paper](https://arxiv.org/pdf/1811.07039.pdf)]
  [[Code](https://github.com/easonnie/combine-FEVER-NSMN/)]
* UCL Machine Reading Group: Four Factor Framework For Fact Finding (HexaF) (Yoneda et al., 2018).
  [[Paper](https://www.aclweb.org/anthology/W18-5515.pdf)]
  [[Code](https://github.com/uclmr/fever)]
* UKP-Athene: Multi-Sentence Textual Entailment for Claim Verification (Hanselowski et al., 2018).
  [[Paper](https://www.aclweb.org/anthology/W18-5516.pdf)]
  [[Code](https://github.com/UKPLab/fever-2018-team-athene)]
* Team Papelo: Transformer Networks at FEVER (Malon, 2018).
  [[Paper](https://www.aclweb.org/anthology/W18-5517.pdf)]
  [[Code](https://github.com/necla-ml/fever2018)]
* Team DOMLIN: Exploiting Evidence Enhancement for the FEVER Shared Task (Stammbach and Neumann, 2019).
  [[Paper](https://www.aclweb.org/anthology/D19-6616.pdf)]
  [[Code](https://github.com/necla-ml/fever2018)]
* GEAR: Graph-based Evidence Aggregating and Reasoning for Fact Verification
  [[Paper](https://www.aclweb.org/anthology/P19-1085.pdf)]
  [[Code](https://github.com/thunlp/GEAR)]
* Fine-grained Fact Verification with Kernel Graph Attention Network
  [[Paper](https://www.aclweb.org/anthology/2020.acl-main.655.pdf)]
  [[Code](https://github.com/thunlp/KernelGAT)]
* Where is your Evidence: Improving Fact-checking by Justification
Modeling (Alhindi et al., 2018).
[[Paper](https://www.aclweb.org/anthology/W18-5513.pdf)]
[[Code](https://github.com/Tariq60/LIAR-PLUS)]
* Generating Fact Checking Explanations (Atanasova et al., 2020).
[[Paper](https://www.aclweb.org/anthology/2020.acl-main.656.pdf)]
* Time-Aware Evidence Ranking for Fact-Checking (Allein et al., 2020).
  [[Paper](https://arxiv.org/pdf/2009.06402.pdf)]


## Related Task


## Surveys

* A Survey of Fake News: Fundamental Theories, Detection Methods, and Opportunities (Zhou and Zafarani, 2020).
[[Paper](https://dl.acm.org/doi/10.1145/3395046)]
* A Survey on Natural Language Processing for Fake News Detection (Oshikawa et al., 2020).
[[Paper](https://www.aclweb.org/anthology/2020.lrec-1.747.pdf)]
* Detection and Resolution of Rumours in Social Media: A Survey (Zubiaga et al., 2018).
[[Paper](http://kddlab.zjgsu.edu.cn:7200/research/rumor/Detection%20and%20Resolution%20of%20Rumours%20in%20Social%20Media_%20A%20Survey.pdf)]
* Automated Fact Checking: Task Formulations, Methods and Future Directions (Thorne and Vlachos, 2018).
[[Paper](https://www.aclweb.org/anthology/C18-1283.pdf)]
* Fake News Detection on Social Media: A Data Mining Perspective (Shu et al., 2017).
[[Paper](https://arxiv.org/pdf/1708.01967.pdf)]


## Tutorials
* Fact Checking: Theory and Practice [[Dong et al., KDD 2018](https://shiralkarprashant.github.io/fact-checking-tutorial-KDD2018/)].
* Fact-Checking, Fake News, Propaganda, and Media Bias: Truth Seeking in the Post-Truth Era [[Nakov and Da San Martino, EMNLP 2020](https://propaganda.qcri.org/emnlp20-tutorial/)].
* Detection and Resolution of Rumors and Misinformation with NLP [[Derczynski and Zubiaga, COLING 2020](https://www.aclweb.org/anthology/2020.coling-tutorials.4.pdf)] [[slides](https://docs.google.com/presentation/d/1ZBVPtHcVgJW2c_ibrdVuoCH7sU9ha8NS7Fq9GCnBnls/edit?usp=sharing)].



