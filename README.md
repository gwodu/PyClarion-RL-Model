
# Modeling Strategy Formation in Dynamic Decision-Making using PyClarion

This repository contains the simulation code for the project:  
**Modeling Strategy Formation in Dynamic Decision-Making: A Clarion Cognitive Architecture Approach**  
by **Gesikeme L. Wodu** for the COG403 Seminar in Cognitive Science.

The model replicates a dynamic auditory categorization task with a reversal phase, originally simulated using ACT-R by Prezenski et al. (2017). The PyClarion implementation integrates reinforcement learning into the Clarion cognitive architecture to explore the dual-process capabilities of implicit associative and explicit rule-based decision-making.

---

## 🧠 Repository Structure

```
├── Final Project Clarion Model.ipynb   # Jupyter Notebook with full simulation code
├── README.md                           # Project overview and replication instructions
```

---

## 📦 Requirements

This project depends on the PyClarion framework. To replicate the simulation:

1. **Clone the PyClarion repository from the correct branch:**

```bash
git clone --branch v2409 https://github.com/cmekik/pyClarion.git
cd pyClarion
pip install .
```

2. **Install additional dependencies if needed:**

```bash
pip install numpy matplotlib
```

---

## 🔁 Reproducing the Simulation

Open the notebook file titled **`Final Project Clarion Model.ipynb`** and execute each cell sequentially to reproduce the simulation results and visualizations described in the final paper.

The simulation follows four main stages, aligned with Clarion modeling practices:

---

### 1. 🧩 Key Space Definition

- Initialize the **Family**, **Atoms**, and **Atom** classes to define the abstract variable spaces your model will operate within.
- These include concepts such as actions (`target`, `non-target`), features (`duration`, `modulation`), and perceptual elements (sound properties).

---

### 2. 🏗️ Model Construction

- Create the Clarion cognitive agent by composing **Chambers** (i.e., subsystems like the Action-Centered Subsystem).
- Define the **Implicit Decision Network (IDN)** using Q-learning, which governs how the model adapts over time.
- Construct the control flow using `ClarionAgent`, encapsulating memory, rule application, and subsymbolic learning.

---

### 3. 🧠 Knowledge Initialization

- Initialize specific task knowledge:
  - Initial rules (if any)
  - Reward structures (reward1: for misclassifying targets initially, reward2: reversed reward mapping after trial 120)
- This step also defines the **reinforcement learning loop**, configuring learning rate, discount factor, and value tracking (e.g., Q-values).

---

### 4. 🔄 Event Processing

- Structure the experiment loop:
  - Present stimuli (tones)
  - Collect model predictions
  - Provide rewards and update Q-values
  - Track performance using cumulative rewards and Q-value confidence
- This segment corresponds to the 240 trial timeline used in the original experiment with a reversal at trial 120.

---

📘 **Reference:**  
Refer to the included [PyClarion tutorial on the official GitHub repository](https://github.com/cmekik/pyClarion) for a detailed walkthrough of the architecture and implementation examples.

---

## 📊 Output

Running the notebook will generate:
- A plot of cumulative rewards over 240 trials
- A plot of maximum Q-values (action confidence)
- Behavioral comparison to human and ACT-R baselines

These outputs replicate the results section in the final project report.

---

## 📚 Citation

If referencing this project or codebase, please cite:

> Wodu, G. L. (2025). *Modeling Strategy Formation in Dynamic Decision-Making: A Clarion Cognitive Architecture Approach*. University of Toronto.

---

## ✉️ Contact

For questions or collaborations, feel free to reach out via GitHub or @ge.wodu@gmail.com.

---
