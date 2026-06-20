# SDP-Symresack: Lexicographic Symmetry Breaking for Semidefinite Programs

This repository presents **SDP-symresacks**: linear constraints that impose a lexicographic ordering on the entries of a symmetric positive semidefinite matrix to select a canonical representative from each symmetry orbit. These constraints, called **FD-inequalities** (first-different inequalities), provably preserve the optimal value of any SDP whose feasible set and objective are invariant under a single permutation acting by conjugation. The proof is elementary: every orbit is finite, so it contains a lexicographically maximal element, which by construction satisfies the FD-inequalities and achieves the same objective value as any other orbit member.

Using the maximum cut SDP relaxation on the complete graph $K_3$ as a minimal working example, the notebook walks through three approaches to symmetry handling: no handling, Gatermann-Parrilo group averaging (GP1), and lexicographic ordering via FD-inequalities. At the pure SDP level, all three approaches give the same bound ($9/4$); the difference between GP1 and FD-inequalities appears only when integer feasibility is required. All analysis is carried out analytically, without external solvers.

## Repository Structure

```
sdp-symresack/
├── README.md
└── sdp_symresack_maxcut.ipynb
```

## Notebook Overview

**`sdp_symresack_maxcut.ipynb`** covers:

- **Semidefinite Programs and Symmetry Groups:** defines the SDP standard form, the conjugation action of a permutation group, and the symmetry group of an SDP.
- **Vectorization, Lexicographic Order, and FD-Inequalities:** introduces the upper-triangle vectorization, the first-different (FD) position, and derives the FD-inequalities $X_{12} \ge X_{13}$, $X_{12} \ge X_{23}$ for $C_3 = \langle (1\;2\;3) \rangle$.
- **Main Theorem:** proves that FD-inequalities preserve the SDP optimum ($\max_\mathcal{F} = \max_{\mathcal{F}_G}$) with a short three-step argument.
- **Comparison with GP Averaging:** explains why GP1 is safe for pure SDPs but fails for integer feasibility, with a comparison table of both methods.
- **Illustration on $K_3$:** computes the SDP optimal value $9/4$, verifies that both FD-inequalities and GP1 recover it, and notes that all three approaches give the same bound at the pure SDP level.
- **Extensions:** discusses cyclic groups $\mathbb{Z}_k$, signed permutation groups $B_n$, orbit-wise application, and how intersecting symresacks yields the symretope for general $S_n$.

## Contributing

Contributions are welcome. Please open an issue or submit a pull request for suggestions, improvements, or corrections. You can also reach out via [Isaac Oliva-González's homepage](https://iolivag.github.io).

## License

MIT License.
