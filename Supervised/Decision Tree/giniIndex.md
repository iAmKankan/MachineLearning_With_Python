
### 🔲 $\large{\color{Purple}\underline{\textrm{Gini Impurity:}}}$ 

<ins><b>Gini impurity is the probability of incorrectly classifying random data point in the dataset if it were labeled based on the class distribution of the dataset</b></ins>. 

Similar to **entropy**, if set, S, is pure—i.e. belonging to one class) then, its impurity is zero. This is denoted by the following formula: 

$$\Large{\color{Purple}\textrm{Gini Impurity} = 1 -\sum_i (p_i)^2}$$


<p align="center">
  <img src="https://github.com/iAmKankan/MachineLearning_With_Python/assets/12748752/0f55d05f-fd02-4774-bd36-130065404532" width=70%/>
  <br>
  <ins><b><i> school-boy data</i></b></ins>
</p>


* Compute the Gini Index for the overall collection of training examples.
* There are four possible output variables- movie, tennis, stay-in and shopping.
* The data has 6 instances of movie, 2 instances of tennis, 1 instance of Stay In and 1 of shopping.
* Gini(S)=1-[ (6/10) ^ 2 + (2/10) ^ 2 + (1/10) ^ 2 + (1/10) ^ 2 ]=0.58

* Computation of Gini Index for Money Attribute It has two possible values of Rich (7 examples) and Poor (3 examples).
* For Money = Poor, there are 3 examples with "Cinema".
* Gini (S) = 1 - [(3/3) ^ 2] = 0
*  For Money = Rich, there are 2 examples with "Tennis", 3 examples with "Cinema" and 1 example with "Stay in", "Shopping" each
*  Gini (S) = 1 - [(2/7) ^ 2 + (3/7) ^ 2 + (1/7) ^ 2 + (1/7) ^ 2] = 0.694
*  Weighted Average(Money) =0*( 3 10 )+0.69 dot 4(7/10) = 0.486

 Computation of Gini Index for Parents Attribute
* It has two possible values of Yes (5 examples) and No (5 examples).
* For Parents = Yes, there are 5 examples, all with "Cinema".
* Gini (S) = 1 - [(5/5) ^ 2] = 0
* For Parents = No, there are 2 examples with "Tennis", 1 example with "Stay in", "Shopping" and "Cinema" each
* Gini (S) = 1 - [(2/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2 + (1/5) ^ 2] = 0.72
* Weighted Average(Parents) =0*( 5 10 )+[ 0.72(5/10) = 0.36

Computation of Gini Index for Weather Attribute
* It has three possible values of Sunny (3 examples), Rainy (3 examples) and Windy (4 examples).
* For Weather = Sunny, there are 2 examples with "Cinema" and 1 with "Tennis".
* Gini(Sunny)= 1 - [(2/3) ^ 2 + (1/3) ^ 2] = 0.44
* For Weather = Rainy, there are 2 examples with "Cinema" and 1 example with "Stay in"
* Gini(Rainy)= 1 - [(2/3) ^ 2 + (1/3) ^ 2] = 0.44
* For Weather = Windy, there are 3 examples with "Cinema" and 1 example with "Shopping"
* Gini(Windy)= 1 - [(3/4) ^ 2 + (1/4) ^ 2] = 0.375
* Weighted Average(Weather) = 0.444(3/10) + 0.444(3/10) + 0.375(4/10) = 0.416

- For Weather - Gini Index: 0.416
- For Parents - Gini Index: 0.36
- For Money - Gini Index: 0.486
