# Optimizing Electric Vehicle Charging Station Placement with Reinforcement Learning

**Team Member:** Minwei Kong, Ruiming Wu, Mengqi Liu  
**Supervisor:** Prof. Chengchun Shi, Department of Statistics, LSE    
**Keywords:** electric vehicle charging station, spatial optimization, reinforcement learning 

---

## Project Overview
This project addresses the optimal placement of electric vehicle (EV) charging stations in central London using [Open Charge Map](https://map.openchargemap.io/#/search) data, to support zero-emission policies. By framing the placement as a reinforcement learning (RL) task, this project aims to maximize utility by efficiently arranging charging stations to balance coverage benefits and time costs within budget constraints.

### Key Contributions
- **Formulated** charging station placement as an RL problem with agent, state, action, reward and policy.
- **Developed** a utility function evaluating placement plans, accounting for various practical constraints.
- **Implemented** RL algorithms (DQN, A2C, PPO) to optimize station placement, outperforming traditional baselines.
- **Visualized** optimal placements on interactive maps to compare practical implications.

### RL Problem Components
- **State:** Current spatial layout of charging stations and configurations.
- **Action:** Adding new stations, increasing station capacity, or relocating stations.
- **Reward:** Utility difference before and after layout changes.

### Evaluation Metrics
| Metric         | Description                                                                                      | Ideal Outcome   |
|----------------|--------------------------------------------------------------------------------------------------|-----------------|
| **Score**      | Represents the comprehensive performance of the charging plan (CP) based on its utility.          | Higher is better|
| **Benefit**    | Measures the advantage of the CP excluding the cost function, as specified in a utility model.     | Higher is better|
| **Waiting Time**| The aggregate of all waiting times at charging stations (CS) across the road network.             | Lower is better |
| **Travel Time** | The total time spent traveling within the road network.                                           | Lower is better |
| **Charging Time**| The cumulative time spent charging within the road network.                                      | Lower is better |


### Results
The RL algorithms significantly improved performance over greedy-based methods:
| Algorithm       | Score  | Benefit | Cost   | Travel Time | Charging Time | Waiting Time |
|-----------------|--------|---------|--------|-------------|---------------|--------------|
| EXISTING        | 100.00 | 100.00  | 100.00 | 100.00      | 100.00        | 100.00       |
| BEST_BENEFIT    | 181.97 | 126.75  | 83.27  | 73.91       | 109.51        | 47.84        |
| HIGHEST_DEMAND  | 182.00 | 126.75  | 83.25  | 73.89       | 109.51        | 47.84        |
| DQN             | 197.87 | 128.75  | 74.34  | 72.80       | 78.93         | 29.64        |
| A2C             | 186.75 | 127.88  | 81.54  | 73.92       | 102.98        | 45.21        |
| PPO             | 190.39 | 125.61  | 74.61  | 76.43       | 69.89         | 30.23        |


## Attribution
The project was completed by three LSE students from the Department of Geography and Environment, the Department of Statistics. I contributed approximately 80% of the coding and 20% of the writing.     
It received a high distinction (96/100) in the ST455 Reinforcement Learning course at LSE.
