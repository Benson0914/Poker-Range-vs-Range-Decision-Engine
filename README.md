# Bayesian Poker Range Decision Engine
# **🧠 Overview**

This project is a simplified poker decision engine built to explore probabilistic decision-making under incomplete information.

The framework combines:

- Monte Carlo equity simulation
- Bayesian opponent range updating
- Expected value (EV) calculations
- Kelly Criterion capital allocation
- Range-weighted sampling under uncertainty

Rather than treating an opponent’s hand range as static, the model dynamically adjusts posterior hand probabilities after observing betting actions.

The project was built primarily as a quantitative decision-making and simulation exercise inspired by concepts from trading, risk management, and probabilistic inference.

# **⚙️ Key Components**

## **1. Range Parsing**

The engine converts poker range notation such as:


```ruby
"TT+,AJs+,KQs,QJs"
```

into explicit weighted hand combinations.

This allows simulation over full opponent distributions rather than single fixed hands.

## **2. Bayesian Range Updating**

After observing an opponent action (e.g. aggressive flop continuation bet), the model updates hand probabilities using Bayesian inference:

### $P(Hand | Action) \propto P(Action | Hand) \times P(Hand)$

Stronger hands receive higher posterior weights while weaker hands are discounted.

This creates a dynamic probabilistic opponent profile.

## **3. Monte Carlo Equity Simulation**

The engine performs weighted Monte Carlo simulations to estimate:

- Hero equity
- expected value
- break-even thresholds

Posterior-weighted opponent ranges are sampled repeatedly across randomized future board runouts.

## **4. Decision Framework**

The framework evaluates:

- call EV
- break-even equity
- bankroll-adjusted Kelly allocation

to determine whether a decision has positive expected value.

## **Example Workflow**

1. Initialize opponent prior range
2. Observe betting action
3. Apply Bayesian posterior update
4. Run weighted Monte Carlo simulation
5. Compute EV and Kelly sizing
6. Output decision recommendation

## **Sample Output**
This project reflects key aspects of trading:

- Expected value-based decision-making
- Managing uncertainty and incomplete information
- Evaluating edge and risk trade-offs
```
Hero Equity: 61.42%
Break-Even Equity: 25.00%
Expected Value: +72.13

Decision: CALL

Quarter Kelly Allocation:
6.12% of bankroll
```
![alt text](range_matrix.png 'range_matrix')

# **Project Motivation**

This project was inspired by the similarities between poker and quantitative trading:

- decision-making under uncertainty
- probabilistic reasoning
- incomplete information
- dynamic belief updating
- risk-adjusted capital allocation

The goal was not to build a production poker solver, but rather to explore how Bayesian inference and simulation methods can be applied to sequential decision systems.

# **Limitations**

This is intentionally a simplified framework.

Current limitations include:

- simplified opponent behavior assumptions
- no bet sizing inference
- no game-theoretic equilibrium modeling
- no reinforcement learning
- no multi-street recursive solving

Future improvements could include:

- action-frequency calibration
- dynamic bet sizing likelihoods
- opponent profiling
- vectorized simulation optimization

# **Technologies**

- Python
- treys
- Monte Carlo simulation
- Bayesian inference
- Kelly Criterion
