# project-template
Project Template
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
