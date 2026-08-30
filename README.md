# Brian2_Fundamentals-Computational Neuroscience
A hands-on collection of computational neuroscience simulations implemented using **Brian2**, covering classical neuron models, synaptic models, neural networks, spike-based learning, and neural activity visualization.

The purpose of this repository is to build a strong foundation in **computational neuroscience and spiking neural networks (SNNs)** by implementing mathematical neuron and synapse models from scratch and studying their dynamics through simulation.

The experiments are designed to be runnable in **Google Colab / Jupyter Notebook**.

---

## 🚀 Overview

This project explores the progression:

```text
Mathematical Models
       ↓
Single Neurons
       ↓
Spiking Neurons
       ↓
Synapses
       ↓
Neural Networks
       ↓
Network Dynamics
       ↓
Synaptic Plasticity
       ↓
Spiking Neural Networks

🧠 Neuron Models

The notebook implements and visualizes multiple classical neuron models, ranging from simple integrate-and-fire models to nonlinear dynamical systems.

1. Leaky Integrate-and-Fire (LIF)

The LIF neuron models the membrane potential as a leaky integrator.

The basic equation is:

$$ \tau_m\frac{dV}{dt} = -(V-V_L)+RI $$

When:

$$ V \geq V_{th} $$

the neuron generates a spike and the membrane potential is reset.

Concepts explored
Membrane potential
Leak current
External current
Threshold
Spike generation
Reset mechanism
Refractory period
Numerical simulation
