# QUBE Servo 2 – Rotary Inverted Pendulum Control

A control systems laboratory project focused on modelling, identification, and full control of the **Quanser QUBE Servo 2** — a DC-motor-driven horizontal arm with a freely rotating pendulum.

The ultimate goal is to **stabilize the pendulum in its unstable upright equilibrium**, starting from the natural downward (stable) position.

---

## System Overview

The QUBE Servo 2 consists of:
- A **DC motor** that directly drives a rotating horizontal arm
- A **pendulum** attached to the arm, free to rotate in the vertical plane
- Two **rotary incremental encoders** measuring arm and pendulum angular positions

The system serves as a classic benchmark for nonlinear control and state-space design.

---

## Project Structure

```
├── Report.pdf        # Full project report
└── README.md
```

---

## Contents

### 1. System Modelling
- Derivation of the equations of motion for the arm + pendulum system (Euler-Lagrange)
- DC motor / actuator model
- Linearization around equilibrium points

### 2. System Identification & Validation
- Identification of horizontal arm and pendulum **friction coefficients**
- Identification of **cable stiffness**
- Model validation against experimental data from the real system

### 3. State Observer
- Design of a full-state observer to estimate non-measured states

### 4. Horizontal Arm Control
 Strategy Description 

 PID - Classical tuning on the linearized model 
 State-space (pole placement) - Full-state feedback with observer 

### 5. Balance Control (Unstable Equilibrium)
 Strategy  Description 

 LQR - Optimal state feedback minimizing a quadratic cost 
 Pole placement - Manual eigenvalue assignment 

Both strategies are compared and the best-performing one is selected for the final implementation.

### 6. Swing-Up Control
- **Resonance excitation**: energy pumping via periodic forcing
- **Energy-based swing-up**: Lyapunov-inspired controller that drives the pendulum energy toward the upright value
- **Lyapunov-based approach**: additional stability analysis
- Switching logic between swing-up and balance controller

---

## Tools & Environment

 MATLAB / Simulink - Modelling, simulation, control design 
 Quanser QUARC - Real-time implementation on QUBE hardware 

---

## Key Results

- Successfully identified a validated nonlinear model of the physical system
- Designed and compared multiple control strategies for arm positioning
- Achieved **stable balancing** of the pendulum in the inverted position
- Implemented a full **swing-up + balance** pipeline on the real hardware

---

## Authors

*Group project — Automation Engineering*

---

## License

This repository contains academic work shared for portfolio purposes. The report is provided for reference only.
