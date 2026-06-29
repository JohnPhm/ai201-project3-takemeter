# ai201-project3-takemeter

This project's intention was to parse information from posts on the r/NBA subreddit and classify them into three different categories. These categories include analysis, hot take, and reaction.

The model itself did yield some misclassifications. Examples of this include "THE OKLAHOMA CITY THUNDER HAVE BEEN ELEIMINATED FROM THE 2026 NBA CHAMPIONSHIP CONTENTION" (which was predicted to be an analysis when it should have been a reaction), "Giannis has 1 playoff series win over the last 5 years. This trade wiill be a disaster for Miami" (which was predicted to be an analysis when it was a hot take), or "Allen Iverson in Australia. Absolutely disgusting." (which was predicted to be a hot take when it should have been a reaction). The model misclassified these due to the context and reasoning behind the post. The model does not have access to the entire post with the user's comments and reasoning for the title so its judgement is misled. This lack of context provided for the model prevents it from making accurate judgement of how to label each post. 

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

Sample Classifications:
Example 1: "With all the discussion about the Heat's current roster situation, I am hearing that they also retained reigning slamdunk champion Keshad Johnson in the deal." 
The predicted label for this sample was analysis with a confidence of 0.37. The actual label should be a reaction. 
This label is reasonable as the model is missing the context of the post. The user is writing this post in reaction to the Giannis trade to the Miami Heat, where a good chunk of the roster has been traded out of Miami in exchange for Giannis. The user posts this as a satirical piece, poking fun at the situation the Miami Heat is currently facing. This is the context that the model is missing. 

Example 2: "THE OKLAHOMA CITY THUNDER HAVE BEEN ELEIMINATED FROM THE 2026 NBA CHAMPIONSHIP CONTENTION" 
The predicted label for this sample was an analysis with a confidence of 0.35. The actual label for this post should be a reaction. The timing for this post was immediately after the Oklahoma City Thunder have been eliminated from the playoffs. The user's intent behind the post was to slander the Thunder as they do not favor that team. Although the post's title was accurate with the Thunder being eliminated, the context and entire post revolves around poking fun at the Thunder's fanbase for being eliminated despite having the current MVP and being the best team in the league. 

Reflection: 
The model was able to capture the meaning behind the titles for each reddit post through parsing the CSV file. Though it was successful, the model was unable to capture the context behind each post. It heavily relied on the meaning of the text, despite potential users poking fun at different situations in the NBA through satirical posts. 

AI Usage: 
There were multiple instances where AI was used in this project. On the Colab "ai201_project3_takemeter_starter_clean", there were several errors when I attempted to run each cell. I used the included Google Gemini AI assitant to help detect and debug the errors. There was an error in the baseline metrics cell that read "ValueError: Number of classes, 0, does not match size of target_names, 3." The AI assistant helped me track down the line where the error was and provided the reasoning as to why this error was occurring. It also provided me a potential fix, which saved me a substantial amount of time. 
Another instance that I used Google Gemini on Colab would be to explain the function def classify_with_groq(text). I read through the function and attempted to edit the code as there were some errors but I chose to use Gemini to first provide me an explanation to how the function worked before I needed to debug and edit the code within the cell. It informed me that the error did not technically reside in this cell and that it was a previous cell so revising the function would not be worth the hassle. 
