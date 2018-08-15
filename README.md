# TopicDistributions
Distribution of topics in the plenary debates of the European Parliament and in the legislative documents of the European Union

This repository contains data on the topics discussed in the Europan Parliament, and represented in the legislative documents of the European Union, between 1999 and 2017.

The raw data of the discussions in the European Parliament was taken from the "Talk of Europe" project (www.talkofeurope.eu). It is available here:

https://easy.dans.knaw.nl/ui/datasets/id/easy-dataset:76464

The legislative documents of the European Union were downloaded from the EUR-lex website:

https://eur-lex.europa.eu/

Only documents of categories 'D' (decisions), 'L' (directives) and 'R' (regulations) were downloaded (cf. https://eur-lex.europa.eu/content/tools/TableOfSectors/types_of_documents_in_eurlex.html). Each document is uniquely identifiable by a CELEX-number, consisting of "3" + year + category + document_id, e.g. 31999D0001 for the first decision of the year 1999.

The data was preprocessed (e.g. removing punctuation and stopwords) using the Python Natural Language Toolkit:

https://www.nltk.org/

A Latent Dirichlet Allocation (LDA) model was fitted to the data, using the Python library gensim:

https://radimrehurek.com/gensim/

The models were validated by comparison with the EUROVOC-descriptors associated with the EUR-lex documents. They are provided by the European Union upon request (via the EUR-lex-website; note that only small datasets can be exported, and the maintainers are often slow in responding to enquiries.)

This repository contains the following data:
- Four LDA-models with differing numbers of topics (80, 100, 120, 150), to capture different degrees of specificity/generality (zip-file). --> folder 'models'
- Visualizations for the four models (html-files). --> folder 'visualizations'
- The topic probabilities for all documents in the dataset; contributions to the plenary debate in the European Parliament are identified in the following format: "lp_eu:" + year-month-day-"Speech"-debate_id-speech_id, e.g. "lp_eu:1999-07-20-Speech-2-001" for the first speech of the second debate on 20 July, 1999. The EUR-lex documents are identified by their CELEX-number (tar-archive). --> archive 'topic_probabilities.tar.gz'
- The propotion of text per topic for 6-months periods, starting Dezember 1998 -- May 1999 (period 1) and ending June 2017 -- November 2017 (period 40) (tsv-files within zip-file. --> folder 'topic_proportions_per_period'

More data can be provided upon request (gast@zedat.fu-berlin.de)
