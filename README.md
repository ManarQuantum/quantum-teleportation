# Quantum Teleportation using Qiskit

A computational implementation and verification of the quantum teleportation protocol using Qiskit.

This project demonstrates how an unknown quantum state can be transferred from one qubit to another using quantum entanglement and coherent quantum operations. The implementation uses ideal statevector simulation to verify that the receiver's final state matches the state prepared on the sender's qubit.

## Overview

Quantum teleportation is a fundamental protocol in quantum information that allows an unknown quantum state to be transferred between two parties using:

* A shared entangled Bell pair
* Local quantum operations
* Classical communication in the standard measurement-based protocol

The quantum state itself is not physically transmitted between the sender and receiver. Instead, entanglement and the appropriate quantum operations allow the receiver to reconstruct the original state.

This project implements a coherent, measurement-free formulation of the teleportation circuit for computational verification using statevector simulation.

## Protocol

The teleportation circuit contains three qubits:

* **Qubit 0:** state to be teleported
* **Qubit 1:** sender's half of the entangled Bell pair
* **Qubit 2:** receiver's half of the entangled Bell pair

The main steps are:

1. Prepare the input state on qubit 0.
2. Create a Bell pair between qubits 1 and 2.
3. Apply the Bell-basis transformation to qubits 0 and 1.
4. Apply coherent correction operations to qubit 2.
5. Simulate the final quantum state.
6. Extract the receiver's reduced density matrix.
7. Calculate the fidelity between the original and teleported states.

## Implementation

The protocol is implemented using:

* Python
* Qiskit
* NumPy
* Matplotlib

The ideal statevector simulation allows the final state to be examined directly and provides a numerical verification of teleportation fidelity.

## Experiments

The project evaluates teleportation for several input states:

| Input state | Description |                                    |
| ----------- | ----------- | ---------------------------------- |
| `           | 0⟩`         | Computational basis state          |
| `           | 1⟩`         | Computational basis state          |
| `           | +⟩`         | Equal superposition state          |
| `           | −⟩`         | Relative-phase superposition state |

For the ideal noiseless simulation, the receiver's state should reproduce the input state with fidelity numerically equal to 1, up to floating-point precision.

## Fidelity

The teleportation fidelity is calculated using:

$$
F(\rho,\sigma)
$$

where the original input state is compared with the reduced density matrix of the receiver's qubit.

For an ideal teleportation process:

$$
F \approx 1
$$

A fidelity of 1 indicates that the receiver's quantum state is identical to the original state.

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

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/quantum-teleportation.git
cd quantum-teleportation
```

Create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter notebook
```

Open:

```text
quantumteleportation.ipynb
```

## Future Improvements

Possible extensions include:

* Testing arbitrary single-qubit states
* Introducing quantum noise
* Studying the effect of depolarizing and bit-flip noise
* Comparing teleportation fidelity under different noise levels
* Investigating circuit depth and gate requirements
* Running the protocol on real quantum hardware

## Author

**Boumendjel Manar**

M.Sc. Quantum Computing
Computer Science · Quantum Communication · Quantum Networking

## Topics

`quantum-computing` `quantum-information` `quantum-teleportation` `qiskit` `quantum-circuits` `quantum-simulation`

