# 🧠 Brian2 Fundamentals

A hands-on computational neuroscience project exploring **biological neuron models, synaptic dynamics, neural networks, and spike-based learning** using [Brian2](https://brian2.readthedocs.io/).

The project begins with fundamental neuron and synapse models and gradually progresses toward **spiking neural networks (SNNs)** and neural computation.

---

## 🚀 Overview

The goal of this project is to understand how mathematical models can be translated into executable neural simulations.

The overall progression is:

**Mathematical Models → Neurons → Synapses → Networks → Plasticity → SNNs**

The primary notebook for this stage is:

📓 **`Brian2_Fundamentals.ipynb`**

The notebook was developed and tested in **Google Colab**.

---

# 🧠 Neuron Models

Several classical neuron models were implemented and simulated, ranging from simple integrate-and-fire models to nonlinear dynamical systems.

### 1. Leaky Integrate-and-Fire (LIF)

The LIF model represents a neuron as a leaky membrane integrator.

It introduces the fundamental concepts of:

- Membrane potential
- Membrane leakage
- External current
- Threshold
- Spike generation
- Reset
- Refractory period

The basic dynamics are:

<div align="center">

\[
\tau_m \frac{dV}{dt}
=
-(V-V_L)+RI
\]

</div>

---

### 2. Adaptive Neuron Models

Adaptive dynamics were explored by introducing additional variables that modify neuronal excitability.

Topics include:

- Spike-frequency adaptation
- Recovery dynamics
- Adaptive firing
- Changes in neuronal excitability

---

### 3. Izhikevich Model

The Izhikevich model combines nonlinear membrane dynamics with an adaptation variable.

The model can reproduce a wide range of neuronal firing behaviors.

Examples include:

- Regular spiking
- Fast spiking
- Bursting
- Chattering
- Spike-frequency adaptation

---

### 4. FitzHugh-Nagumo Model

The FitzHugh-Nagumo model is a reduced two-variable model of neuronal excitability.

It separates neuronal dynamics into:

- A fast excitation variable
- A slower recovery variable

This model was used to explore:

- Excitability
- Spike generation
- Recovery
- Nonlinear oscillations
- Limit-cycle behavior

---

### 5. Morris-Lecar Model

The Morris-Lecar model is a conductance-based neuron model.

It represents neuronal dynamics through ionic currents, including:

- Calcium current
- Potassium current
- Leak current

The model provides an introduction to:

- Conductance-based modeling
- Reversal potentials
- Ionic currents
- Nonlinear dynamics
- Neuronal oscillations

---

### 6. Hindmarsh-Rose Model

The Hindmarsh-Rose model introduces three interacting dynamical variables and allows significantly more complex neuronal behavior.

The model can produce:

- Spiking
- Bursting
- Quiescence
- Mixed-mode dynamics
- Nonlinear oscillations

This provides a transition from relatively simple neuron models toward complex dynamical systems.

---

# ⚡ Synaptic Models

The project also explores how neurons communicate with one another through synapses.

---

## Basic Synapses

Brian2's `Synapses` framework was used to create connections between neurons.

Different connectivity mechanisms were explored, including:

- Explicit connections
- Conditional connections
- Probabilistic connections
- One-to-one connections
- Recurrent connections

---

## Excitatory Synapses

Excitatory synapses increase postsynaptic neuronal activity.

They were used to study:

- Synaptic weights
- Postsynaptic responses
- Excitatory transmission
- Network activation

---

## Inhibitory Synapses

Inhibitory synapses reduce postsynaptic activity.

They were used to investigate:

- Inhibitory transmission
- Reversal potentials
- Suppression of neural activity
- Excitation-inhibition balance

---

# 🔌 CUBA Synapses

**CUBA (Current-Based Synapses)** models synaptic transmission through currents.

A presynaptic spike produces a change in postsynaptic current.

<div align="center">

\[
I_{syn} \leftarrow I_{syn} + w
\]

</div>

CUBA models are:

- Simple
- Computationally efficient
- Useful for large-scale SNNs
- Easy to implement

---

# ⚡ COBA Synapses

**COBA (Conductance-Based Synapses)** models synaptic transmission through conductances.

The synaptic current depends on the membrane potential and synaptic reversal potential.

<div align="center">

\[
I_{syn}=g_{syn}(V-E_{syn})
\]

</div>

COBA provides a more biologically realistic representation of synaptic transmission.

### CUBA vs COBA

| Feature | CUBA | COBA |
|---|---|---|
| Synaptic quantity | Current | Conductance |
| Voltage dependent | ❌ | ✅ |
| Reversal potential | Not required | Required |
| Complexity | Lower | Higher |
| Biological realism | Lower | Higher |
| Suitable for SNNs | ✅ | ✅ |

---

# 🔗 Neural Networks

After studying individual neurons and synapses, the project progresses toward networks of interacting neurons.

## Recurrent Networks

Recurrent connections allow neurons to influence one another.

```text
Neuron 1 ─────→ Neuron 2
   ↑               │
   │               ↓
Neuron 4 ←───── Neuron 3
