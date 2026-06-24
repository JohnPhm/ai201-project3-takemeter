Community: 
The community chosen for this project comes from the subreddit r/nba. This community discourse ranges from emotionally-charged game reactions to deeply researched statistical arguments. The three labels for this dataset are analysis, hot-take, and reaction. These labels capture the distinction that the community makes informally between "real arguments" and "takes" as the NBA discourse is quite notorious for claims based on a single statistic. The key boundary rule is that evidence must causally support the claim. These distinctions matter for people of this community as it assists new followers of the NBA to understand the key events of the NBA and allows users to distinguish between what is factual and what are personal opinions.

Labels: 

Analysis - A structured argument based on statistics, historical comparisons, or strategic observations. An example of this would be comparing a team's offensive rating with and without a specific player. For example, the New York Knicks offensive rating dropping from 119.7 to 109.8 without Jalen Brunson on the floor, highlighting his impact.

Hot Take - A bold comment stated either without supporting evidence or evidence doesn't bear any weight. An example of this would be a fan stating that the Golden State Warriors 2010's dynasty was on of the softest dynasties in NBA history.

Reaction - An immediate emotional response to an in-game event, which includes little to no argument as it mainly expresses a feeling in the moment. An example of this would be fans complaining about the referees making last minute calls, causing a team to lose the game. 

Hard Edge Cases:
Any ambiguous cases include posts that have a confident claim with exactly one statistic attached to it but the statistic attached doesn't actually prove the point.

Data Collection Plan:
To collect data on this community, posts from the r/nba subreddit will be pulled and skimmed, more specifically from old.reddit.com/r/nba. These posts will vary in terms of style, including recent game threads and discussion style posts. Since there are three labels, there will be approximately 60-70 examples of each label to ensure that there is an even distribution of the labels. If the label distribution is underrepresented after the 200 examples, then more examples of that labels will be pulled from the r/nba subreddit to even out the label distribution. 

Evaluation Metrics:
To evaluate the model, the Macro F1 and per-class precision and recall is used to determine the performance of the model. Per-class precision and recall allows us to analyze how much each of the label actually successfully labelled each post, looking at the false alarms and the misses. 

Definition of Success: 
To determine the success, we can look at the evaluation metrics and manually review each post to determine if they match the correct label that is associated with them. 

AI Tool Plan:
Label Stress Testing - Ask the AI to generate several posts that purposefully sits at the boundary between two labels.
Failure Analysis - Once the predictions have been created, the list of wrong predictions can be fed into an AI tool so that it can identify pattens before writing about it in the evaluation. Once the AI determines what the pattern is, a manual review would be done to confirm this pattern exists. 


In the labeling of the examples, a couple examples were difficult to determine what label it falls under. An example of this would be "Kobe Bryant a couple days before he tore his Achilles. Hits 4 of the most unbelievable shots you'll ever see to win the game against Toronto." This example was difficult to label as the post was mainly a video clip of Kobe Bryant scoring insane shots to beat the Toronto Raptors. The post includes a description of what happened in the video clip but is also skewed in the sense that it describes Kobe's shots as the best shots you'll ever see. Ultimately, I decided to label this example as a reaction because of the user who uploaded the clip is clearly reacting to the in-game events that transpired. 
