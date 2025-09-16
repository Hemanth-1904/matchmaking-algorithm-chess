# PlaySimple Games – Assignment Submission


## 📌 Problem Statement
** Matchmaking for the users**

Many Player vs Player (PvP) games require pairing players fairly. As a newly hired Data Scientist, the goal is to design a matchmaking algorithm that goes beyond random pairing and ensures balanced, engaging matches.  

---

## 🎯 Proposed Solution
The solution focuses on **Chess** as the test game because it is skill-based, structured, and relies heavily on balanced matchmaking.

### Key Assumptions
- Skill is normalized using **Elo rating**.  
- Players can choose between **ranked** and **unranked** matchmaking.  
- **Geographical proximity** is important to minimize latency.  
- Player performance can be profiled using their **last 10 games**.  

### Approach
1. **Skill Normalization** – Use Elo rating as the baseline.  
2. **Performance Profiling** – Track win rate & recent form using last 10 games.  
3. **Latency-Aware Matching** – Factor in geolocation to reduce lag.  
4. **Random Matchmaking via KNN** – Represent players in a 3D space:  
   - Elo rating (last 10 games average)  
   - Win rate (last 10 games)  
   - Geographical position  
5. **KNN Algorithm** – Find nearest neighbours in this feature space and select opponents accordingly.  

---

## 📂 Datasets
- [Custom dataset (generated)](https://tinyurl.com/ymkxb34m)  
- [Kaggle – Chess Games](https://www.kaggle.com/datasets/arevel/chess-games)  
- [Kaggle – Chess Dataset](https://www.kaggle.com/datasets/datasnaek/chess)  
- [Stockfish Chess Data](https://stockfishchess.org/)  

If extra data is required, **in-game surveys** can be used to gather preferences with minimal disruption.  

---

## ⚙️ Algorithm Details
1. Collect player features (Elo, win rate, geolocation).  
2. Map each player as a point in 3D space.  
3. Compute **Euclidean distance** between players.  
4. Use **KNN** to find the most similar opponents.  
5. Confirm match with additional checks (e.g., latency, activity).  
6. Initiate the match or fall back to broader rules if no match found.  

---

## 📊 Validation
The success of the new algorithm is evaluated through:

- **A/B Testing** – Compare against random matchmaking.  
- **Player Metrics** – Elo difference, accuracy, retention, session duration.  
- **Business Metrics** – Monetization, churn, queue wait time.  
- **Continuous Monitoring** – Dashboards, anomaly detection, player feedback.  

---

## ✅ Outcome
- Fair and balanced matches.  
- Reduced churn and early exits.  
- Better player satisfaction and engagement.  
- Improved monetization without harming player experience.  

