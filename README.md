# Supervised-Learning-Revenue-Prediction
DISCLAIMER: I've removed/alterred all information proprietary to my employer (e.g., key statements, variable selection, variable names, and algorithim coefficients). The sole purpose of this repo is to serve as a high-level illustration of the approach I took. 

Necessary Context:
The coefficients from the winning model (defined by confusion matrix results below) are used in the professional services predictor algorithm (not shown in this file), 
where the resultant log odds ratio is converted into a win probability and then multiplied by each opportunity's professional services value to arrive at an expected PS value for each opportunity. This exact same algorithm can be used to predict bookings as well.

Efficacy:
Before implementing this model, professional services budget estimates were, on average, 62% off from the actual final sales value for the quarter. Even software sales forecasts (which are revised on a weekly basis) had a 46% final sales variance. But after implementing this model, the forecast variance dropped to just 25%.

The following confusion matrix error rates may seem high, but it's important to note that predicting enterprise sales outcomes isn't comparable to calculating something deterministic like mechanical failure. No matter how much data you collect, enterprise buying decisions are highly variable and impossible to predict at the individual level. The accuracy of the forecast is determined by the algorithim's expected value calculation for the quarter, so even though the positive error rate is 46.2%, the expected value of the false negatives partially offsets the value of the false positives, resulting in a 21 percentage point reduction in forecast variance.  

Model Comparison Results
	- Model A
		○ Version 1b (the winning model)
			§ Pos Error: 46.2% 
	- Model B
		○ Version 1
			§ Pos Error: 54.6%
		○ Version 2b
			§ Pos Error: 53%
	- Model C
		○ Version 1
			§ Pos Error: 66.6%
		○ Version 2
			§ Pos Error: 66%


The final model I stuck with (Model A) was a variant of the "forty.balanced.reg" model that dropped many of the interaction terms (which turned out to not be all that differentiated from the base inputs), along with other dummy variables that lacked predictive power. The coefficients from this final model were then plugged into the forecast algorithim as discussed in the introductary paragraph.
