# lean-eval-gleason

[![Comparator](https://github.com/zblore/lean-eval-gleason/actions/workflows/comparator.yml/badge.svg)](https://github.com/zblore/lean-eval-gleason/actions/workflows/comparator.yml)

A solution to lean-eval's `gleason_theorem_finite`, Gleason's theorem in finite dimensions as stated
by Kim Morrison in [leanprover/lean-eval](https://github.com/leanprover/lean-eval).

For a finite-dimensional complex Hilbert space of dimension at least 3, every frame function on the
orthogonal projections is P ↦ Re Tr(ρP) for a unique positive operator ρ with trace 1. The statement
in `Challenge.lean` and `Solution.lean` is lean-eval's, unchanged.

The proof comes from my [csd-lean4](https://github.com/zblore/csd-lean4) repository (commit
`4b396fa3`), where I proved Gleason's theorem for matrices on ℂᴺ following Cooke, Keane and Moran
(1985). `Submission/Gleason` holds those files, ported to lean-eval's pins. `Submission/Bridge.lean`
takes matrices in an orthonormal basis to turn lean-eval's operator statement into the matrix one.

Checks: the [Comparator workflow](.github/workflows/comparator.yml) runs lean-eval's own checker on
every push, with the same tool versions lean-eval uses. Comparator builds `Solution` in a sandbox and
confirms it proves the statement in `Challenge.lean` using only `propext`, `Classical.choice` and
`Quot.sound`. The Lean kernel and the independent nanoda kernel both accept it. lean-eval archived
this problem on 20 Aug 2026, so its server no longer takes solutions.

This isn't the first Lean proof of finite-dimensional Gleason.
[Bobart0/gleason-theorem-lean](https://github.com/Bobart0/gleason-theorem-lean) proves the same case
by the same route, and [markkasaurus/gleason-theorem-lean](https://github.com/markkasaurus/gleason-theorem-lean)
proves the separable case.

I drafted the Lean with Claude Code. Fable 5.1 and Astra reviewed the Gleason proof in csd-lean4
before I carved it out.
