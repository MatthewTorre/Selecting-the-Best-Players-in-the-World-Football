Project Title: Selecting the Best Players in the World Football
Colab Code
Dataset
Introduction
In the world of football, fans love to conversate and compare players. Sports commentators and
sets of rival fans love to make arguments for a player's skill and value to a team. Oftentimes,
professional football clubs and the international football market will place valuations on players
on the basis of their performance. In a sport where there is often a lot of ambiguity and
intangibles that can factor into the decision to sign a player or select a player for individual/team
awards, a statistical baseline for clubs and fans alike to judge the objective ability of players is
incredibly valuable. In this project, our goal is to statistically select the top football players from
the 2021-2022 season using logistic regression introduced in class. In this project we leverage
key player performance metrics (including Goals, Assists, Passes completed, Passes attempted,
Number of players tackled, and Number of loose balls recovered) to identify top performers from
this comprehensive player statistics data set. The process includes data preprocessing, model
training, predictive analytics, and selection of players based on logistic regression outputs.
Data Collection & Considerations
The dataset comprises detailed player statistics from the 2021-2022 football season. Key
performance metrics analyzed include goals, assists, passes completed, pass attempts, tackles,
and recoveries. These metrics provide a solid quantitative foundation for evaluating and
comparing player performance. It is also worth noting that there a several advanced metrics
included in the data set that are not explicitly weighted in our final output, in an extension to this
project we would take into account: Shots on target, SoT% : Shots on target percentage for
attacking players (or attacking minded defensive players), and for goalkeepers more specialized
statistics likes saves, deflections, catch rate, etc.
Methodology:
1) Google Drive Setup and Library Imports:
The project starts by mounting Google Drive in a Google Colab environment to access the
dataset. It imports essential libraries such as pandas for data manipulation, numpy for numerical
operations, sklearn for machine learning functionalities, and visualization libraries like
matplotlib.pyplot and seaborn.
2) Data Loading:
A CSV file containing player statistics from the 2021-2022 season is loaded, using specific
encoding and delimiter settings to correctly parse data with special characters.
3) Data Preprocessing:
Removes rows with missing data for data integrity and retains key columns (‘Player’, ‘Pos’) for
later use.
4) Feature Selection and Engineering:
Key performance indicators like goals, assists, completed passes, attempted passes, tackles, and
recoveries are selected. A binary ‘Performance’ target variable is created based on whether
players’ goals surpass the mean.
5) Data Transformation:
Converts categorical data into dummy variables to meet the logistic regression model’s input
requirements.
6) Model Training Setup:
Divides the dataset into training (70%) and testing (30%) sets. Ensures the presence of at least
two classes in the training set to facilitate effective logistic regression training.
7) Logistic Regression Model:
Trains the logistic regression model on the training data, evaluates it using metrics like accuracy,
precision, recall, and visualizes performance distinctions with a confusion matrix.
8) Prediction and Selection of Top Performers:
Uses the model to estimate the probability of each player being a top performer, reintegrates
these probabilities into the main DataFrame, sorts players by predicted performance, and selects
the top 50 for display based on these probabilities.
Results
The results from the logistic regression model, as depicted in the classification report and
confusion matrix, offers a detailed performance evaluation for predicting top football players.
The model achieves an impressive overall accuracy of 94%, with precision scores of 0.92 for
non-top performers and 1.00 for top performers, which is indicative that it is highly reliable in
identifying true top performers without any false positives. The recall scores show a perfect 1.00
for non-top performers, meaning all actual non-top performers were correctly identified.
However, the recall for top performers is somewhat lower at 0.79, suggesting that the model
misses about 21% of the actual top performers, which are false negatives.
Analyzing the confusion matrix provides further insight: out of 876 predictions, 623 were true
negatives (correctly identified non-top performers), and 199 were true positives (correctly
identified top performers), but there were 54 false negatives where top performers were not
recognized. This aspect of the model’s performance points to a conservative prediction
strategy—prioritizing accuracy in positively identifying top performers (as evidenced by no false
positives), yet at the cost of missing some true top performers. This conservative approach may
result in underestimating player potential, which could be critical in real-world scouting or team
formation scenarios.
The imbalance between high precision and lower recall for top performers suggests potential
areas for model improvement. Enhancing feature selection or incorporating more granular data
might capture subtle nuances better, potentially increasing sensitivity without sacrificing the
precision that ensures non-top performers are not mistakenly classified as top talent. Adjusting
the decision threshold or experimenting with more complex or different machine learning
algorithms could also help balance the precision-recall trade-off, aiming for a more balanced
approach that doesn’t overly penalize false negatives at the expense of missing out on true top
performers.
Conclusion
This project implemented logistic regression—a model studied in our class—to select the best XI
of players from the 2021-2022 season based on comprehensive and all-round performance
metrics like predicting top football players based on their performance statistics (goals, assists,
passes completed, passes attempted, number of players tackled, and number of loose balls
recovered). This method's high accuracy and precision can make it a valuable tool for sports
analysts, team scouts, and club back offices when seeking to enhance their decision-making
processes and recruitment policies with robust, data-driven strategies. While the model excels in
identifying true top performers without false positives, it does show limitations in its
conservative nature, particularly in under-identifying true top talents. Moving forward, the
project could be expanded by incorporating advanced metrics specifically for defenders, such as
tackles, clearances, and goal-scoring opportunities stopped, to refine predictions in this player
category. The methodology can be adapted to more accurately scout goalkeepers by utilizing key
goalkeeper-specific statistics like saves, goals conceded, and clean sheets. While logistic
regression provides a strong foundation, exploring more complex models could further optimize
our ability to capture and predict nuanced player attributes across all positions and increase the
model’s utility in sports analytics. Note: I used LLMs to help brainstorm ideas related to my
topic and generate ideas for applying logistic regression to make a useful classification tool.
