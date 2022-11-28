# project-template
Project Template
# Task 1&2 
# Constraints:
1. Short_Name, Long_Name, Player_Position, Club_Name, League_Name, Club_Position is "NotNull" String 
2. CHECK("nationality_id " < 200)
3. CHECK("preferred_id" = "Left" or "Right")
4. CHECK("weak_foot" > 0 AND "weak_foot" < 6)
5. CHECK("skill_moves" > 0 AND "skill_moves" < 6)
6. CHECK("international_reputation" > 0 AND "international_reputation" < 6)
7. CHECK(" overall" < 100)
8. CHECK(" potential" < 100)

## Players' info:
### The following columns are basic information about the players
sofifa_id,short_name,long_name,player_positions,value_eur,wage_eur,age,dob,height_cm,weight_kg,club_team_id,club_name,league_name,league_level,club_position,club_jersey_number,club_loaned_from,club_joined,club_contract_valid_until,nationality_id,nationality_name,nation_team_id,nation_position,nation_jersey_number,preferred_foot,weak_foot,skill_moves,international_reputation,work_rate,body_type,real_face,release_clause_eur,player_tags,player_traits,player_face_url,club_logo_url,club_flag_url,nation_logo_url,nation_flag_url,players_url

## Players' Attribute:
### The following columns are descriptive attribute：
#### 1.The following columns give the attribute of players in different aspects:
pace,shooting,passing,dribbling,defending,physic,attacking_crossing,attacking_finishing,attacking_heading_accuracy,attacking_short_passing,attacking_volleys,skill_dribbling,skill_curve,skill_fk_accuracy,skill_long_passing,skill_ball_control,movement_acceleration,movement_sprint_speed,movement_agility,movement_reactions,movement_balance,power_shot_power,power_jumping,power_stamina,power_strength,power_long_shots,mentality_aggression,mentality_interceptions,mentality_positioning,mentality_vision,mentality_penalties,mentality_composure,defending_marking_awareness,defending_standing_tackle,defending_sliding_tackle,goalkeeping_diving,goalkeeping_handling,goalkeeping_kicking, overall, potential,goalkeeping_positioning,goalkeeping_reflexes,goalkeeping_speed
#### 2.The following columns give the attribute of players as different roles:
ls,st,rs,lw,lf,cf,rf,rw,lam,cam,ram,lm,lcm,cm,rcm,rm,lwb,ldm,cdm,rdm,rwb,lb,lcb,cb,rcb,rb,gk

# Task 3
## Pspark
### Why we choose model?
In pyspark, we chose RandomForestRegressor and LinearRegression models to make the prediction.
Linear regression is the most wide-used regression algorithm. It makes the estimation procedure simple, and its interpretation of weights can be easily understood.
The random forest has the ability to handle large datasets efficiently, and it produces good predictions that can be understood easily.
### What parameters and how we tune them?
1. In random forests, we choose to change numTrees and maxDepth. 
a) Among the parameters of the decision tree, maxDepth works on the macrplevel by greatly reducing the growth of the decision tree. The drawback of the maxdepth is that the model inclines to overfit the training set when the value of the maxDepth is too large. Therefore, its generalization will become weak, and it has low prediction accuracy for those points that are not existing in the training set. In this case, to balance the accuracy and the generalization, we should carefully choose the value of the maxDepth. We found that the accuracy of the training set would increase when we increased the value of the maxDepth. However, the accuracy of the test dataset would decrease if the value of the maxDepth is too large, which means that the model starts to overfit. 
b) The properties of the numTrees are similar to the maxDepth.
2. In linear regression, we chose to change the value of regParam and maxIter.
a) Depending on the complexity of the model, regParam adds a penalty to the cost. When the penalty is too large, the accuracy of the model decreases.
b) The meaning of maxIter is the maximum number of iterations to perform before giving up. As we expected, the more we run the loop, the more parameters get closer to the optimum. However, more iterations also mean higher computational costs, especially for large datasets. In this way, a proper maxIter that can balance the performance of the model and the computational cost is needed. In this case, we get the maxIter when the accuracy converges, i.e. the accuracy will not increase or increase slightly as we increase the maxIter.

## Tensorflow
In Tensorflow, we chose Neural Networks and Linear Regression to train the model. 
### What parameters and how we tune them?
1. During the training process of the Neural Network, the number of layers and the number of neurons in each layer are finetuned to reach a better performance. 
a) Among all the hyperparameters of NN, the number of layers greatly enhances the model's capability of prediction. However, there is also a greater chance for a deep neural network with more layers to underfit without enough data. Generally, 3-5 layers are enough for regular-size datasets.
b) Also, the number of neurons in each layer is as significant as the num of layers. It can also, to some extent, decide the model's capability of the prediction(not as efficient as the number of layers). The finetuning strategy of num of neurons is similar to the num of layers. 
To this end, we tune the two hyperparameters simultaneously using param grid and choose the model with the highest accuracy.

2. During the training process of Linear Regression, we tuned the learning rate, which is different from the hyperparameters we tuned in pySpark, to get the model with better prediction accuracy. It can be easily found that when the learning rate is too large(i.e., equal to 0.001), the accuracy of the model oscillates, which means the trainable parameters skips the optimum. Also, when we give a lower learning rate(i.e., equal to 0.00001 or 0.000001), even if we run ten times more iterations, it gives a similar performance to 15 iterations as the lr=0.0001. To balance the accuracy and the computational cost, the learning rate was chosen as 0.0001.
