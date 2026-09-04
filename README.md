#  Brian2 Fundamentals

A hands-on computational neuroscience project exploring **biological neuron models, synaptic dynamics, neural networks, and spike-based learning** using [Brian2](https://brian2.readthedocs.io/).

The project progresses from individual neuron models to synapses, neural populations, recurrent networks, and synaptic plasticity.

---

##  Overview

The goal of this project is to understand how mathematical models of neurons and synapses can be implemented, simulated, and visualized computationally.

The overall progression is:

**Mathematical Models → Neurons → Synapses → Networks → Plasticity → Spiking Neural Networks**

The primary notebook for this stage is:

 **`Brian2_Fundamentals.ipynb`**

The notebook was developed and tested using **Google Colab**.

> **Note:** This repository focuses on implementing and visualizing the fundamental concepts first. Detailed experiments for individual models and advanced topics will be developed in separate notebooks.

---

#  Neuron Models

Multiple classical neuron models were implemented and simulated, ranging from simple integrate-and-fire neurons to nonlinear dynamical systems.

---

## 1. Leaky Integrate-and-Fire (LIF)

The **Leaky Integrate-and-Fire (LIF)** model represents a neuron as a leaky membrane integrator.

It introduces the fundamental concepts required to understand spiking neurons.

### Concepts explored

- Membrane potential
- Membrane leakage
- External current
- Threshold
- Spike generation
- Reset mechanism
- Refractory period
- Numerical simulation
- Spike timing

The LIF model provides the basic foundation for understanding how a neuron integrates input and generates spikes.

---

## 2. Adaptive Neuron Models

Adaptive neuron models were explored by introducing additional variables that modify neuronal excitability based on the neuron's previous activity.

### Concepts explored

- Spike-frequency adaptation
- Recovery dynamics
- Adaptive firing
- Changes in neuronal excitability
- Interaction between membrane dynamics and adaptation
- Different firing responses to external input

Adaptive models provide a bridge between simple integrate-and-fire neurons and more biologically expressive neuron models.

---

## 2. Exponential Leaky Integrate-and-Fire (Exponential LIF / ELIF)

The **Exponential Leaky Integrate-and-Fire (ELIF)** model extends the standard LIF model by introducing a nonlinear exponential term near the firing threshold.

While the standard LIF model has a linear relationship between membrane potential and its rate of change, the exponential term in the ELIF model causes the membrane potential to rise rapidly as it approaches threshold.

This provides a smoother and more biologically realistic transition toward spike generation while retaining the computational simplicity of an integrate-and-fire model.

### Concepts explored

- Extension of the standard LIF model
- Nonlinear membrane dynamics
- Exponential spike initiation
- Membrane potential evolution
- Threshold behavior
- Spike generation
- Reset mechanism
- Refractory period
- Comparison between LIF and ELIF
- Effect of changing model parameters

---  

## 3. Izhikevich Model

The **Izhikevich neuron model** combines nonlinear membrane dynamics with an adaptation variable.

One of its major advantages is that it can reproduce a wide range of biologically relevant firing patterns while remaining computationally efficient.

### Behaviors explored

- Regular spiking
- Fast spiking
- Bursting
- Chattering
- Spike-frequency adaptation
- Different neuronal firing regimes

This model demonstrates how changing model parameters can produce fundamentally different neuronal behaviors.

---

## 4. FitzHugh-Nagumo Model

The **FitzHugh-Nagumo model** is a reduced two-variable model of neuronal excitability.

It separates neuronal dynamics into:

- A fast excitation variable
- A slower recovery variable

### Concepts explored

- Excitability
- Spike generation
- Recovery dynamics
- Nonlinear oscillations
- Limit-cycle behavior
- Dynamical-systems interpretation of neurons
- Response to external stimulation

The model provides an introduction to nonlinear dynamical systems in computational neuroscience.

---

## 5. Morris-Lecar Model

The **Morris-Lecar model** is a conductance-based neuron model.

It represents neuronal behavior through ionic currents and conductances.

### Concepts explored

- Conductance-based modeling
- Ionic currents
- Calcium dynamics
- Potassium dynamics
- Leak currents
- Reversal potentials
- Nonlinear neuronal dynamics
- Oscillatory behavior
- Excitability

The Morris-Lecar model provides a more biologically motivated description of neuronal activity compared with simplified integrate-and-fire models.

---

## 6. Hindmarsh-Rose Model

The **Hindmarsh-Rose model** uses multiple interacting dynamical variables to reproduce complex neuronal activity.

### Behaviors explored

- Spiking
- Bursting
- Quiescence
- Mixed-mode dynamics
- Nonlinear oscillations
- Complex neuronal activity

This model provides a transition from relatively simple neuron models toward more complex dynamical systems.

---

#  Synaptic Models

The project explores how neurons communicate with one another through synaptic connections.

---

## Basic Synapses

Brian2's `Synapses` framework was used to establish connections between presynaptic and postsynaptic neurons.

Different connectivity mechanisms were explored, including:

- Explicit connections
- Conditional connections
- Probabilistic connections
- One-to-one connections
- Recurrent connections
- Synaptic weights
- Synaptic delays

The experiments demonstrate how the structure of connections affects neural activity.

---

## Excitatory Synapses

Excitatory synapses increase postsynaptic neuronal activity.

They were used to study:

- Excitatory transmission
- Synaptic weights
- Postsynaptic responses
- Spike propagation
- Network activation
- Interaction between connected neurons

---

## Inhibitory Synapses

Inhibitory synapses reduce postsynaptic neuronal activity.

They were used to investigate:

- Inhibitory transmission
- Reversal potentials
- Suppression of neural activity
- Excitation-inhibition balance
- Network stability

---

#  CUBA Synapses

**CUBA (Current-Based Synapses)** models synaptic transmission using currents.

A presynaptic spike produces a change in postsynaptic current.

### Characteristics

- Simple
- Computationally efficient
- Easy to implement
- Useful for large-scale spiking neural networks
- Suitable for studying basic synaptic interactions

CUBA provides an intuitive starting point for understanding synaptic transmission in spiking neural networks.

---

#  COBA Synapses

**COBA (Conductance-Based Synapses)** models synaptic transmission using conductances.

The synaptic current depends on the postsynaptic membrane potential and synaptic reversal potential.

### Characteristics

- More biologically realistic than simple current-based models
- Voltage dependent
- Uses synaptic reversal potentials
- Represents synaptic conductances
- Useful for studying biologically motivated network dynamics

---

## CUBA vs COBA

| Feature | CUBA | COBA |
|---|---|---|
| Synaptic quantity | Current | Conductance |
| Voltage dependent | ❌ | ✅ |
| Reversal potential | Not required | Required |
| Complexity | Lower | Higher |
| Biological realism | Lower | Higher |
| Computational cost | Lower | Higher |
| Suitable for SNNs | ✅ | ✅ |

---

#  Neural Networks

After studying individual neurons and synapses, the project progresses toward networks of interacting neurons.

---

## Recurrent Networks

Recurrent connections allow neurons to influence one another within the same population.

```text
Neuron 1 ─────→ Neuron 2
   ↑               │
   │               ↓
Neuron 4 ←───── Neuron 3
```

Recurrent networks allow investigation of:

- Feedback
- Persistent activity
- Synchronization
- Network memory
- Collective dynamics
- Recurrent spike propagation
- Network stability

Recurrent connectivity is an important step toward understanding how complex behavior can emerge from interacting neurons.

---

#  Excitatory-Inhibitory Networks

Separate excitatory and inhibitory populations were used to study population-level neural dynamics.

The network architecture can contain:

- Excitatory → Excitatory
- Excitatory → Inhibitory
- Inhibitory → Excitatory
- Inhibitory → Inhibitory

This provides a basic framework for studying:

- Excitation-inhibition balance
- Population activity
- Network stability
- Synchronization
- Collective neural behavior
- Feedback between neural populations

---

#  Poisson Input

Stochastic neural input was explored using Poisson spike trains.

Poisson input can be used to represent:

- Background neural activity
- External stimulation
- Random spike trains
- Stochastic network input
- Network perturbations

This provides a simple way of introducing randomness into neural simulations.

---

#  Monitoring and Visualization

Brian2 monitoring tools were used to record and visualize neural activity.

---

## StateMonitor

`StateMonitor` was used to record continuous state variables.

Examples include:

- Membrane potential
- Synaptic conductance
- Adaptation variables
- Other neuron state variables

These recordings can then be plotted to visualize the evolution of neural states over time.

---

## SpikeMonitor

`SpikeMonitor` was used to record neuronal spikes.

It provides information such as:

- Spike times
- Neuron indices
- Spike counts
- Spike trains

This information can be used to generate raster plots and perform spike analysis.

---

## PopulationRateMonitor

`PopulationRateMonitor` was used to measure the firing rate of a neural population.

This is useful for studying:

- Population activity
- Average firing rate
- Network oscillations
- Collective behavior
- Temporal changes in network activity

---

#  Neural Activity Visualization

Several visualization techniques were explored throughout the simulations.

---

## Membrane Potential Plots

Membrane potential plots show how the voltage of a neuron changes over time.

These plots help visualize:

- Action potentials
- Subthreshold dynamics
- Oscillations
- Bursting
- Adaptation
- Neuronal responses to external input

---

## Raster Plots

Raster plots visualize spike timing across a population of neurons.

They can be used to identify:

- Firing patterns
- Bursting
- Synchronization
- Population activity
- Spike timing
- Network-wide activity

Example:

```text
Neuron
  9 |    •       •       •
  8 |       •       •
  7 | •       •       •
  6 |    •       •
  5 |       • •       •
  4 | •       •       •
  3 |    •       •
  2 |       •       •
  1 | •       •       •
  0 |    •       •
    +----------------------→ Time
```

Raster plots are particularly useful for identifying synchronization and population-level firing patterns.

---

#  STDP

**Spike-Timing-Dependent Plasticity (STDP)** was implemented to explore activity-dependent changes in synaptic strength.

STDP modifies synaptic weights according to the relative timing of presynaptic and postsynaptic spikes.

Conceptually:

```text
Presynaptic spike
        ↓
Postsynaptic spike
        ↓
Synaptic potentiation
```

and:

```text
Postsynaptic spike
        ↓
Presynaptic spike
        ↓
Synaptic depression
```

STDP introduces the concept of **learning through synaptic plasticity** into spiking neural networks.

### Concepts explored

- Synaptic weight updates
- Pre/post spike timing
- Potentiation
- Depression
- Activity-dependent learning
- Plasticity in spiking neural networks

---

#  Brian2 Units

One of the important features explored in Brian2 is its built-in physical unit system.

Examples include:

```python
mV
ms
Hz
pA
nA
uA
nS
pF
```

Brian2 automatically checks dimensional consistency in neuron and synapse equations.

This is particularly useful when implementing biological models because incorrect units can be detected before the simulation begins.

The unit system helps prevent common mistakes such as:

- Mixing voltage and current
- Using incorrect time units
- Assigning incompatible quantities
- Writing equations with inconsistent dimensions

---

#  Technologies

The project uses:

- **Python**
- **Brian2**
- **NumPy**
- **Matplotlib**
- **Google Colab**
- **Jupyter Notebook**

---

#  Project Structure

```text
Brian2_Fundamentals/
│
├── README.md
│
└── Brian2_Fundamentals.ipynb
```

The fundamentals notebook serves as the foundation for future computational neuroscience experiments.

Detailed experiments will be developed in separate notebooks.

---

#  Learning Progression

```text
LIF
 │
 ▼
Adaptive Neurons
 │
 ▼
Izhikevich
 │
 ▼
FitzHugh-Nagumo
 │
 ▼
Morris-Lecar
 │
 ▼
Hindmarsh-Rose
 │
 ▼
Synapses
 │
 ├── Excitatory
 ├── Inhibitory
 ├── CUBA
 └── COBA
 │
 ▼
Recurrent Networks
 │
 ▼
Excitatory-Inhibitory Networks
 │
 ▼
Poisson Input
 │
 ▼
Network Dynamics
 │
 ▼
STDP
 │
 ▼
Spiking Neural Networks
```

---

#  Current Status

The fundamentals stage covers:

- Brian2 fundamentals
- Physical units
- Dimensional analysis
- LIF neurons
- Adaptive neuron models
- Izhikevich neurons
- FitzHugh-Nagumo neurons
- Morris-Lecar neurons
- Hindmarsh-Rose neurons
- Excitatory synapses
- Inhibitory synapses
- Synaptic weights
- Synaptic delays
- CUBA synapses
- COBA synapses
- Recurrent networks
- Excitatory-inhibitory networks
- Poisson input
- SpikeMonitor
- StateMonitor
- PopulationRateMonitor
- Raster plots
- Membrane-potential visualization
- Network activity analysis
- STDP

---

#  Future Work

The fundamentals notebook will remain as the foundation of the project.

Future experiments will be developed in separate notebooks covering topics such as:

- Hodgkin-Huxley model
- Detailed ion-channel dynamics
- Advanced synaptic models
- Short-term synaptic plasticity
- Detailed STDP experiments
- Neural coding
- Population coding
- Large-scale spiking neural networks
- Reservoir computing
- Neuromorphic computing
- SNN learning
- Reinforcement learning with SNNs

---

#  Future Notebook Organization

The project will eventually be organized into separate notebooks for deeper experiments:

```text
Brian2_Fundamentals/
│
├── Brian2_Fundamentals.ipynb
│
├── Neuron_Models/
│   ├── LIF.ipynb
│   ├── Izhikevich.ipynb
│   ├── FitzHugh_Nagumo.ipynb
│   ├── Morris_Lecar.ipynb
│   └── Hindmarsh_Rose.ipynb
│
├── Synapses/
│   ├── Basic_Synapses.ipynb
│   ├── CUBA.ipynb
│   ├── COBA.ipynb
│   └── STDP.ipynb
│
├── Networks/
│   ├── Recurrent_Networks.ipynb
│   ├── Excitatory_Inhibitory_Networks.ipynb
│   └── Poisson_Networks.ipynb
│
└── README.md
```

The current fundamentals notebook acts as the starting point before moving toward these specialized experiments.

---

#  What This Project Covers

This project establishes the core concepts required to move into more advanced computational neuroscience and spiking neural network research.

The progression can be summarized as:

```text
Individual Neurons
        ↓
Neuron Dynamics
        ↓
Synaptic Communication
        ↓
Neural Populations
        ↓
Recurrent Networks
        ↓
Network Dynamics
        ↓
Synaptic Plasticity
        ↓
Learning in SNNs
```

---

# 👤 Author

**Srujan**

---

# 📚 References

- [Brian2 Documentation](https://brian2.readthedocs.io/)
- [Brian2 Tutorials](https://brian2.readthedocs.io/en/stable/resources/tutorials/)
- [Brian2 Examples](https://brian2.readthedocs.io/en/stable/examples/index.html)

---

