---
title: "Reading Griffith's Introduction to Electrodynamics, 4th Edition"
categories: Reading Physics
tags: electrodynamics
math: true
---

This post contains some notes on [David J. Griffiths](https://www.reed.edu/physics/faculty/griffiths/)' [*Introduction to Electrodynamics*, 4th Edition](), which was published in 2017.

{% include toc.html %}

## Chapter 1. Vector Analysis
### 1.1 Vector Algebra
#### 1.1.1 Vector Operations

The *distributive* laws of both dot product and cross product are not easy to see.

I will use the *orthogonal bases* technique to prove the distributive laws. Suppose we have three orthogonal bases $\hat{e}_1$, $\hat{e}_2$, and $\hat{e}_3$. First, we prove the distributive laws is true for them. The proof uses some Euclidean geometry knowledge but still trivial.

Now, it's time to prove general cases:

- Proving $\mathbf{A}\cdot(\mathbf{B} + \mathbf{C}) = \mathbf{A}\cdot\mathbf{B} + \mathbf{A}\cdot\mathbf{C}$.

    Suppose $\mathbf{A}=\sum A_i \hat{e}_i$, $\mathbf{B}=\sum B_i \hat{e}_i$, and $\mathbf{C}=\sum C_i \hat{e}_i$, then we have

    $$
    \begin{align}
    \mathbf{A}\cdot(\mathbf{B} + \mathbf{C}) &= \sum A_i \hat{e}_i \cdot \sum (B_i + C_i) \hat{e}_i \\
                                             &= \sum A_i(B_i + C_i) \\
                                             &= \sum A_i B_i + \sum A_i C_i \\
                                             &= \sum A_i B_i \hat{e}_i \cdot \hat{e}_i + \sum A_i C_i \hat{e}_i \cdot \hat{e}_i \\
                                             &= \mathbf{A}\cdot\mathbf{B} + \mathbf{A}\cdot\mathbf{C} \\
    \end{align}
    $$

- Proving $\mathbf{A}\times(\mathbf{B} + \mathbf{C}) = \mathbf{A}\times\mathbf{B} + \mathbf{A}\times\mathbf{C}$.

    Again, we suppose $\mathbf{A}=\sum A_i \hat{e}_i$, $\mathbf{B}=\sum B_i \hat{e}_i$, and $\mathbf{C}=\sum C_i \hat{e}_i$, then we have

    $$
    \begin{align}
    \mathbf{A}\times(\mathbf{B} + \mathbf{C}) &= \sum A_i \hat{e}_i \times \sum (B_i + C_i) \hat{e}_i \\
                                              &= \sum A_i(B_j + C_j) \hat{e}_i \times \hat{e}_j \\
                                              &= \sum A_i B_j\hat{e}_i \times \hat{e}_j + \sum A_i C_j\hat{e}_i \times \hat{e}_j \\
                                              &= \mathbf{A}\times\mathbf{B} + \mathbf{A}\times\mathbf{C} \\
    \end{align}
    $$

Pay attention to that the proof process doesn't assume the dimensions of the vector space. That means if we can prove the distributive laws of orthogonal bases of any dimension vector space, the general distributive laws are also held.

#### 1.1.2 Vector Algebra: Component Form
#### 1.1.3 Triple Products
#### 1.1.4 Position, Displacement, and Separation Vectors
#### 1.1.5 How Vectors Transform
### 1.2 Differential Calculus
#### 1.2.1 “Ordinary” Derivatives
#### 1.2.2 Gradient
#### 1.2.3 The Del Operator
#### 1.2.4 The Divergence
#### 1.2.5 The Curl
#### 1.2.6 Product Rules
#### 1.2.7 Second Derivatives
### 1.3 Integral Calculus
#### 1.3.1 Line, Surface, and Volume Integrals
#### 1.3.2 The Fundamental Theorem of Calculus
#### 1.3.3 The Fundamental Theorem for Gradients
#### 1.3.4 The Fundamental Theorem for Divergences
#### 1.3.5 The Fundamental Theorem for Curls
#### 1.3.6 Integration by Parts
### 1.4 Curvilinear Coordinates
#### 1.4.1 Spherical Coordinates
#### 1.4.2 Cylindrical Coordinates
### 1.5 The Dirac Delta Function
#### 1.5.1 The Divergence of $\hat{r}/r^{2}$ 
#### 1.5.2 The One-Dimensional Dirac Delta Function
#### 1.5.3 The Three-Dimensional Delta Function
### 1.6 The Theory of Vector Fields
#### 1.6.1 The Helmholtz Theorem
#### 1.6.2 Potentials

## Chapter 2. Electrostatics
### 2.1 The Electric Field
#### 2.1.1 Introduction
#### 2.1.2 Coulomb’s Law
#### 2.1.3 The Electric Field
#### 2.1.4 Continuous Charge Distributions
### 2.2 Divergence and Curl of Electrostatic Fields
#### 2.2.1 Field Lines, Flux, and Gauss’s Law
#### 2.2.2 The Divergence of E
#### 2.2.3 Applications of Gauss’s Law
#### 2.2.4 The Curl of E
### 2.3 Electric Potential
#### 2.3.1 Introduction to Potential
#### 2.3.2 Comments on Potential
#### 2.3.3 Poisson’s Equation and Laplace’s Equation
#### 2.3.4 The Potential of a Localized Charge Distribution
#### 2.3.5 Boundary Conditions
### 2.4 Work and Energy in Electrostatics
#### 2.4.1 The Work It Takes to Move a Charge
#### 2.4.2 The Energy of a Point Charge Distribution
#### 2.4.3 The Energy of a Continuous Charge Distribution
#### 2.4.4 Comments on Electrostatic Energy
### 2.5 Conductors
#### 2.5.1 Basic Properties
#### 2.5.2 Induced Charges
#### 2.5.3 Surface Charge and the Force on a Conductor
#### 2.5.4 Capacitors

## Chapter 3. Potentials
### 3.1 Laplace’s Equation
#### 3.1.1 Introduction
#### 3.1.2 Laplace’s Equation in One Dimension
#### 3.1.3 Laplace’s Equation in Two Dimensions
#### 3.1.4 Laplace’s Equation in Three Dimensions
#### 3.1.5 Boundary Conditions and Uniqueness Theorems
#### 3.1.6 Conductors and the Second Uniqueness Theorem
### 3.2 The Method of Images
#### 3.2.1 The Classic Image Problem
#### 3.2.2 Induced Surface Charge
#### 3.2.3 Force and Energy
#### 3.2.4 Other Image Problems
### 3.3 Separation of Variables
#### 3.3.1 Cartesian Coordinates
#### 3.3.2 Spherical Coordinates
### 3.4 Multipole Expansion
#### 3.4.1 Approximate Potentials at Large Distances
#### 3.4.2 The Monopole and Dipole Terms
#### 3.4.3 Origin of Coordinates in Multipole Expansions
#### 3.4.4 The Electric Field of a Dipole

## Chapter 4. Electric Fields in Matter
### 4.1 Polarization
#### 4.1.1 Dielectrics
#### 4.1.2 Induced Dipoles
#### 4.1.3 Alignment of Polar Molecules
#### 4.1.4 Polarization
### 4.2 The Field of a Polarized Object
#### 4.2.1 Bound Charges
#### 4.2.2 Physical Interpretation of Bound Charges
#### 4.2.3 The Field Inside a Dielectric
### 4.3 The Electric Displacement
#### 4.3.1 Gauss’s Law in the Presence of Dielectrics
#### 4.3.2 A Deceptive Parallel
#### 4.3.3 Boundary Conditions
### 4.4 Linear Dielectrics
#### 4.4.1 Susceptibility, Permittivity, Dielectric Constant
#### 4.4.2 Boundary Value Problems with Linear Dielectrics
#### 4.4.3 Energy in Dielectric Systems
#### 4.4.4 Forces on Dielectrics

## Chapter 5. Magnetostatics
### 5.1 The Lorentz Force Law
#### 5.1.1 Magnetic Fields
#### 5.1.2 Magnetic Forces
#### 5.1.3 Currents
### 5.2 The Biot-Savart Law
#### 5.2.1 Steady Currents
#### 5.2.2 The Magnetic Field of a Steady Current
### 5.3 The Divergence and Curl of B
#### 5.3.1 Straight-Line Currents
#### 5.3.2 The Divergence and Curl of B
#### 5.3.3 Ampère’s Law
#### 5.3.4 Comparison of Magnetostatics and Electrostatics
### 5.4 Magnetic Vector Potential
#### 5.4.1 The Vector Potential
#### 5.4.2 Boundary Conditions
#### 5.4.3 Multipole Expansion of the Vector Potential

## Chapter 6. Magnetic Fields in Matter
### 6.1 Magnetization
#### 6.1.1 Diamagnets, Paramagnets, Ferromagnets
#### 6.1.2 Torques and Forces on Magnetic Dipoles
#### 6.1.3 Effect of a Magnetic Field on Atomic Orbits
#### 6.1.4 Magnetization
### 6.2 The Field of a Magnetized Object
#### 6.2.1 Bound Currents
#### 6.2.2 Physical Interpretation of Bound Currents
#### 6.2.3 The Magnetic Field Inside Matter
### 6.3 The Auxiliary Field H
#### 6.3.1 Ampère’s Law in Magnetized Materials
#### 6.3.2 A Deceptive Parallel
#### 6.3.3 Boundary Conditions
### 6.4 Linear and Nonlinear Media
#### 6.4.1 Magnetic Susceptibility and Permeability
#### 6.4.2 Ferromagnetism

## Chapter 7. Electrodynamics
### 7.1 Electromotive Force
#### 7.1.1 Ohm’s Law
#### 7.1.2 Electromotive Force
#### 7.1.3 Motional emf
### 7.2 Electromagnetic Induction
#### 7.2.1 Faraday’s Law
#### 7.2.2 The Induced Electric Field
#### 7.2.3 Inductance
#### 7.2.4 Energy in Magnetic Fields
### 7.3 Maxwell’s Equations
#### 7.3.1 Electrodynamics Before Maxwell
#### 7.3.2 How Maxwell Fixed Ampère’s Law
#### 7.3.3 Maxwell’s Equations
#### 7.3.4 Magnetic Charge
#### 7.3.5 Maxwell’s Equations in Matter
#### 7.3.6 Boundary Conditions

## Chapter 8. Conservation Laws
### 8.1 Charge and Energy
#### 8.1.1 The Continuity Equation
#### 8.1.2 Poynting’s Theorem
### 8.2 Momentum
#### 8.2.1 Newton’s Third Law in Electrodynamics
#### 8.2.2 Maxwell’s Stress Tensor
#### 8.2.3 Conservation of Momentum
#### 8.2.4 Angular Momentum
### 8.3 Magnetic Forces Do No Work

## Chapter 9. Electromagnetic Waves
### 9.1 Waves in One Dimension
#### 9.1.1 The Wave Equation
#### 9.1.2 Sinusoidal Waves
#### 9.1.3 Boundary Conditions: Reflection and Transmission
#### 9.1.4 Polarization
### 9.2 Electromagnetic Waves in Vacuum
#### 9.2.1 The Wave Equation for E and B
#### 9.2.2 Monochromatic Plane Waves
#### 9.2.3 Energy and Momentum in Electromagnetic Waves
### 9.3 Electromagnetic Waves in Matter
#### 9.3.1 Propagation in Linear Media
#### 9.3.2 Reflection and Transmission at Normal Incidence
#### 9.3.3 Reflection and Transmission at Oblique Incidence
### 9.4 Absorption and Dispersion
#### 9.4.1 Electromagnetic Waves in Conductors
#### 9.4.2 Reflection at a Conducting Surface
#### 9.4.3 The Frequency Dependence of Permittivity
### 9.5 Guided Waves
#### 9.5.1 Wave Guides
#### 9.5.2 TE Waves in a Rectangular Wave Guide
#### 9.5.3 The Coaxial Transmission Line

## Chapter 10. Potentials and Fields
### 10.1 The Potential Formulation
#### 10.1.1 Scalar and Vector Potentials
#### 10.1.2 Gauge Transformations
#### 10.1.3 Coulomb Gauge and Lorenz Gauge
#### 10.1.4 Lorentz Force Law in Potential Form
### 10.2 Continuous Distributions
#### 10.2.1 Retarded Potentials
#### 10.2.2 Jefimenko’s Equations
### 10.3 Point Charges
#### 10.3.1 Liénard-Wiechert Potentials
#### 10.3.2 The Fields of a Moving Point Charge

## Chapter 11. Radiation
### 11.1 Dipole Radiation
#### 11.1.1 What is Radiation?
#### 11.1.2 Electric Dipole Radiation
#### 11.1.3 Magnetic Dipole Radiation
#### 11.1.4 Radiation from an Arbitrary Source
### 11.2 Point Charges
#### 11.2.1 Power Radiated by a Point Charge
#### 11.2.2 Radiation Reaction
#### 11.2.3 The Mechanism Responsible for the Radiation Reaction

## Chapter 12. Electrodynamics and Relativity
### 12.1 The Special Theory of Relativity
#### 12.1.1 Einstein’s Postulates
#### 12.1.2 The Geometry of Relativity
#### 12.1.3 The Lorentz Transformations
#### 12.1.4 The Structure of Spacetime
### 12.2 Relativistic Mechanics
#### 12.2.1 Proper Time and Proper Velocity
#### 12.2.2 Relativistic Energy and Momentum
#### 12.2.3 Relativistic Kinematics
#### 12.2.4 Relativistic Dynamics
### 12.3 Relativistic Electrodynamics
#### 12.3.1 Magnetism as a Relativistic Phenomenon
#### 12.3.2 How the Fields Transform
#### 12.3.3 The Field Tensor
#### 12.3.4 Electrodynamics in Tensor Notation
#### 12.3.5 Relativistic Potentials

## A. Vector Calculus in Curvilinear Coordinates
### A.1 Introduction
### A.2 Notation
### A.3 Gradient
### A.4 Divergence
### A.5 Curl
### A.6 Laplacian

## B. The Helmholtz Theorem
## C. Units
