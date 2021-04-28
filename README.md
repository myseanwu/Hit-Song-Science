# Hit Song Science: Modeling Weekly Billboard 100 Chart with Twitter Data

<table border="0">
 <tr>
    <td><b style="font-size:30px">Yin Kwong (John) Lee</b></td>
    <td><b style="font-size:30px">Hsin-Yuan (Sean) Wu</b></td>
    <td><b style="font-size:30px">Tz-Huei (Melody) Chang</b></td>
 </tr>
 <tr>
    <td>LSA, Department of Statistics
        University of Michigan, Ann Arbor
        lykjohn@umich.edu
   </td>
    <td>UMSI, School of Information
        University of Michigan, Ann Arbor
        wusean@umich.edu
   </td>
   <td>UMSI, School of Information
        University of Michigan, Ann Arbor
        tzhueic@umich.edu 
   </td>
   
 </tr>
</table>

## SUMMARY
In this project, we aim to explore whether tweet features from Twitter data can help predict rankings of the top 100 songs on Billboard. Our work is an extension of the previous work by Tsiara and Tjortjis [1]. In order to better represent the music charts prediction problem in reality, we also incorporated songs that were popular on Spotify. After querying 3-month worth of data, we gathered 16 features from the Twitter Decahose Data related to popularity measures (e.g., counts of song-related tweets), network patterns (e.g., average number of friends), and textual components (e.g., average sentiment score). Combining this with the weekly song rankings from the Billboard and Spotify charts, we compiled a complete list of predictors for the songs’ future rankings. Considering the dimension of the training data, this is a multi-class classification problem. To represent song popularity, we grouped rankings into 6 classes, with class 0 indicating songs that were popular on the Spotify chart but not on the Billboard chart.

Following some data exploration, we fit an array of training algorithms, where the performance of each was evaluated with MAE, confusion matrix (macro F1 score), skewness, and kurtosis. We first fit and trained two baseline models using Naive Bayes and Support Vector Machine (SVC). The latter performs better among the two with a MAE score of 0.742 and a F1 score of 0.498. We then built a variant of classification designs with 11 other models, including Logistic Regression, Random Forest, Quadratic Discriminant Analysis (QDA) Classification, Multilayer Perceptron (MLP), Gradient Boosting, and many more. To optimize these models, we further applied normalization, feature selection, feature expansion, and hyperparameter tuning. It turns out that the Random Forest model with normalization and tree-based feature selection yielded the best results, having a MAE score of 0.387 and a F1 score of 0.719.

In general, we were impressed with the fit and evaluation scores for the ensemble methods. The results showed that discussions and activities on social media could imply song popularity, that predicting chart rankings with features extracted from social media is possible. Among all the features fed into the models, the popularity measure- counts of relevant tweets- is of the most important. Therefore, we believed that if we were able to incorporate other popularity measures such as the counts of retweets and likes, it would be possible for us to further enhance the model performance in the future. Some of the challenges that we faced include the real-time streaming nature of Decahose, which prevented us from obtaining accurate data on some important popularity measures, as well as the limited resources on Cavium, which led to longer data processing and feature extraction runtimes.






