1.My Activities
===

## Experience
Language:  
Python3, Ruby on Rails, C++, csh, Octave
 - I am major in natural language processing, so I usually write in Python3 for researches.  
    - especially dependency parsing and Language Modeling 
 - Experience of Web Developing by Ruby on Rails
    - including HTML/CSS (SCSS,bootstrap), JavaScript, PostgreSQL, PaaS (Heroku)
 - Algolithms & data structures written in C++
    -  Aizu Online Judge ALDS completed (http://judge.u-aizu.ac.jp/onlinejudge/user.jsp?id=samayotta)  
 - Experience of developing CLI tools
 - Machine Learning on Statistics such as regression, classification, PCA and LDA on Python & Octave. 

Work:  
 - Shinsuke Mori laboratory, Kyoto University, Office Assistant (June 2016 ~ March 2017)  

## Products  

### Text2Feature
Text2Feature is an OSS Japanese document search engine written by Python3.  
Text2Feature runs on UNIX.  
This system is adopted by “Q&A communication system" SHARP CLOUD LABS. http://qac.cloudlabs.sharp.co.jp/  
GitHub: https://github.com/IKKO-Ohta/Text2Feature  

Job:
 - June 2016 ~ December	2016 	*engineer*  
 - December 2016 ~ March 2017 	*Chief engineer*  

release:
 - April 2016	OSS version 1.0  released

### VCS-Mirador
VCS-Mirador is a Web app for humanities research. 
This app is mainly written by Ruby on Rails.  
Supporting IIIF/International Image Interoperability Framework(http://iiif.io), this system make them “Documents”. The document has annotations,hypotheses and comments. If you want, your document is only shared by authorized group.   
In addition, this system has some SNS functions.  

α Version was announced in SIG-CH 2017.This project is improving!  
GitHub: https://github.com/IKKO-Ohta/VCS_mirador  

production:
 - Heroku
 - PostgreSQL

Job:
 - April 2017 ~ 	*Chief engineer*  

2.Text2Feature
===

### What is Text2Feature?  
Text2Feature is a OSS Japanese Document Search Engine.  
With morphological analysis & dependency analysis, Text2Feature TF-IDF vectorizes existing documents. And this engine receives a query document, calculates cosine similarity between the input and the vectorized documents, and find ones which similar to the query.   

Here is an example.
> ![make_index](https://github.com/IKKO-Ohta/others/blob/master/makeindex_ss.png)
### Purposes & Goals  
One of the our project’s purpose is to provide document search engine easy for everyone to use. As a result SHARP CLOUDS LABS’s service “Q&A communication system” did.   
We continue to improve Text2Feature to aquire more and more users!

### T2F’s Beautiful Points  
**Accurately and speedy!**  
We have implemented some useful methods.  
At first, we adopted the option features called “Dep_n_gram”. If you want, T2F considers dependency analysis’s result as one of features. Here is an example of dep_bi_gram:  

> input string: “太郎はおにぎりを食べる。”   
> features by unigram: [“太郎”,”は”,”おにぎり”,”を”,”食べる”]  
> features by unigram + dep_bi_gram: [“太郎”,”は”,”おにぎり”,”を”,”食べる”,”太郎-は”,”おにぎり-を”,”は-食べる”]  

This option may improve the accuracy slightly in specific area.  

Secondly we implements some manual configuration functions such as “”synonym,“ “blacklist” and ”whitelist.” These configuration may look like not smart. However when your available resource is limited, these functions can help you to keep your product’s accuracy.  

Thirdly we builded the effective models of morphological analysis & dependency analysis. Especially in dependency analysis, our model is much lighter than naive methods. And our model is not only speedy & memory efficient but also accurate.  

### T2F’s file structure & flow ![FileStructure](https://github.com/IKKO-Ohta/others/blob/master/t2f_structure.png)  
 - bin/  
    - **Makeindex.csh**:	 set_up database  
    - **Vectorize.csh**:	 calculate query doc  
 - auto/  
 - model/  
    - **KyTea model**:	for morphological analysis  
    - **EDA model**: 	for dependency analysis  
 - corpus/  
    - **makeindex/**:	text to calculate  
    - **newtext/**: 	preprocessed queries  
    - **thesaurus.txt**:	     synonym, whitelist, blacklist  
 - lib/  
![flow](https://github.com/IKKO-Ohta/others/blob/master/vectorize.png)  
Here is T2F's processing flowchart.  
These processing ["preprocess","parse","vectorize"] correspond with ["preprocess.py","parse.py","vectorizer.py"] in the lib/.  

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
