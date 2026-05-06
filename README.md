# Understanding ML Systems from First Principles

A personal learning project focused on understanding the mathematical and systems-level foundations of modern machine learning frameworks.

The goal is **not** to build another production deep learning framework, but to deeply understand:

- backpropagation
- automatic differentiation
- computational graphs
- optimization
- GPU execution
- JIT compilation
- tensor operations
- differentiable programming
- ML systems internals

The project progresses from pure NumPy implementations to modern frameworks such as JAX, PyTorch, MLX, and TinyGrad. In parallel, selected low-level components are implemented in C++ to build intuition for memory layout, numerical kernels, and systems-level performance.

---

# Project Goals

This repository focuses on:

1. Implementing machine learning algorithms from scratch
2. Understanding autodiff systems internally
3. Exploring GPU execution on Apple Silicon
4. Comparing execution models of modern ML frameworks
5. Building intuition for differentiable programming
6. Rebuilding selected numerical components in C++ to understand low-level execution

---

# Learning Roadmap

## Phase 0 — Mathematical Foundations

Topics:
- vectors, matrices, tensors
- gradients
- chain rule
- Jacobians
- optimization basics
- computational graphs

Tasks:
- manual differentiation
- gradient descent on toy problems
- linear regression from scratch
- logistic regression from scratch

 C++ track:
  - implement basic vector operations
  - implement dot products and matrix-vector multiplication
  - compare C++ implementations with NumPy results
  - inspect numerical precision and memory layout

Tools:
- NumPy
- matplotlib

Dataset:
- synthetic 2D datasets

---

## Phase 1 — Manual Neural Networks

Goal:
Implement neural networks entirely manually without autodiff.

Implement:
- dense layers
- activations (ReLU, sigmoid, tanh)
- softmax
- cross-entropy
- SGD
- momentum
- Adam
- minibatching
- backpropagation

Dataset:
- Fashion-MNIST

Target:
- train an MLP using only NumPy

 C++ track:
  - implement selected forward-pass operations in C++
  - implement dense-layer inference
  - compare C++ output against the NumPy implementation
  - optionally call C++ kernels from Python using `pybind11`

---

## Phase 2 — Tiny Autograd Engine

Goal:
Understand how frameworks such as PyTorch and JAX compute gradients.

Implement:
- computation graph
- reverse-mode autodiff
- tensor class
- `.backward()`
- gradient accumulation

Operations:
- addition
- multiplication
- matrix multiplication
- exponentials
- logarithms
- ReLU

Inspirations:
- micrograd
- tinygrad

Dataset:
- Fashion-MNIST

 C++ track:
  - keep graph construction and autodiff in Python initially
  - implement performance-critical tensor operations in C++ later
  - use C++ kernels as a backend for selected operations

---

## Phase 3 — JAX and Differentiable Programming

Goal:
Understand functional ML and transformed computation.

Topics:
- immutable computation
- tracing
- JIT compilation
- vectorization
- automatic differentiation

Learn:
```python
jax.grad
jax.jit
jax.vmap
jax.value_and_grad
```

Projects:
- rewrite previous MLP in JAX
- compare manual gradients vs JAX gradients
- benchmark JIT vs non-JIT execution

Dataset:
- Fashion-MNIST

---

## Phase 4 — Convolutions and Vision

Goal:
Understand image-processing pipelines and CNNs.

Implement:
- 2D convolution
- pooling
- padding
- strides
- channel operations

Then:
- small CNNs

Datasets:
- MNIST
- CIFAR-10

---

## Phase 5 — GPU and ML Systems

Goal:
Understand execution below high-level frameworks.

Topics:
- kernels
- tensor memory layouts
- parallelism
- batching
- unified memory
- GPU execution
- device synchronization

Focus:
- Apple Metal
- PyTorch MPS
- MLX
- TinyGrad backends

Experiments:
- CPU vs GPU benchmarks
- memory bottlenecks
- profiling
- scaling with batch size

 C++ track:
  - benchmark C++ kernels against NumPy
  - study row-major memory layout
  - implement naive matrix multiplication
  - optionally compare naive C++, optimized C++, BLAS, and GPU-backed operations

---

## Phase 6 — Framework Internals

Goal:
Study real framework internals.

Topics:
- autograd systems
- tracing
- graph compilation
- lazy execution
- kernel fusion
- backend abstraction

Frameworks:
- TinyGrad
- PyTorch
- JAX
- MLX

---

## Phase 7 — Advanced Topics

Possible directions:
- Neural ODEs
- PINNs
- differentiable simulation
- reinforcement learning
- graph neural networks
- sparse tensor operations
- quantization
- model compression
- federated learning

---

# Dataset Progression

```text
Synthetic 2D Data
→ Fashion-MNIST
→ CIFAR-10
→ Custom robotics/control datasets
```

---

# Technology Stack

| Stage | Tools |
|---|---|
| Foundations | NumPy |
| Low-level implementation | C++ |
| Autodiff | Custom engine |
| Functional ML | JAX |
| Practical training | PyTorch |
| Apple Silicon | MLX |
| Framework internals | TinyGrad |

---

# C++ Systems Track

In addition to the Python-based learning path, this project includes a small C++ track.

The goal is not to replace Python, NumPy, or modern ML frameworks. The goal is to understand what happens underneath high-level tensor libraries.

Planned C++ components:
  - vector operations
  - matrix-vector multiplication
  - matrix-matrix multiplication
  - activation functions
  - dense-layer inference
  - small tensor and matrix abstractions without hiding memory layout
  - simple loss functions
  - selected benchmark kernels

Possible later extensions:
  - Python bindings via `pybind11`
  - comparison against NumPy and BLAS
  - memory-layout experiments
  - basic SIMD exploration
  - Metal/GPU comparison on Apple Silicon

---

# Key Principle

The objective is not API familiarity.

The objective is understanding:

```text
implement
→ break
→ debug
→ profile
→ optimize
→ compare
```

---

# References

- Andrej Karpathy — Micrograd / Neural Networks
- TinyGrad
- JAX documentation
- PyTorch internals
- MLX documentation
- Stanford CS231n
- Deep Learning by Goodfellow et al.