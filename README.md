# 🍲 Multi-Agent Reinforcement Learning in Overcooked

---

### 📝 Abstract  
- **Agent Features (50 elements each):** 🧑‍🍳 Encodes orientation, currently held objects, distances to key items (e.g., onion, pot, serving counter), and detailed contextual data, such as pot states (empty, cooking, ready), proximity to obstacles (walls, counters), and dynamic environment attributes.  

This study investigates the application of advanced **Reinforcement Learning (RL)** techniques, including **Proximal Policy Optimization (PPO)** and **Multi-Agent Deep Deterministic Policy Gradients (MADDPG)**, within the multi-agent **"Overcooked"** simulation. Agents collaborate to prepare and deliver onion soups in a variety of kitchen layouts, emphasizing the importance of communication, coordination, and adaptive strategies. 🧅 🍜  

Results highlight how architectural choices and hyperparameter tuning critically impact multi-agent performance in dynamic, partially observable environments. This research contributes to developing scalable solutions for RL in cooperative tasks and provides valuable insights into optimizing learning efficiency in real-time scenarios.  

- **Teammate Features (50 elements):** 👫 A mirrored set of features for the teammate, representing their current state, held objects, and relative position.  
- **Interaction Metrics (6 elements):** 🔄 Captures inter-agent dynamics, such as distances and coordinated tasks.  

This feature set ensures that agents are equipped with a **holistic representation** of their own state, their teammate's state, and the broader environment. This comprehensive encoding enhances decision-making capabilities for cooperative gameplay.  

---

### 🌍 Environment and Task Description  
Agents are trained within the **Overcooked** game to collaboratively prepare and serve onion soup 🍲. The environment spans five distinct kitchen configurations:  
1. **Cramped Kitchen** 🏠: Small, shared spaces requiring precise navigation.  
2. **Asymmetric Layout** ↔️: One agent has greater access to resources, promoting role specialization.  
3. **Coordination Ring** 🔁: Tasks demand tight synchronization due to circular pathways.  
4. **Forced Coordination** 🤝: Critical tasks cannot be completed without joint effort.  
5. **Dynamic Circuit** ⚙️: High mobility is required to navigate moving obstacles.  

The goal is to maximize completed soup deliveries within a **400-timestep episode**, with each soup requiring **20 timesteps** to cook. Deliveries earn a **+20 reward**, while errors such as cooking with incomplete ingredients or misplacing items result in lost opportunities without direct penalties.

---

### 🎮 Action Space  
The environment defines a discrete action space comprising:  
1. ⬆️ Move up  
2. ⬇️ Move down  
3. ⬅️ Move left  
4. ➡️ Move right  
5. 🛑 Stay  
6. 🛠️ Interact (context-sensitive action based on proximity to objects like pots, counters, or other agents)  

---

### 🎯 Objectives  
The Overcooked environment functions as a **Markov Decision Process (MDP)**, offering agents full observability of the game state represented as a **100-element vector** for each agent. This vector incorporates environmental features, inter-agent dynamics, and individual states, allowing agents to adapt to complex kitchen layouts.  

The challenge is to develop a single algorithm that performs effectively across all layouts, with a target of **at least eight soups delivered per episode** on average.  

Key goals:  
- **⚙️ Robustness**: Adapt to various task demands.  
- **📈 Scalability**: Facilitate multi-agent decision-making.  
- **⏱️ Optimization**: Maximize task efficiency within a constrained timeframe.  

This study explores the role of diverse RL architectures in achieving these goals while evaluating performance through standardized metrics and layout-specific benchmarks.  
