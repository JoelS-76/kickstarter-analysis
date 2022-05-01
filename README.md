# Kickstarter Analysis
Analysis of various data from kickstarter to find trends
The Client ("Louise") plans a Crowdfunding campaign to raise $10,000 to fund her play production. I am analyzing data to see if there are any trends that distiguish successful campaigns from failed campaigns, to give Louise a better chance to succeed.

#### Narrowing the dataset
Since Louise is producing a play, I narrowed the field to look at all theater campaigns, and also all play productions within that category (As opposed to funding for spaces and for musicals). ![image](https://user-images.githubusercontent.com/84299125/121837021-e1781680-cc91-11eb-94c8-d5a10e2dada1.png)![image](https://user-images.githubusercontent.com/84299125/121837086-0bc9d400-cc92-11eb-8287-a25215bb3d29.png). 

## Challenges
My own challenges in performing this analysis were mainly limited to the newness of the material and my lack of familiarity with the excel formulas. I had some trouble with the COUNTIFS function, which I used for some fairly long formulas. It took me some time (and some assistance) to remember how to lock my cell ranges in the formulas. Eventually I realized that I was placing the $ before the column position but not the row number. This problem cost me quite a bit of time. Also, there was so much data it was tempting to run various analyses on far more information than would truly be helpful, simply out of personal curiosity.

## Main Analysis
### Theater vs Launch
There were two main analyses: the outcomes of theater projects according to launch date, and the correlation between project outcomes and their financial goals.
The analysis of theater projects by date revealed that May had the highest number of successful projects, although anytime between April and August was above average. This was also the period of highest general activity; i.e., there were more projects going live during that time. May also had the highest number of failed projects. However, the difference between successful and failed projects was more significant in May than any other month. https://github.com/JoelS-76/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png

### Outcomes vs Goals
The research of Theater outcomes relative to goal amount revealed the highest success rate for projects under $5,000. The respective rates of success and failure cross just above $10,000. Rates for projects higher than that amount cross multiple times, revealing little or no correlation, presumably due to small sample size. Above $15,000 the number of total projects may be too small to draw any reliable conclusions. https://github.com/JoelS-76/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png

## Limitations
This dataset cannot explain why more people supported one project than another, or why May had such a high success rate. The table below is derived from the collection of successful plays in the US. Projects in May were slightly below average in both number of backers and average donation amount. October had the highest number of backers per successful outcome, and November averaged the highest donation amount. ![image](https://user-images.githubusercontent.com/84299125/121882798-39cd0980-ccce-11eb-8ed1-a98f12373044.png) 

Nevertheless, May was by far the most successful month, and also had the widest variance between successful and failed projects.

## Other possible angles of research
We could also create a table that would tell us if there is a correlation between staff picks, spotlight projects, and success rates, which would give us some idea how effective various marketing tools are.

Something I noticed perusing the dataset was that the blurbs for several successful projects tended to be more well-written, more focused, and more clear about the project than those for failed projects. It would be interesting to take a sample of failed and successful projects and rate the quality of the blurb relative to the number of backers. It would require some literary analysis as well as a grading system to quantify said quality, and we would have to allow for some subjectivity in that analysis. But that could be a key element in attracting more backers for a project. That would be a much more time consuming avenue of research, so it is unlikely to be helpful for this project. However, since Louise also wants to fund a play for the Edinburgh festival, it might be worth looking at for future projects.

## Machine Learning
I created and ran a machine learning model to address some of the above ideas in the "Other possible angles" section. I selected a Balanced Random Forest Classifier, because I wanted to discover how close the correlation was between various different criteria. The strongest correlation by far was in spotlight projects. Below is a list of the top 5 correlating features.

![image](https://user-images.githubusercontent.com/84299125/166140092-272c08d3-3294-4201-8686-2cbda00ca585.png)

The number of backers was typically more important than the average donation. The goal was more likely to be reached by many giving a little than by few giving a lot. Yet, as we already saw, May was below average in number of backers and still was the most successful month. Now we should look at the projects in May to find further correlation there.
