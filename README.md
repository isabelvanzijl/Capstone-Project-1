# Studying and Predicting Doping Related Incidents in New York State’s Horse Racing Industry

### Final Report:
https://docs.google.com/document/d/13T1fpkFmUUIyhQPvhc5sfjtQHuFFy2Yyp_3YAY52UPI/edit?usp=sharing

### Slide Deck:
https://docs.google.com/presentation/d/1x3C1t3bUPbQUUqrkfYR_PQ5-TRPVW_duZ0d15aKY_rk/edit?usp=sharing

### Final Code:
ipython notebook in this repo: Final_Analysis_Code.ipynb


# Overview

## The Problem

Horse racing is a sport that has been practiced since ancient times and today is a multi-billion dollar industry. It is a dangerous sport, both for the horse and the jockey, and has only grown to be more dangerous with the increased presence of doping abuse within the practice. Laws and regulations have been introduced to address safety and fairness concerns within the sport, but have they made a difference? Many trainers have been identified and punished over the years for doping their horses, but the problem seems to persist in the sport. Is there a way for us to predict which trainers are likely drugging their horses based on the histories of trainers that have already been suspended and/or fined for equine doping? If we can identify such trainers, what further legislation and regulations could be introduced to continue to build integrity within the sport?

## Limitations

Overall, the two machine learning algorithms I implemented were inconclusive. Neither model was able to correctly identify whether an incident was doping related or not. The two biggest limitations in creating accurate machine learning models for this project were the lack of official verified data and the lack of descriptive variables. 

The doping trainers data set that I compiled is comprehensive but there most likely are other trainers that haven’t been caught yet and therefore were not included in my data set. We had to make a large assumption for this project that an incident was doping related only if the trainer for the incident had a history of equine doping. The significance of the variables we studied couldn’t be properly measured because of this assumption and the overall lack of background information on all the trainers. If there was an official list of doping trainers that included information such as where they trained, what owners they work for, what other trainers they’re associated with, etc., then maybe our results would be more conclusive. Unfortunately, the large assumption we made regarding trainers with a history of doping combined with the lack of descriptive information made it difficult to identify which incidents occurred due to drugging. Under our assumption, we also don’t account for whether an incident happened despite an incident being marked as doping related. For example, if the track was muddy and a horse broke its leg because it got stuck, we would be counting this as a doping related incident if it occurred under a trainer with a history of doping. The incident didn’t necessarily occur because the horse was drugged though, so we end up with a type of false positive result. These types of errors likely exist throughout the data set, so this is kept in mind when analyzing the results.

What also would have helped is if there were more descriptive variables in the original Equine Death and Breakdown data set, such as more information on the owners and horses. Even before implementing the logistic regression and random forest, I knew that the independent variables being used wouldn’t necessarily give us desirable results because predictors such as Track and Weather Condition aren’t variables you would assume would be significant in this analysis. If I had been provided with a lot of variables, I would have thought more about excluded certain ones. Since there wasn’t that much descriptive information available, I felt inclined to include all the variables that I could. I think that if there was also some quantitative data included (maybe length of the race, age of the horse, number of races done per day, etc.), it would have also helped the analysis. Essentially all of our data was qualitative and had to be transformed into binary variables for the analysis. I think that including some quantitative data would have at least improved the p-values and the accuracy of the coefficients for the logistic regression.

## Conclusions

Although our machine learning methods were fairly inconclusive and this project faced many limitations, there were still insights to be gained from the analysis.

We saw that yearly equine death and breakdown rates have been decreasing, but there is always room for improvement. The majority of our records are racing related, and fortunately those yearly totals have decreased over the years. We saw that adding horses to the Steward’s/vet’s list most likely helped save some horses from impending injuries and death, but the rate of an incident occurring (especially death) is still quite high in 2017 compared to other incident types.

In our exploratory data analysis, we found that the yearly incident rate under doping trainers has been decreasing, but we didn’t know if this decrease was statistically significant. We compared the 2017 incident rates to those of the other years since THADA’s ​Thoroughbred Horseracing Integrity Act came into effect in 2017. Though we didn't find the decrease of the 2017 incident rate under doping trainers compared to other years to be significant in our t-test, we still identified statistical significance in our two other tests. The significant decrease in the proportion of incidents under doping trainers in 2017 compared to the average proportion of incidents under doping trainers for the previous eight years suggests that anti-doping legislation and regulations are likely influencing trainers’ decisions to not drug their race horses. 

For the machine learning aspect of this project, I implemented two supervised learning algorithms. In both our logistic regression models and random forest models, we were unable to accurately predict whether an incident occurred under a doping trainer. Overall, the independent variables we studied were not good predictors of our dependent variable, yielding low R2 values, precision, recall, and accuracy scores. If we had been provided with more descriptive variables and official verified data, we likely would have gotten better results. Based on our models though, we saw that two variables of higher importance to our analysis were Division and Racing Type. If we were to redo this project with a better data set, I would still include these variables in my model.

Though the number incidents under doping trainers has decreased over the years, it doesn't mean that the practice of doping is coming to an end. The mindset of cheating the system and winning more races (and money) will always be present. New drugs are always being developed and drug testing is only administered at races, so there are definitely some gaps in the above analysis for non-racing and training incidents. With the development of more robust anti-doping tests and stringent rules, hopefully the number of deaths and breakdowns per year will continue to decrease and the racetrack can return to being a level playing field for all participants.
