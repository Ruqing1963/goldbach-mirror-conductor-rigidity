# The Goldbach Mirror: Conductor Rigidity and the Static Conduit in GSp(4)

**Author:** Ruqing Chen, GUT Geoservice Inc., Montréal, QC, Canada

## Paper

This repository contains the companion code and paper for:

> R. Chen, *The Goldbach Mirror: Conductor Rigidity and the Static Conduit in GSp(4)*, Zenodo, 2026.

This is the seventh paper in the conductor rigidity series:

| # | Paper | Zenodo |
|---|-------|--------|
| 1 | Conductor Incompressibility for Frey Curves Associated to Prime Gaps | [10.5281/zenodo.18682375](https://zenodo.org/records/18682375) |
| 2 | Density Thresholds for Equidistribution in Prime-Indexed Geometric Families | [10.5281/zenodo.18682721](https://zenodo.org/records/18682721) |
| 3 | Weil Restriction Rigidity and Prime Gaps via Genus 2 Hyperelliptic Jacobians | [10.5281/zenodo.18683194](https://zenodo.org/records/18683194) |
| 4 | On Landau's Fourth Problem: Conductor Rigidity and Sato-Tate Equidistribution | [10.5281/zenodo.18683712](https://zenodo.org/records/18683712) |
| 5 | The 2-2 Coincidence: Conductor Rigidity for Primes in Arithmetic Progressions | [10.5281/zenodo.18684151](https://zenodo.org/records/18684151) |
| 6 | The Genesis of Prime Constellations: Weil Restriction on GSp(8) | [10.5281/zenodo.18684352](https://zenodo.org/records/18684352) |
| 7 | **The Goldbach Mirror** (this paper) | *forthcoming* |

## Repository Contents

```
├── README.md                       # This file
├── Goldbach_Mirror_GSp4_v3.tex     # LaTeX source
├── Goldbach_Mirror_GSp4_v3.pdf     # Compiled paper
├── goldbach_scanner_v2.py          # Goldbach Comet Geometric Scanner
└── verify_discriminant.py          # Discriminant formula verification
```

## Scripts

### goldbach_scanner_v2.py — Goldbach Comet Geometric Scanner

Verifies the Hardy-Littlewood prediction for Goldbach representations by:

1. **Sieving** primes up to a configurable limit
2. **Counting** ordered Goldbach representations G(2N) = #{(p,q) : p+q=2N, both prime}
3. **Computing** the Hardy-Littlewood prediction: G(2N) ~ 2·C₂·∏(r-1)/(r-2)·2N/(ln 2N)²
4. **Classifying** each 2N by its mod-6 orbit type (Resonant / Stable / Generic)
5. **Verifying** the discriminant formula Δ = 2¹² · p⁶ · (2N-p)⁶ · (N-p)⁴ · N⁴

The "wormhole factor" ∏_{r|N, r>2} (r-1)/(r-2) in the script corresponds precisely to the **static conduit** factor in Theorem 5.1 of the paper.

```bash
python3 goldbach_scanner_v2.py
```

**Output includes:**
- Ordered Goldbach counts vs Hardy-Littlewood predictions (ratio ≈ 1.0)
- Statistics by orbit type showing the banded structure of the Goldbach comet
- Discriminant verification for a specific example (2N=30, p=7)

### verify_discriminant.py — Independent Discriminant Verification

Verifies Theorem 3.2 (Δ = 2¹² · p⁶ · (2N-p)⁶ · (N-p)⁴ · N⁴) and Theorem 5.1(iii) (ord_r(Δ) = 4·ord_r(N)) across multiple test cases.

```bash
python3 verify_discriminant.py
```

## Key Results

The paper constructs the Goldbach-Frey curve C_{N,p} : y² = x(x²−p²)(x²−(2N−p)²) and proves:

- **Theorem 3.2:** Discriminant Δ = 2¹² · p⁶ · (2N−p)⁶ · (N−p)⁴ · N⁴, with N⁴ as a parameter-independent **static conduit**
- **Theorem 4.1:** Kani-Rosen splitting Jac(C_{N,p}) ⊗ K ~ E_p × E_p^σ over K = Q(√−1)
- **Theorem 5.1:** Uniform conductor at the static conduit: every curve in the family {C_{N,p}} sees the same local obstruction at primes dividing N

## Requirements

- Python 3.6+
- No external dependencies (uses only `math` and `time` from the standard library)

## License

This work is released under the [MIT License](https://opensource.org/licenses/MIT).
