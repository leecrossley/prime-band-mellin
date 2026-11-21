# The phase of the Mellin transform of a compact prime weight

For every real $b>1$, $H_b(s)$ is nonzero for $0<\Re s<1$. On the critical line it is $b^s$ times a strictly positive real factor.

Let $W_b(t)$ equal $b(1-1/t)$ for $1<t\le b$, $b^2/t-1$ for $b<t<b^2$, and zero elsewhere. Define $P_b(y)=\sum_{p\ {\rm prime}}(\log p)W_b(p/y)$ for $y>0$, with natural logarithms. Its expected main term is $b(b-1)y\log b$. Write $B_b=2\sqrt b(\sqrt b-1)^2$ for the asymptotic prime-square contribution, $D_b(y)=b(b-1)y\log b-P_b(y)$ for the deficit and $H_b(s)=(b^s-1)(b^s-b)/(s(s-1))$ for the Mellin transform. For $\rho=1/2+i\tau$ the identity $b/b^\rho=\overline{b^\rho}$ gives

$$
 H_b(\rho)=e^{i\tau\log b}h_\rho,\qquad
 h_\rho=\frac{\sqrt b\thinspace(b+1-2\sqrt b\cos(\tau\log b))}{1/4+\tau^2}>0.
$$

Integrating the two pieces against $t^{s-1}dt$ yields the displayed rational expression in $b^s$. On the open strip the modulus of $b^s$ lies strictly between $1$ and $b$, so neither numerator factor vanishes. For $\Re s=1/2$, put $z=b^s$, so $z\bar z=b$ and $s(s-1)=-|s|^2$. Consequently $(z-1)(z-b)=-z(b+1-2\Re z)$. The real multiplier of $z$ is positive since $b+1-2\Re z\ge(\sqrt b-1)^2>0$.

## Verification

The two assertions about the displayed expression are kernel-checked against Mathlib. The identification with the Mellin transform follows by integrating the two elementary pieces. The Lean statements are made away from the removable singularities at 0 and 1.

The recorded run used Lean 4.33.1 on arm64 macOS. It freshly elaborated this repository’s modules, used compiled dependencies from the pinned sources, replayed each local module with `leanchecker`, and inspected the named declarations’ axioms. The receipt records the module counts and axiom lists. Compiler commit `819816b2e0a3bf405af45ae5c7af2491d8f5bee6` and Mathlib commit `0df444a360eaa60ab8c11dca51a86af692955474` fix the environment. [Lean release](https://github.com/leanprover/lean4/releases/tag/v4.33.1) · [Mathlib revision](https://github.com/leanprover-community/mathlib4/tree/0df444a360eaa60ab8c11dca51a86af692955474)

This result imports Mathlib directly. When reusing an existing installation, supply an empty directory as the source argument.

For a fresh build on x86-64 Linux with Git, curl, tar, zstd and Python 3.9 or later, run

```sh
bash verify-linux.sh
```

With the pinned toolchain and Mathlib cache already installed, use

```sh
cd /path/to/pinned/mathlib4
lake env python3 /path/to/repository/verify.py /path/to/empty/directory /path/to/build
```

The build directory can begin empty. Reusing a dependency cache requires the same sources and compiler. A successful run ends with the kernel and axiom summary recorded below.

The Linux entry point checks the SHA-256 manifest before downloading the pinned dependencies and compares the resulting kernel and axiom summary with the recorded run.

[Recorded verification output](evidence/check.txt) · [SHA-256 manifest](SHA256SUMS) · [Tagged publication](https://github.com/leecrossley/prime-band-mellin/releases/tag/v1.0.2)

## Related result

[Derivation of the general extremal formula](https://github.com/leecrossley/prime-band-extrema/tree/v1.0.1)
