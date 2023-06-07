# Supervised-Learning-Revenue-Prediction
The coefficients from the winning model (defined by error matrix results below) are used in the professional services predictor algorithm (not shown in this file), 
where the resultant log odds ratio is converted into a win probability and then multiplied by each opportunity's professional services value to arrive at an expected PS value for each opportunity. 
This exact same algorithm can be used to predict bookings as well.

For cleanliness, I didn't include all of the different model iterations, but here are their error matrix results compared. 

Model Comparison Results
	- Forty.balanced.reg
		○ Version 1b (the winning model)
			§ Pos Error: 46.2% 
			§ Predicted Win: 28.1%
			§ Actual vs Predicted Win: -11.9%
				□ Relative to win rate: 29.75%
	- Thirty.balanced.reg
		○ Version 1
			§ Pos Error: 54.6%
			§ Predicted Win: 19.8%
			§ Actual vs Predicted Win: -10.2%
				□ Relative to win rate: 34%
		○ Version 2b
			§ Pos Error: 53%
			§ Predicted Win: 20.3%
			§ Actual vs Predicted Win: -9.8%
				□ Relative to win rate: 32.67%
	- Twent.balanced.reg
		○ Version 1
			§ Pos Error: 66.6%
			§ Predicted Win: 10.8%
			§ Actual vs Predicted Win: -9.2%
				□ Relative to win rate: 46%
		○ Version 2
			§ Pos Error: 66%
			§ Predicted Win: 10.8%
			§ Actual vs Predicted Win: -9.2%
				□ Relative to win rate: 46%


The final model I stuck with (forty.balanced.reg version 1b) was a variant of the "forty.balanced.reg" model that dropped all of the interaction terms (which turned out to not be all that differentiated from the base inputs), along with other dummy variables that lacked predictive power. Here are the final values with their coefficients from the winning model. 

	- Forty.balanced.reg (Version 1b)
		○ Coefficients
			§ Intercept: -0.63
			§ Lifespan.30: 2.02
			§ Lifespan.60: 1.65
			§ New: -0.19
			§ Upgrade: -1.50
			§ Upsell: 0.52
			§ Migration: -1.25
			§ Decommission: -5.68
			§ Recontract: -0.77
			§ Agency.Enterprise: 0.20
			§ Agency.Field: -0.39
			§ CMGA: -0.07
			§ DCM: 0.15
			§ Commit: 1.03
			§ Pipeline: -0.36
			§ 5th-8th Week: -0.20
			§ 9th-10th Week: -0.35
			§ 11th-12th Week: -0.47
			§ 13th Week: -0.56
