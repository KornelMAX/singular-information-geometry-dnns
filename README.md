# Overview

This repository contains the note “Unified Singular Information Geometry of Deep Neural Networks” and supporting code/experiments. Very roughly: I treat parameters and hidden activations as redundant
coordinates on the same underlying probabilistic model, and use
Fisher–Rao geometry to understand which directions actually matter.

This note is about degeneracy in deep neural networks, phrased in geometric
language. Modern networks are heavily overparameterised: many different weight
configurations, and many different internal representations, implement exactly
the same input–output behaviour. Training trajectories also appear to explore
only a thin subset of parameter space. The aim here is to make these phenomena
precise by treating parameters and representations as redundant coordinates on a
single space of probability distributions.

The starting point is the task itself. We equip the space $\mathcal{S}$ of
output distributions with the canonical information-geometric metric,
Fisher–Rao. A given network and likelihood model then define smooth maps
$\Theta \to \mathcal{S}$ and $M_\ell \to \mathcal{S}$, from parameter space
$\Theta$ and from each layer representation manifold $M_\ell$ into (strata of)
$\mathcal{S}$. Pulling back the Fisher–Rao metric along these maps endows both
$\Theta$ and the $M_\ell$ with *degenerate* Riemannian metrics: directions that
do not change the task-induced output distribution have zero length.

These null directions are the deep-learning analogue of gauge directions or flat
directions in a potential: infinitesimal moves in parameter or representation
space that leave the realised probabilistic map unchanged. Their integral
manifolds form “leaves” of functionally equivalent parameters or
representations. Collapsing each leaf to a point produces a quotient space which
can be interpreted as the *effective* parameter manifold or representation
manifold seen by the task. On constant-rank regions of the relevant maps, these
quotients are smooth Riemannian manifolds; globally, as ranks jump across
activation boundaries or symmetry-related regions, they assemble into a
stratified singular geometry in the sense of singular Riemannian geometry.

In this picture, familiar objects in deep learning theory are just coordinate
expressions of the same underlying structure. The Fisher information matrix is
the matrix representation of the pullback metric on parameter space; its
eigenvalue spectrum or “effective rank” measures how many independent
task-relevant directions survive after quotienting out null directions.
Operators such as Cauchy–Green-type deformation tensors or NTK-like kernels can
be viewed as alternative probes of the same singular pullback geometry.

The framework is static: it describes the geometry of a fixed network (or a
snapshot along training). Technically, the cleanest statements are local, on
patches where the parameter-to-distribution and representation-to-distribution
maps have approximately constant rank; conceptually, the singular Riemannian
viewpoint allows one to talk about the resulting global, stratified geometry
obtained by gluing these patches. Within this setting one can pose concrete
questions: How large are the null spaces at different layers? How do their
dimensions and quotient manifolds evolve during training? How do these
degeneracies relate to phenomena such as mode connectivity, representation
collapse, or the existence of sparse subnetworks? The rest of the note develops
the formalism needed to address such questions in a unified way.

This is a research note in progress. Please feel free to read and share the link. If you’d like to reuse material, please contact me.
