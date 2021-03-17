# Offensive-language-detection-in-social-media-for-Romanian
by Toxic Players

- **Elena Calmis**
- **Liliana Gavrilas**
- **Adrian Plesescu** (project leader)

##  Week 1
### Usecases
1. Social Media platforms wanting to monitor and filter offensive content.
2. Gouvernment entities fighting against possible online threats.
3. Antivirus like programs which act as a firewall that blocks children to access certain toxic/ offensive/ hateful contents.
4. Basically all platforms managing a comment section, including online stores, blogs, etc. 

*(censoring notice is forwarded to the offender, prefferably with an atached explanation)*

### Language: Python

##  Week 2
### Previous Work Research
> Eddie Yang and Margaret Roberts from University of California, San Diego published on 22.Jan.2021 the atricle "[Censorship of online Encyclopedia](https://arxiv.org/pdf/2101.09294.pdf)", which discusses the differences of training a NLP model on 2 online encyclopedia: Wikipedia and its Chinese equivalent, Baidu Baike. The researchers found proof of what they initially believed, that censorship influences the classification of words based on their political meaning: for example 'democracy' is more related to 'chaos' then it is to 'stability'. Finally, a news headline analyzer built on top of this had a bias in siding with propaganda ideas and against non-patriots.

##  Week 3
### Corpus Research
1. Brain stormed ideas for gathering [corpus content](https://docs.google.com/spreadsheets/d/1vXtONVagKMbVIvUUwgDBpjeS1uEmiUlqtZZfDh_jPaw/edit?fbclid=IwAR0md6rpmfYsYBEcadvcT6dZ3yCfo7PuoTAlFL9xmgvmPONJKLayaAWm88k#gid=0):
  - [Sentiment Analysis for Romanian](https://github.com/katakonst/sentiment-analysis-tensorflow) -> gets positive (non-offensive comments);
  - [Offensive/Obscene/Vulgar lexicon](https://l.facebook.com/l.php?u=https%3A%2F%2Fdexonline.ro%2Fstatic%2Fdownload%2Fdex-database.sql.gz%3Ffbclid%3DIwAR3maZW15dLaon8mbxjAv-XTcb00VP6A3YyPpza_Ge6nStGsW6_xTdtcj_M&h=AT2pjshPIeuDSKDGQLqifLDRJ-u98iuiKFTAy4Ne9lPpDhg7BigUoG5NtesNdt9L7tAogxALD8P_f1xbVqe5I9cfVKwO6J1OZKbJA_HddLvT2rGXKXyhQzdc9oHxf6n-d_rXdS-HnjofrCi8AIt5Cw) -> gets a list of highly offensive words and expressions from an online dictionary(mainly slang) using regex;
  - [Facebook comment extractor](https://www.commentexporter.com/) -> automates the extraction of Facebook comments from a specific post, needs further manual labeling;
  - Twitch live comments extractor -> a crawler(v.0.1) that combined with [a timed html saving chrome extension](https://chrome.google.com/webstore/detail/autosave-webpage/kfnkfhdbeidcdpdlefbfabepmfhldkoi) produces a list of comments
2. Built a [Trello page](https://trello.com/b/wBNqe7h3/offensive-language-detection-in-social-media-for-romanian) to easily monitor progress.

##  Week 4 (10.mar - 17.mar)
### Corpus and Lexicon Building
1. We updated our existing shallow corpus with thousands of YouTube comments dynamically gathered by a python scrips and a few hundreds from Facebook.
2. Running the last week's sentiment analyzer, we found out that the results were largely inconclusive. 
3. We manually annotated them on the basis of 3 categories = Offensive/ Non-offensive/ Neutral(which we can also count), but at this point we have doubts of the accuracy of these annotations. That is because we discovered that many comments are offensive only looking at the context/ or can be better classified at threats or hate. We surely have to step back and rethink this issue.
4. Having the Romanian Dictionary's(dex) database already downloaded from last week, we queried it based on representative tags/ abbreviations for our specific problem (prst., obs., vulg., eufem, depr.) and filtered them manually. This was done to gather a lexicon of bad words and expressions to use it as a first wall against the use of obscene words, no matter the context. We will be improving it (460+).
5. We currently have to resolve how our program can deal with common abbreviations / misspelled words / emoji combos / popular spellings (more or less like the ones we found in the comments at this time).
6. As for the next spring, we can think more about the difficulties we faced and also work at the tokenization, stemming, lemmatization and pos tagging. I think this will give us a clearer picture on how we need to adapt our corpus for real work and a bit of insight on the ML algorithm / neural network we will use in the weeks to come.
7. We also worked at the frontend (one main page with a textbox + a second page for the result). This said, we leave an open door for next improvements like advanced options / filtering and black box interpretations.
