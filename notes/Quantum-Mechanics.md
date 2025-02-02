---
title: "Quantum Mechanics"
description: "Basic QM Notes"
publishDate: "3 Feb 2025"
tags: ["Quantum Mechanics", "Notes"]
---

This note has some important portions of introductory Quantum Physics course. Concepts are mostly taken from three books namely:
- Quantum Mechanics Concepts and Applications - Zettili.
- Quantum Physics - H C Verma
- Introduction to Quantum Mechanics - D J Griffiths

---
## A Few basics

### Postulates

1. $\ket{\psi (t)}$ contains all needed information about the system.
2. Physically measurable quantities or observables are all Hermitian operators.
3. $\hat{A}\ket{\psi} = a_{n} \ket{\psi}$
   where $a_n = \ket{\psi}$
4. Probability:
$$P_n = \frac{|\braket{\psi|\psi}|^2}{\braket{\psi}} = \frac{|a_n|^2}{\braket{\psi|\psi}}$$

5. Time evolution : $i\hbar\left(\frac{\partial \ket{\psi (t)}}{\partial t} \right) = \hat{H} \ket{\psi (t)}$


### Observables and operators

- Hamiltonian $H = \frac{\vec{p}^2}{2m} + V(\vec{r}, t)$
- $\hat{H} = \frac{-\hbar^2}{2m} \nabla^2 + V(\vec{R}, t)$
- Angular momnetum: $\hat{\vec{L}} = -i\hbar (\hat{\vec{R}} \times \vec\nabla)$

### Uncertainty Relation
  $\sigma_A\sigma_B \geq \frac{1}{2}|\braket{[\hat A, \hat B]}|$;
where, $\sigma_A = |sqrt{\braket{\hat A^2}-\braket{\hat A}^2}$

- proof:
$\sigma_A ^2 = \braket{(\hat A - \braket{\hat A})\psi|(\hat A - \braket{\hat A})\psi} = \braket{f|f}$

Similarly,

$\sigma_B ^2 = \braket{(\hat B - \braket{\hat B})\psi|(\hat B - \braket{\hat B})\psi} = \braket{g|g}$
$\braket{f|g} = \braket{(\hat A - \braket{\hat A})\psi|(\hat B - \braket{\hat B})\psi}
\\
= \braket{\hat A \hat B} - \braket{\hat B} \braket{\hat A}$

$\braket{g|f} = \braket{(\hat A - \braket{\hat A})\psi|(\hat B - \braket{\hat B})\psi}
\\
= \braket{\hat B \hat A} - \braket{\hat B} \braket{\hat A}$

 but also, 
$$\sigma_A^2\sigma_B^2 = \braket{f|f} \braket{g|g} \geq \overbrace{ |\braket{f|g}|^2 \geq \left(\frac{1}{2i} [ \braket{f|g} - \braket{g|f}] \right)^2}^{\because |z|^2 \geq \left[\frac{1}{2i}(z-z^*)\right]}$$

$\therefore \sigma_A \sigma_B \geq  \frac{1}{2}|\braket{[\hat A, \hat B]}|$

### Conservation of Probability

- Expression:

$$\frac{\partial \rho (\vec{r}, t)}{\partial t} + \vec{\nabla}\cdot \vec J = 0$$

where
$$\rho = \Psi^*\Psi \text{   .   (Probability density)}$$
and, $$\vec J = i\hbar(\Psi\vec{\nabla}\Psi^* - \Psi^* \vec{\nabla}\Psi) \text{ .  (Probability current density)}$$

---

## Quantum Mechanics - 1D Problems

### Free Particle