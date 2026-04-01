# Presentation Outline: Autonomous Urban Ecosystem Repair Swarm

### 1. The Core Problem: Static vs. Dynamic Sensing
*   **Traditional Monitoring:** Large, expensive stations that provide data but don't 'act.'
*   **The Swarm Vision:** A network of $10 nodes that not only detect pollution but coordinate a response (like deploying repair drones) without needing a central server.

### 2. Phase 1: Building the 'Brain' (TinyML)
*   **The Data:** We used the UCI Air Quality dataset, focusing on sensor readings (CO, NOx, Temperature, Humidity).
*   **Intelligence:** We trained a Deep Learning model to categorize 'Pollution Levels' (Low to Very High).
*   **Shrinking the Brain:** To fit on a tiny microcontroller, we used **int8 Quantization**. This reduced the model size to ~4KB (the size of a small text file) while keeping it smart.
*   **Hardware Ready:** We converted the model into a **C Header file (`.h`)**, which is the 'language' microcontrollers like ESP32 or Arduino speak.

### 3. Phase 2: Swarm Intelligence (Collective Logic)
*   **Decentralized Voting:** Instead of one node making a mistake, we simulated a 3-node swarm. They 'vote' on the urgency of the situation.
*   **Spatial Awareness:** We implemented an **Adjacency Matrix** (Graph Logic). This ensures nodes trust their immediate neighbors more than distant sensors, preventing 'false alarms' from outliers.
*   **Self-Healing:** If one node is damaged or tampered with, the swarm uses **Anomaly Detection** (Z-scores) to ignore the faulty data and keep the mission going.

### 4. Phase 3: Sustainability & Survival
*   **The 'Golden Ratio':** We simulated a 24-hour solar cycle. Since these nodes live outside, they must balance 'Thinking Time' with 'Sleeping Time.'
*   **Power Management:** We proved that a node can survive indefinitely on a 500mAh battery if it intelligently schedules its inferences based on environmental triggers.

### 5. Future Impact
*   **Scalability:** This logic can be scaled to 100+ nodes to cover an entire city park or industrial zone.
*   **Autonomous Action:** This isn't just a dashboard; it's a foundation for a 'Self-Healing City' where the environment looks after itself.


