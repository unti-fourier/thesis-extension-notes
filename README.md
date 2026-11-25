# Thesis extension research notes

**Work in progress.** These research notes document work toward possible future papers. They are not submissions, peer-reviewed publications, or entries for a CV, publication list, or researcher profile.

| Direction | Note | Status |
| --- | --- | --- |
| 1 | [Type (M) coefficients and the Bochner tensor identification](01-type-m-bochner-tensor.md) | Exact row completion and a conditional tensor-composition theorem checked in Lean; full import-level assembly remains unverified. |
| 2 | [A measurable Reiter gap and a compact metrizable factor](02-measurable-reiter-gap.md) | Common measurable lower bound checked in Lean; factor argument checked in writing; Hochschild nonvanishing not covered. |
| 2 | [An absolute degree-two witness](02-absolute-hochschild-degree-two.md) | Written-checked characterization for countable discrete actions with a norm-one witness; not fully formalized. |
| 3 | [Real row-norm convolution completion](03-real-row-convolution-completion.md) | Real Banach algebra identification checked in Lean; complex and amenability theorems not covered. |
| 3 | [Complex row-norm convolution completion](03-complex-row-convolution-completion.md) | Exact complex norm and product checked in Lean; amenability theorem not covered. |
| 3 | [A single innerness criterion for Reiter nets](03-inner-derivation-reiter-net.md) | Both directions for the specified derivation verified in Lean in the stated second-countable setting. |
| 4 | [Sharp implementer bounds](04-sharp-implementer-bounds.md) | Sharp bounds 2 and 1 under the stated coefficient hypothesis, with independent written audit; full theorem not formalized. |
| 5 | [Sharp Reiter radius profile of a free group boundary](05-free-group-boundary-radius-profile.md) | Exact range-only value 2/(R+1), verified in writing; full I-defect not covered. |
| 6 | [Symmetric local probability kernels](06-symmetric-local-haar-kernels.md) | Pair-groupoid and general compact-unit Haar kernel existence checked in Lean. |
| 6 | [Innerness and Reiter fields for étale groupoids](06-etale-innerness-reiter.md) | Written-checked equivalence for a specified derivation with compact units; not fully formalized. |
| 6 | [A Johnson-type criterion for Hausdorff étale groupoids](06-etale-essential-core.md) | All derivations with right type (M) on the essential core, for any full continuous left Haar system; written proof, not formalized. |
| 6 | [Uniform innerness for profinite central extensions](06-profinite-central-extensions.md) | Written-checked equivalence in a non-étale class, including noncompact unit spaces, via finite corners and the quotient witness; not formalized. |
| 7 | [Uniformly bounded stabilizers and matrix reconstruction](07-uniformly-bounded-stabilizers.md) | Written proof independently checked; no Lean verification or priority claim. |
| 7 | [Right-ℓ¹ coefficients and the fixed-set quotient](07-fixed-set-quotient.md) | Written-checked annihilator formula for full and reduced crossed products; contrasts with the row-norm algebra. |

The stabilizer note proves a comparison for compact Hausdorff actions with uniformly bounded finite stabilizers, without requiring finitely many stabilizer elements or conjugacy classes. It separates the sharp matrix reconstruction constant from the bound for the inverse cohomological comparison.
