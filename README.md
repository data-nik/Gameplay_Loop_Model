# Gameplay_Loop_Model



Dynamic In-Game Difficulty Adjustment

This project demonstrates a system for dynamically adjusting in-game difficulty based on player performance, creating a more engaging and adaptive gaming experience. The core idea is to train a machine learning model to predict an optimal difficulty level given a player's skill and in-game metrics, then continuously adjust the game's difficulty during a simulated gameplay loop. 
This is something I have been working on to improve my skills and to overall understand more of how things work. Thank you for checking it out!


Dynamic In-Game Difficulty Adjustment

This project demonstrates a system for dynamically adjusting in-game difficulty based on player performance, creating a more engaging and adaptive gaming experience. The core idea is to train a machine learning model to predict an optimal difficulty level given a player's skill and in-game metrics, then continuously adjust the game's difficulty during a simulated gameplay loop.


Project Breakdown

1. Game Simulation: A simplified game environment is simulated to generate realistic player performance data. This simulation takes into account player_skill and difficulty to produce accuracy, completion_time, and deaths for each game session.

2. Data Generation: A dataset of 1000 simulated game sessions is created. Each entry includes the player_skill, difficulty the player encountered, and their resulting accuracy, completion_time, and deaths.

3. Performance Score Preprocessing: A composite performance_score feature is engineered from the raw game metrics. This score quantifies overall player performance, with higher values indicating better play (e.g., high accuracy, low completion time, few deaths).

4. Model Training: A Random Forest Regressor model is trained to predict the difficulty level based on the player_skill and the calculated performance_score, along with the individual metrics (accuracy, completion_time, deaths). This allows the model to learn the relationship between player performance and appropriate difficulty. The model's effectiveness is evaluated using Mean Squared Error (MSE).

5. Difficulty Adjustment Logic: A function adjust_difficulty uses the trained model to recommend a new difficulty. To prevent sudden, jarring changes for the player, a smoothing factor is applied, blending the predicted difficulty with the current difficulty. The adjusted difficulty is also capped within a valid range (0 to 1).

6. Gameplay Loop Simulation: The project culminates in a simulated gameplay loop. In each round, the game is played with the current difficulty, performance metrics are recorded, and then the adjust_difficulty function is called to dynamically update the difficulty for the next round. This simulates how an adaptive difficulty system would work in a real game. The player's skill is also updated based on their performance to simulate learning and improvement over time.


This project was my attempt to understand, with a clear example through practice, of how machine learning can be integrated into game development to create more personalized and responsive gameplay.
