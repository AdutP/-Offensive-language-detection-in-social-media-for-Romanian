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
2. Built a [Trello page](https://trello.com/b/wBNqe7h3/offensive-language-detection-in-social-media-for-romanian) for monitoring process.
