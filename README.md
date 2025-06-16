# Markov-Chain Based Strategic Betting Simulator

This project reimagines **Snakes and Ladders** as a **stochastic betting environment**, where each square represents a player's balance (💰$0–$8) and transitions are based on **bet outcomes**, not dice rolls. We model this as a **Discrete-Time Markov Chain** and explore betting strategies that aim to maximise win probability.

> Can you improve your odds of winning by betting strategically?  
> Or are players statistically destined to lose?

We answer this through a mix of **Markov Chains**, **Monte Carlo Simulation**, and **Simulated Annealing**.

---

## 🧠 Key Questions

1. **Do players win or lose on average?**  
2. **How quickly do games end (win/lose)?**  
3. **Does your starting balance influence the outcome?**  
4. **Can strategy improve your odds?**

---

## 📊 Model Overview

- **States**: Balances from $0 to $8  
- **Absorbing states**: `$0` (Bankrupt 💀) and `$8` (Win 🏆)  
- **Actions**: Players place bets; each has win/loss probabilities and affects balance  
- **Strategies**: Map each balance to a preferred bet type (A, B, C, D)

Each bet has different risk/reward transitions → forming a stochastic transition matrix for each.

---

## 🔧 Techniques Used

| Technique                 | Purpose                                                                 |
|--------------------------|-------------------------------------------------------------------------|
| **Markov Chains**        | Analytical probabilities of Win/Lose & expected steps to absorption     |
| **Monte Carlo Simulation** | Empirical spread of outcomes across 1,000+ games                        |
| **Heuristics (Simulated Annealing)** | Search for betting strategies that improve win outcomes       |

---

## Key Results

### 🔁 Without Strategy (Random Betting)

- Players lose more than win — even from $7, win rate ≈ **61%**
- Starting from $1? Win rate drops below **10%**
- Games usually end within **2–3 steps** (lower balances) or **5–8 steps** (higher balances)

### With Strategy (Simulated Annealing)

- Win rates nearly **double** with optimised strategies  
- From $4: win rate improved from ~45% → **96%**  
- From $6–$7: win rate > **90%**  
- Lower balances still lose often due to proximity to $0
