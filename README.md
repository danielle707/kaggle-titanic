# kaggle-titanic
RapidMiner (Beginner SQL) guide for Kaggle titanic data competition

#Steps:Several Problems we need to solve with the data, and we start by cleaning the data.
/1
In the following I will explain some problems incurred in the data and my solution using Excel and RapidMiner

Issue 1: Duplicate entries are found in the dataset. 
Mitigation: Using “Remove Duplicates” to remove duplicate entries. 

Issue 2: Many values of Cabin attribute are missing
Mitigation: Since the attribute has little correlation with the result of survival and the Cabin attribute could be roughly represented by Fare and Pclass, we can delete the attribute to clean up the data. 
 
Issue 3: Some values under “age” attribute is missing.  
Mitigation: Using “Replace missing values” to replace these values with average age. 
 
Issue 4: Choosing features as appropriate regressors.
I choose ‘Age’, ‘Fare’, ‘Pclass’, ‘Sex’ and ‘Survived’ as five features. In the real situation, with limited lifeboat, people chose to save seats for woman and young people. That’s the reason I select ‘Age’ and ‘Sex’ attributes. Those passengers who are near  lifeboats had a higher chance to escape, and first class cabins tended to have better facilities to reach a lifeboat. Though cabin attributes are missing, ‘Fare’ and ‘Pclass’ attributes can roughly represent it. Based on these assumptions, I took ‘Fare’, ‘Pclass’ into account. Besides, the ’Survived’ is the prime feature to our training model. Therefore, I include ‘Age’, ‘Fare’, ‘Pclass’, ‘Sex’ and ‘Survived’ as selected attributes. 
I didn’t choose ‘Embarked’ since where passengers started from doesn’t matter. And the ‘Ticket’ attribute is only a series of numbers which explain little information, thus I also exclude the feature ‘Ticket’.

/2
#Results

As it shown in the result panel, the precision of the optimized model is 79.53% +/- 5.17%, and the recall rate is 73.95% +/- 9.15% according to the confusion matrix. 
These two model evaluation indices are pretty high, so we are safe to conclude the recommended combination in RapidMiner of ‘sex’, ‘fare’, ‘age’ make the best model.
Under this combination to modify my model, and the score of the prediction is tested to be 0.77033 on Kaggle.com. 
