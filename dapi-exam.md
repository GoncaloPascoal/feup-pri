
# DAPI Exam

*Answers do not consider 'No Answer' options*

**1.** D ❓  
**2.** C ✅  
**3.** D ✅  
**4.** A ✅  
**5.** C ✅  
**6.** A  
**7.** C ✅  
**8.** D ✅  
**9.** C ✅  
**10.** B ✅  
**11.** C ✅  
**12.** C ✅  
**13.** B ✅  
**14.** D ✅  
**15.** D ✅  
**16.** D ✅  
**17.** A ✅  
**18.** A ✅  
**19.** ✅

Since there are 20 relevant documents in the collection, recall increases by 5%
(1/20) each time a relevant document is retrieved. Thus, the recall-precision
pairs are:

| Recall | Precision |
| --- | --- |
| 5% | 33.3% |
| 10% | 33.3% |
| 15% | 42.9% |
| 20% | 40% |
| 25% | 33.3% |
| 30% | 27.3% |

**20.** ✅
```
AP = (1/3 + 2/6 + 3/7 + 4/10 + 5/15 + 6/22) / 6 = 0.3502 = 35.02%
```

**21.** A ✅  
**22.** A ✅  
**23.** C ✅  
**24.** C ✅  
**25.** C ✅  
**26.** B ✅  
**27.** B ✅  
**28.** A ✅  
**29.** D ✅  
**30.** C ✅  
**31.** D ✅  

In your project you selected datasets and considered search functionalities for the data. What is your dataset? Give a name and a very short description of it and its contents.

**32.** The dataset used in our project, Steam Games and Reviews, aggregates Steam game
information from many different sources (Kaggle for the base dataset, ProtonDB for
Linux compatibility information, HowLongToBeat for expected playtime, SteamSpy for
tags and player count information, user reviews from the Steam Store and articles
from Wikipedia). Information was obtained through many different methods, such as
direct downloads, public APIs or website scraping.

**33.** Our search system indexes two different types of documents: games and
reviews. Game documents all contain some base information such as name, release
date, genres, tags and descriptions. Other related information, such as Linux 
compatibility scores, Wikipedia article extracts and expected playtime is optional.

Review documents contain the actual review text, some specific metadata such as
user votes or whether the product was obtained for free, and some information
about the game being reviewed (such as the name or tags) to allow for more expressive
queries. This information is also present in the corresponding game document.

A game can have several user reviews and a user can review several different games,
but each user can only review a particular game once.

**34.** 

**35.** 
