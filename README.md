# Offensive-language-detection-in-social-media-for-Romanian
by Toxic Players

- **Elena Calmis**
- **Liliana Gavrilas**
- **Adrian Plesescu** (project leader)

##  Links
> [Trello](https://trello.com/b/wBNqe7h3/offensive-language-detection-in-social-media-for-romanian)
> 
> [Project Description Document](https://docs.google.com/document/d/195N0kqXc-AFzPUR4RPY2n59n6XzWKZrdynWKp9xj4jk/edit?usp=sharing)

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
6. As for the next sprint, we can think more about the difficulties we faced and also work at the tokenization, stemming, lemmatization and pos tagging. I think this will give us a clearer picture on how we need to adapt our corpus for real work and a bit of insight on the ML algorithm / neural network we will use in the weeks to come.
7. We have also worked on the frontend side(one main page with a textbox + a second page for the result). This said, we leave an open door for next improvements like advanced options / filtering and black box interpretations.

##  Week 5 (17.mar - 24.mar)
### Preprocessing module
1. This weeks's attention was on resources that can help us preprocess data. We managed to write a script that normalizes, removes stop words and punctuation marks and lemmatizes random texts.
2. Using these 2 links we received last week: [the TEPROLIN documentation](http://relate.racai.ro/index.php?path=teprolin/doc_dev) and [the UAIC Natural Language Processing Group's Resources and Tools](http://nlptools.info.uaic.ro/Resources.jsp?fbclid=IwAR1LZO5t4sT8n96b1OVvz7-BrqH5FAovJG1tMuYl0TjSsH65pK46XPEiryU), we enriched our understanding on preprocessing and our NLP vocabulary(anaphora, chunking, etc.).
3. Through TEPROLIN's API, we fed a sentence and received its POS tagging, followed by lemmatization.
4. We compared different methods of lemmatization inluding the snowball lemmatizer and the one TEPROLIN provides us, concluding that the second delivers a better performance. We will use TEPROLIN further in the project and hope its standardized format will help us in the integration process.
5. We researched language models and how can we build one using an existing corpus for Romanian. We tried using Rowordnet but failed discovering that synsets can be valuable later on. Not being able to easily import a Romanian corpus through nltk(because there is none available in the nltk.corpus) and not being able to download parts of CoRoLa, we are still trying to find a solution.
6. Everyone filled out the SWOT part of the project descripton file, but sections such as goal and qualitative benchmarks are needed to be further discussed.
7. Research about input has led us to [this article](https://blog.insightdatascience.com/how-to-solve-90-of-nlp-problems-a-step-by-step-guide-fda605278e4e), which will serve as guideline. 
8. We centralized the corpus comment files and counted the annotated texts: ~3000

##  Week 6 (24.mar - 31.mar)
### Corpus integration and ML tryouts
1. This week we had a second collaboration/exchange with another team =>TEPROLIN connection / <=a large corpus(~12.000 non-offensive & ~6.000 offensive comments). This came at a good time for us, giving that we had already planed to implement preprocessing operations on our dataset. After we took a look at this new corpus, it became obvious that we had a "positive bias", and based our classification of offensive comments on other criteria.
2. We compiled the received dataset in a .csv file and began adding our own comments to lower the inbalance between the 2 categories. This meant converting our -1/0/1 system to a 0/1.
3. We used our stop word removal and tokenization in conjuction with TEPROLIN's POS tagging(also gives us the lemma). 
4. We researched how POS tagging can influence and create a feature in the Naive Bayes algorithm. This lead us to implement our own algorithm, but also test pre-built ones such as those provided by [scikit learn](https://scikit-learn.org/stable/).
5. Thought of filters for detecting misspelings(internal) and a spellchecker module for Romanian(an external one but no results).
6. We researched [BERT](https://mccormickml.com/2019/05/14/BERT-word-embeddings-tutorial/) but have to build a larger knowledge base in order to fully understand it.
7. We found new resources to use in the next 2 weeks: [BERT](https://www.youtube.com/watch?v=FKlPCK1uFrc&list=PLam9sigHPGwOBuH4_4fr-XvDbe5uneaf6), [Voting Process](https://www.youtube.com/watch?v=vlTQLb_a564&list=PLQVvvaa0QuDf2JswnfiGkliBInZnIC4HL&index=16) and [NLP-Cube](https://github.com/adobe/NLP-Cube), [udpipe](https://ufal.mff.cuni.cz/udpipe), [paperswithcode.com](https://paperswithcode.com/area/natural-language-processing)(from the 30.mar course) 

## Week 7 (- 14.apr)
### Demo of basic functionalities
1. Started working on a shared Google Colab notebook, and managed to test one Naive Bayes algorithm and a SVM network uing scikit-learn. We reached an impressive detection rate of over 90% for our original smaller corpus.
2. Integration is the name of the game now as we rush to finish the basic functionalities. We bottlenecked firstly because we do not heve well-defined in-code modules. So we want to decouple some of our files and better organze the project.
3. We downloaded TEPROLIN on a virtual machine to avoid overloading the main server with thousands of requests given our corpus size. We used the offered [docker container](https://github.com/racai-ai/TEPROLIN#docker-container). We still have to test the pos tagging and lemas we get from this.
4. The corpus is growing in offensive words, and for the spelling mistakes we continue to see, we adopted a strategy that will be implemented by first developing modules for finding whether or not a text is in Romanian/ a word is correctly written in Romanian.
5. In order to highlight the offensive part of a longer phrase, we decided to go for a segmented input aproach. So we first need to split a comment in text segments and feed them to the algorithm condecutively, thus calculating a offensive score for each segment. Then, we will have a general idea where the expression/ bad word is found, so we could provide a visual supervised feedback to the user.
6. We are in the process of integrating a module that detects text zones/ ROI in an image and censors any offensive text. We already had some code along the lines of OCR text detection and we figured it will come usefull in this project too. Its main utility is to capture offensive material in images with clear text, preferably black on white(memes, ad campains and screenshots). We are using easyocr to find the ROI and tesseract to extract the text. We might go only with easyocr after some more testing and some driver installs because it is the slowest between the 2. All other image processing is done with OpenCV.
