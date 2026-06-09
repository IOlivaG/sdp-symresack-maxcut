# SDP-Symresack: Symmetry Handling in Semidefinite Programming

This repository explores whether the idea behind **symresacks** (Hojny, 2020), lexicographic ordering of symmetric variables, can be adapted from binary integer programming to semidefinite programming. Using the maximum cut SDP relaxation on the complete graph $K_3$ as a minimal working example, the notebook walks through three approaches to symmetry handling: no handling, Gatermann-Parrilo group averaging, and lexicographic ordering via FD-inequalities. All analysis is carried out analytically, without external solvers, so that every step can be verified by hand.

## Repository Structure
```
sdp-symresack-maxcut/
├── README.md
└── sdp_symresack_maxcut_K3.ipynb
```

## Notebook Overview

**`sdp_symresack_maxcut_K3.ipynb`** is organized into the following sections:

- **MaxCut SDP Relaxation on $K_3$:** presents the Goemans-Williamson semidefinite relaxation, writes the $3 \times 3$ PSD matrix with variables $a, b, c$, derives PSD conditions via principal minors, characterizes $S_3$ symmetry by conjugation, and identifies the optimal MaxCut solution.
- **GP1 Averaging:** applies the Gatermann-Parrilo fixed-point restriction, forcing $a = b = c$, and shows analytically that it loses optimality (dual bound 2.25 > 2).
- **FD-Inequalities (SDP-Symresack):** introduces lexicographic ordering constraints ($a \ge b$) that select a canonical representative per orbit, preserving optimality while breaking symmetry. Compares all three approaches and discusses limitations and future work directions.

## References

- [1] Goemans, M. X., & Williamson, D. P. (1995). Improved approximation algorithms for maximum cut and satisfiability problems using semidefinite programming. *Journal of the ACM*, 42(6), 1115–1145.
- [2] Hojny, C., & Pfetsch, M. E. (2019). Polytopes associated with symmetry handling. *Mathematical Programming*, 175, 197–240.
- [3] Hojny, C. (2020). Packing, partitioning, and covering symresacks. *Discrete Applied Mathematics*, 283, 689–717.
- [4] Gatermann, K., & Parrilo, P. A. (2004). Symmetry groups, semidefinite programs, and sums of squares. *Journal of Pure and Applied Algebra*, 192(1–3), 95–128.
- [5] Margot, F. (2010). Symmetry in integer linear programming. In *50 Years of Integer Programming 1958–2008* (pp. 647–686). Springer.
- [6] Kobert, P., & Scheiderer, C. (2020). Spectrahedral representation of polar orbitopes. arXiv:2010.02045.

This is a minimal, self-contained exploration. There are no new theorems or computational experiments here, just one worked example that makes the core idea concrete.

## License

This project is licensed under the MIT License.
