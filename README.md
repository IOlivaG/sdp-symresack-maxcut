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

## Contributing

Contributions are welcome. Please open an issue or submit a pull request for suggestions, improvements, or bug fixes. You can also reach out via [Isaac Oliva-González's homepage](https://iolivag.github.io).

## License

This project is licensed under the MIT License.
