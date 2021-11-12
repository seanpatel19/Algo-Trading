# Algo-Trading

## Evaluation Report

During our evaluation of the current model the following imputs were used.

The first time frame looked at was 3 months.

![original time sample](https://github.com/seanpatel19/Challenge-14/blob/04817cff05989aea7629b9be2d8c92ca377a00ef/Images/time%20sample%20original.png)

The first set of moving averages looked at where 4 days and 100 days 
![original SMAs](https://github.com/seanpatel19/Challenge-14/blob/04817cff05989aea7629b9be2d8c92ca377a00ef/Images/SMA%20original.png)

The original classification report shows that the model should be useful with a weighted average of 77 and very high recall and precision in longing and shorting respectively

![original classification report](https://github.com/seanpatel19/Challenge-14/blob/04817cff05989aea7629b9be2d8c92ca377a00ef/Images/original%20classification%20report%20.png)

While the numbers seem good the performance of this strategy is not desirable as it underperforms 

![original returns graph](https://github.com/seanpatel19/Challenge-14/blob/ed60de7fdd7d8a0fb77104fb66908e4b54ba3b89/Images/plotted%20returns.png)

I set out to tune the model to find some better performance.

One of the things I did was to increase the time horizon that was used for testing, from 3 months to 6 months.

This was coupled with adjusting the moving averages used as trading signals. We decided on using a shorter SMA horizon with 14 days being our "Fast" SMA and 30 being our "Slow" SMA 

These changes together produced this classification report which on the surface looks worse than the original classification report with a whole 20 points lower on weighted average and much worse recall and precision.

![new classification report](https://github.com/seanpatel19/Challenge-14/blob/ed60de7fdd7d8a0fb77104fb66908e4b54ba3b89/Images/New%20classifciation%20report.png)

Despite this the returns were much better and outperformed. As this new model outperformed on nearly all times frames, I believe that changing the moving averages had a greater effect than increasing the time period that we looked at originally  

![new plotted returns](https://github.com/seanpatel19/Challenge-14/blob/ed60de7fdd7d8a0fb77104fb66908e4b54ba3b89/Images/new%20plotted%20returns.png)

Another model was used on the original time frame and original moving averages to see if more performance could be gained. I used Logisitic Regression to see if that created any improvements. 

While the classification report showed a lower weighted average than the previous model with time frame changes, we have seen that better weighted average does not guarantee better trading results 

![logisitic regression classfication report](https://github.com/seanpatel19/Challenge-14/blob/ed60de7fdd7d8a0fb77104fb66908e4b54ba3b89/Images/lr%20classifcation%20report.png)

But this model is no good. It lags actual returns to such an extent, I am of the opinion that logistic regression is not suitable for a trading algorithms

![lr returns plotted ](https://github.com/seanpatel19/Challenge-14/blob/ed60de7fdd7d8a0fb77104fb66908e4b54ba3b89/Images/new%20model%20graph.png)


### Conclusions 

I would appear that Support Vector Machine (SVM) learning is suitable for putting together a trading strategy. 

The updated model appears to work well enough, that it should be fitted to other assets to see what sort of performance gains could be found. 

It would also be useful to look at the returns of the model over a very long time horizon to see how well it does. 

During a 6 month timeframe the new 14 and 30 SMA SVM is a winning trading algo.
