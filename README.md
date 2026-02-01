# Mass-Spring-Damper-Simulation-Euler-vs-Heun-vs-odeint-
Python simulation of a coupled mass–spring–damper system under an impulse input, comparing Euler and Heun (RK2) methods against odeint, with damping-ratio estimation and error analysis.
This repository contains a Python script that numerically simulates a coupled mechanical mass–spring–damper system.
The system is excited by a rectangular, unit-impulse-like input force F2(t) (1 second duration), and the resulting displacement response p2(t) is computed and analysed.

Implemented Features
Numerical ODE Solvers

Explicit Euler method: simulate_system_euler(dt, T)

Heun’s method (second-order Runge–Kutta): simulate_system_heun(dt, T)

Reference solution using scipy.integrate.odeint for verification

Time Step and Simulation Time Justification

Chosen time step: dt = 0.05, tested over the range 0.01 ≤ dt ≤ 0.1

Total simulation time: T = 80 s, selected so all responses converge within 1% of the analytical steady-state value (y_ss = 0)

Error Analysis

Absolute error and percentage error arrays for Euler and Heun relative to the steady-state value

Final-value error reporting for both numerical methods

Percentage error vs time plot including a 1% error threshold

System Behaviour and Damping

Visual identification of an underdamped response (decaying oscillations)

Automatic damping-ratio estimation (zeta) using logarithmic decrement

Peak detection implemented with scipy.signal.find_peaks

Printed damping ratios for Euler and Heun confirming 0 < zeta < 1

Plots and Visual Outputs

p2(t) vs time for Euler and Heun (separate plots)

Combined comparison plot: Euler vs Heun vs odeint

Input force F2(t) vs time to illustrate the effect of time step on impulse shape

Percentage error vs time for both numerical methods

The script is extensively commented to justify:

The choice of time step

The total simulation time

The interpretation of system damping (underdamped, overdamped, critically damped)
