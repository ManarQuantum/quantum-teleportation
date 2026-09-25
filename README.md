# Quantum Teleportation using Qiskit

A computational implementation and verification of the quantum teleportation protocol using Qiskit.

This project demonstrates how a single-qubit quantum state can be transferred to another qubit using entanglement and coherent quantum operations. The protocol is simulated using an ideal statevector model, and the receiver's state is compared with the original input using quantum-state fidelity.

---

## Overview

Quantum teleportation is a fundamental protocol in quantum information that allows an unknown quantum state to be transferred from one qubit to another using a shared entangled state and quantum operations.

The protocol does **not** physically transmit the quantum state itself. Instead, quantum entanglement and local operations allow the receiver to reconstruct the original state.

The standard operational teleportation protocol involves:

1. Preparing the input quantum state
2. Creating a shared Bell pair
3. Performing a Bell-basis measurement
4. Communicating the measurement results classically
5. Applying conditional corrections at the receiver

This project uses a **coherent, measurement-free formulation** of the teleportation circuit. This formulation is useful for computational verification because the complete quantum state remains available for statevector analysis.

The simulation assumes an ideal, noiseless quantum system.

---

## Protocol

The circuit uses three qubits:

| Qubit   | Role                                       |
| ------- | ------------------------------------------ |
| Qubit 0 | Input quantum state to be teleported       |
| Qubit 1 | Sender's half of the entangled Bell pair   |
| Qubit 2 | Receiver's half of the entangled Bell pair |

The main operations are:

1. Prepare the input state on qubit 0.
2. Create a Bell pair between qubits 1 and 2.
3. Apply the Bell-basis transformation to qubits 0 and 1.
4. Apply coherent correction operations to qubit 2.
5. Simulate the resulting three-qubit state.
6. Trace out qubits 0 and 1.
7. Compare the receiver's reduced state with the original input state using fidelity.

---

## Input States

The teleportation protocol is tested using four standard single-qubit states:

| State | Description       | Basis / Property          |                      |                                         |         |
| ----- | ----------------- | ------------------------- | -------------------- | --------------------------------------- | ------- |
| $     | 0\rangle$         | Computational basis state | Z-basis              |                                         |         |
| $     | 1\rangle$         | Computational basis state | Z-basis              |                                         |         |
| $     | +\rangle = \frac{ | 0\rangle +                | 1\rangle}{\sqrt{2}}$ | Equal superposition                     | X-basis |
| $     | -\rangle = \frac{ | 0\rangle -                | 1\rangle}{\sqrt{2}}$ | Equal superposition with relative phase | X-basis |

Testing both computational-basis and superposition states provides a more meaningful verification than testing a single input state.

---

## Fidelity Verification

The quality of the teleportation is evaluated using quantum-state fidelity.

For the input state $\rho$ and the receiver's reduced state $\sigma$, the fidelity is written as:

$$
F(\rho,\sigma)
$$

For an ideal noiseless teleportation process:

$$
F \approx 1
$$

A fidelity of 1 indicates that the receiver's state is identical to the original input state.

Small numerical deviations from exactly 1 can occur because of floating-point precision.

---

## Results

The ideal statevector simulation is expected to produce fidelity values numerically equal or extremely close to 1 for all four tested states.

| Input State | Expected Fidelity | Interpretation |                                                          |
| ----------- | ----------------: | -------------- | -------------------------------------------------------- |
| $           |         0\rangle$ | $\approx 1$    | Input state reproduced at receiver                       |
| $           |         1\rangle$ | $\approx 1$    | Input state reproduced at receiver                       |
| $           |         +\rangle$ | $\approx 1$    | Superposition state reproduced at receiver               |
| $           |         -\rangle$ | $\approx 1$    | Superposition with relative phase reproduced at receiver |

The notebook calculates these values directly from the simulated quantum states rather than assuming the result.

---

## Visualization

The experiment also generates a comparison of the teleportation fidelity for the four input states.

![Teleportation Fidelity](results/fidelity_comparison.png)

---

## Implementation

The project is implemented using:

* **Python** — programming language
* **Qiskit** — quantum circuit construction and simulation
* **NumPy** — numerical computation
* **Matplotlib** — result visualization
* **Jupyter** — interactive computational notebook

The simulation uses Qiskit's statevector representation to examine the quantum state produced by the circuit.

---

## Repository Structure

```text
quantum-teleportation/
│
├── README.md
├── quantumteleportation.ipynb
├── requirements.txt
├── LICENSE
│
└── results/
    └── fidelity_comparison.png
```

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/quantum-teleportation.git
cd quantum-teleportation
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows:**

```bash
.venv\Scripts\activate
```

**Linux / macOS:**

```bash
source .venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Launch Jupyter

```bash
jupyter notebook
```

Open:

```text
quantumteleportation.ipynb
```

and run the notebook from beginning to end.

---

## Assumptions

The current experiment uses an idealized quantum system.

The simulation does not currently model:

* Gate errors
* Decoherence
* Measurement errors
* Qubit relaxation
* Qubit dephasing
* Channel noise
* Hardware imperfections

Therefore, the results represent an ideal theoretical simulation rather than the performance of a physical quantum device.

---

## Future Work

Possible extensions of the project include:

* Testing arbitrary single-qubit states
* Implementing the standard measurement-based teleportation protocol
* Introducing depolarizing noise
* Studying bit-flip and phase-flip errors
* Modeling imperfect quantum gates
* Analyzing teleportation fidelity as a function of noise strength
* Comparing ideal simulation with noisy simulation
* Running the protocol on real quantum hardware
* Studying teleportation as a primitive for larger quantum communication and networking systems

---

## Author

**Boumendjel Manar**

M.Sc. Quantum Computing
Computer Science · Quantum Communication · Quantum Networking

---

## Topics

`quantum-computing` `quantum-information` `quantum-teleportation` `qiskit` `quantum-simulation` `python`
