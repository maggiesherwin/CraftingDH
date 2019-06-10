# Week 5
## Activities
### Gephi
- Downloaded Gephi
- Load .csv into Gephi
- Copy Id to Label
- Set layout to Force Atlas 2
- Notice the outliers that are not part of the larger network
- Remove the outliers by running `connected components` under statistics, and select undirected
- Close the popup graph
- Go to Filters > Attributes > Equal > Component ID
- Set value to 0 and run
- Outliers are gone!
- Statistics > Page Rank > Run > Directed > OK > Close
- Appearence > Nodes > Size > Ranking > PageRank > Min 1 Max 10 > Apply
- Reduce size of lines to avoid weird looking stuff
- Layout > Force Atlas 2 > Prevent Overlap > Run
- Go to Preview
- Select "Show Labels," "Proportional Size," "Rescale Weight," and deselect "Curved" edges.
- Select Refresh
- Save as a `.graphml` file
### Topic Modeling Tool
- Download Topic Modeling Tool 
- Download Colonial Newspaper Database and place it in a folder
- Open Topic Modeling Tool
- Set the Input Directory to the folder I made containing the CND
- Set output directory to my donwloads folder
- Click Learn Topics and go through that
- Go to the newly created folders in Downloads
- Open output_html and open all_topics.html in a browser
- Wow! Those are some topics!
- Clicked around a bit
- Put the folders into my class folder
### Topic Modeling in R
#### No errors in this exercise!
    - install.packages("mallet")
    - library("mallet")
    - install.packages("RCurl")
    - library("RCurl")
    - x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))
    - documents <- read.csv(text = x, col.names=c("Article_ID", "Newspaper Title", "Newspaper City", "Newspaper Province", "Newspaper Country", "Year", "Month", "Day", "Article Type", "Text", "Keywords"), colClasses=rep("character", 3), sep=",", quote="")
    - counts <- table(documents$Newspaper.City)
    - barplot(counts, main="Cities", xlab="Number of Articles")
    - years <- table(documents$Year)
    - barplot(years, main="Publication Year", xlab="Year", ylab="Number of Articles")
    - Created and filled en.txt
    - mallet.instances <- mallet.import(documents$Article_ID, documents$Text, "en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")
    - #documents <- mallet.read.dir("/home/maggiesherwin/CND")
    - #mallet.instances <- mallet.import(documents$id, documents$text, "en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")
    - num.topics <- 20
    - topic.model <- MalletLDA(num.topics)
    - topic.model$loadDocuments(mallet.instances)
    - vocabulary <- topic.model$getVocabulary()
    - word.freqs <- mallet.word.freqs(topic.model)
    - head(word.freqs)
    - write.csv(word.freqs, "word-freqs.csv" )
    - topic.model$setAlphaOptimization(20, 50)
    - topic.model$train(1000)
    - topic.model$maximize(10)
    - doc.topics <- mallet.doc.topics(topic.model, smoothed=T, normalized=T)
    - topic.words <- mallet.topic.words(topic.model, smoothed=T, normalized=T)
    - mallet.top.words(topic.model, topic.words[7,])
    - topic.docs <- t(doc.topics)
    - topic.docs <- topic.docs / rowSums(topic.docs)
    - write.csv(topic.docs, "topics-docs.csv" )
    - topics.labels <- rep("", num.topics)
    - for (topic in 1:num.topics) topics.labels[topic] <- paste(mallet.top.words(topic.model, topic.words[topic,], num.top.words=5)$words, collapse=" ")
    - topics.labels
    - write.csv(topics.labels, "topics-labels.csv")
    - plot(hclust(dist(topic.words)), labels=topics.labels)
    - plot(hclust(dist(topic.words)))
    - topic_docs <- data.frame(topic.docs)
    - names(topic_docs) <- documents$article_id
    - install.packages("cluster")
    - library(cluster)
    - topic_df_dist <- as.matrix(daisy(t(topic_docs), metric = "euclidean", stand = TRUE))
    - topic_df_dist[ sweep(topic_df_dist, 1, (apply(topic_df_dist,1,min) + apply(topic_df_dist,1,sd) )) > 0 ] <- 0
    - install.packages("igraph")
    - library(igraph)
    - g <- as.undirected(graph.adjacency(topic_df_dist))
    - layout1 <- layout.fruchterman.reingold(g, niter=100)
    - plot(g, layout=layout1, edge.curved = TRUE, vertex.size = 1, vertex.color= "grey", edge.arrow.size = 0, vertex.label.dist=0.5, vertex.label = NA)
    - write.graph(g, file="cnd.graphml", format="graphml")
#### Okay, so one error, caused by trying to read from both the web and a directory. The lines causing the issue are marked with # above. This was solved by removing these two lines: 
 - ~~documents <- mallet.read.dir("/home/maggiesherwin/CND")~~
 - ~~mallet.instances <- mallet.import(documents$id, documents$text, "en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")~~
### Overview
- Lorem ipsum
### AntConc
- Lorem ipsum
### Voyant
- Lorem ipsum
### RAW
- Lorem ipsum
### Mapping and Georectifying
- Lorem ipsum
### Network Analysis in R
- Lorem ipsum
### QGIS
- Lorem ipsum
### TensorFlow
- Lorem ipsum
