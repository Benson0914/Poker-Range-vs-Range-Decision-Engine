# Poker-Range-vs-Range-Decision-Engine
# **🧠 Overview**

This project simulates decision-making under uncertainty using a poker framework.
It models range-vs-range interactions and evaluates expected value (EV) to determine optimal actions (call or fold).
The goal is to demonstrate probabilistic thinking and decision-making under incomplete information, similar to trading environments.

# **⚙️ Key Components**

**1. Range Parsing**

- Supports inputs such as:
    - AA, 88+, AKs, AJo
- Generates all possible hand combinations using combinatorics

**2. Monte Carlo Simulation**

- Simulates random outcomes given:
    - Hero hand
    - Villain range
    - Partial board (e.g., flop)
- Handles:
    - Dead card removal
    - Random board completion
- Outputs:
    - Equity (win probability)

**3. Expected Value (EV) Calculation**

Decision rule:

- Call EV:
EV = equity × (pot + call_cost) − call_cost
- Fold EV = 0
- Choose action with higher EV

**4. Decision Engine**

Returns:

- Equity
- Call EV
- Fold EV
- Final decision (CALL / FOLD)

# **Example**

hero = ['Jh', 'Qs']
villain_range = parser.parse_range("8hTd")
board = ['Jd', '9h', 'Ts']
equity = range_vs_range_equity(hero, villain_range, board)
result = decide_call_or_fold(equity, pot=100, call_cost=50)

# **📊 Insights**

- Demonstrates decision-making under uncertainty
- Shows how small changes in equity affect optimal action
- Highlights the importance of edge and risk-reward trade-offs

# **Limitations**

- Assumes equal weighting across opponent ranges
- Single-street model (no future betting)
- Monte Carlo approximation introduces variance

# **Relevance to Quant Trading**

This project reflects key aspects of trading:

- Expected value-based decision-making
- Managing uncertainty and incomplete information
- Evaluating edge and risk trade-offs
