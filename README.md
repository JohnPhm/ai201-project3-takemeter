# ai201-project3-takemeter

This project's intention was to parse information from posts on the r/NBA subreddit and classify them into three different categories. These categories include analysis, hot take, and reaction.

The model itself did yield some misclassifications. Examples of this include "THE OKLAHOMA CITY THUNDER HAVE BEEN ELEIMINATED FROM THE 2026 NBA CHAMPIONSHIP CONTENTION" (which was predicted to be an analysis when it should have been a reaction), "Giannis has 1 playoff series win over the last 5 years. This trade wiill be a disaster for Miami" (which was predicted to be an analysis when it was a hot take), or "Allen Iverson in Australia. Absolutely disgusting." (which was predicted to be a hot take when it should have been a reaction). The model misclassified these due to the context and reasoning behind the post. The model does not have access to the entire post with the user's comments and reasoning for the title so its judgement is misled.

The evaluation results json file and the confusion matrix are attached in this repository but the information that it contains are as detailed. 

evaluation_results.json:
baseline_accuracy	0.4333
finetuned_accuracy	0.5
improvement	0.0667
test_set_size	30
label_map	
Analysis	0
Hot Take	1
Reaction	2
model	"distilbert-base-uncased"

confusion_matrix.png:
<img width="1050" height="750" alt="confusion_matrix" src="https://github.com/user-attachments/assets/48d7afae-64dc-4d43-a071-db533eb1c09a" />

