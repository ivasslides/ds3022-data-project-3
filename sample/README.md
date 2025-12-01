# Team Cool

## Team members
Iliana Vasslides and Claire Bassett 


## Data Source

*What data source did you work with?*
We continued to work with the BlueSky firehose for our data source. 


## Challenges / Obstacles

*What challenges did this data choice present in data gathering, processing and analysis, and how did you work through them? What methods and tools did you use to work with this data?* 


This data choice was actually our third choice of a source, because the two previous news APIs that we were trying to work with were not ending well. One main challenge we faced during data processing was determining what columns, aka information from each message/post, we wanted to keep and use for our analysis. Besides simply choosing what information we wanted, it took us a couple tries to figure out the pattern of the nested tree to appropiately extract specific data labels. Additionally, the first time we ran our Kafka Consumer it was taking over 10 hours and so we had to troubleshoot that in order to consume our data in an appropiate amount of time to be able to analysis as well. We solved this issue by removing time.sleep() from inside the consumer try block, and only having it present if there was an error consuming a record. After removing that line of code, we were able to process over 1,000 records ever 10 seconds, which was much more managable. 

During data analysis, a challenge we struggled with was deciding how to use a sentiment analysis on our data when it was in multiple languages, not just English. We used the package langdetect to help us with this process. Using this packages, we only kept the rows that were in English to make our sentiment analysis easier. 

To perform our sentiment analysis, we used pipline from transformers. This package made the process extremely easy and gave us nice summaries to then apply to our graphs. The only small challenges with this package was figuring out the proper format to make the text and how to map the keywords we pulled to each specific mogul and their company. 



## Analysis

*Offer a brief analysis of the data with your findings. Keep it to one brief, clear, and meaningful paragraph.*

For our analysis, we compared sentiment analysis on the top 5 tech moguls compared to their respective companies. We then created two bar graphs to show the number of posts that showed each sentiment for the different tech moguls and their companies. It was unsurprising that overall the companies were mentioned in a higher number of posts than almost all of the moguls. Additionally, it was unsurprising that Elon Musk was the most mentioned tech mogul, with a much higher negative sentiment than the others given some previous and current happenings in the news and the US. However, the most surprising finding was that for each mogul and company alike, there was more negative sentiments than positive. We originally thought that only a few moguls or companies would have this large of a difference between the number of posts showing each sentiment, but few showed an equal sentiment of each mogul or company. This could possibly hint that BlueSky users have strong negative feelings towards technology and other monopolistic companies. Given the overall negative feelings towards these people and companies, users who post on BlueSky are more likely to post negative thoughts about technology than positive ones. 


## Plot / Visualization

*Include at least one compelling plot or visualization of your work. Add images in your subdirectory and then display them using markdown in your README.md file.*

## GitHub Repository

Github Repo: https://github.com/clairembassett/bluesky-tech-sentiment/tree/main 