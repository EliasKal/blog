---
layout: post
title:  "Variational characterization of eigenvalues"
date:   2016-09-28
categories: mathematics
---

*Note: These notes refer to the [Lecture Notes on Graph Partitioning, Expanders and
Spectral Methods](https://people.eecs.berkeley.edu/~luca/books/expanders-2016.pdf) by Luca Trevisan \[[1](#ref_01)\].*

Regarding Section 1.3, "Variational characterization of
eigenvalues", of Lecture 1, below is another way, maybe more 
intuitive, to get the values of the eigenvalues from the
Reyleigh quotient.

For a symmetric matrix $M \in \mathbb{R}^{n \times n}$ and a 
vector $\mathbf{x}$, the Reyleigh quotient is:

$$
R_M(\mathbf{x}) = \frac{\mathbf{x}^T M \mathbf{x}}
{\mathbf{x}^T \mathbf{x}}
$$

Let $\lambda_{\text{min}} = \lambda_1 \leq \lambda_2 \leq \ldots
\leq \lambda_n = \lambda_{\text{max}}$ be the eigenvalues of $M$
and $\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n$ the
corresponding unit length eigenvectors. The eigenvectors form 
an orthonormal basis on which every vector $\mathbf{x}$ can be 
expressed:

$$
\mathbf{x} = \sum_{i=1}^n \alpha_i \mathbf{v}_i,
$$

where $\alpha_i$ is the $i$-th coordinate of $\mathbf{x}$ in the
eigenvector basis.

The numerator of the Reyleigh quotient is:

$$
\mathbf{x}^T M \mathbf{x} =
\left( \sum_{i=1}^n \alpha_i \mathbf{v}_i \right)^T M
\left( \sum_{i=1}^n \alpha_i \mathbf{v}_i \right) = 
\sum_{i=1}^n \alpha_i^2 \mathbf{v}_i^T M \mathbf{v}_i = 
\sum_{i=1}^n \alpha_i^2 \lambda_i,
$$

where the facts that the eigenvectors are orthogonal to each
other and have a length of 1 have been used. Similarly, the
denominator of the Reyleigh quotient is:

$$
\mathbf{x}^T \mathbf{x} = \sum_{i=1}^n \alpha_i^2.
$$

The Reyleigh quotient thus becomes:

$$
R_M(\mathbf{x}) = \frac{\sum_{i=1}^n \alpha_i^2 \lambda_i}
{\sum_{i=1}^n \alpha_i^2}
$$

The above expression can be restructured in the following way:

\begin{equation}
\label{eq:rq_weighted_average}
R_M(\mathbf{x}) =
\frac{\alpha_1^2}{\sum_{i=1}^n \alpha_i^2} \lambda_1 +
\frac{\alpha_2^2}{\sum_{i=1}^n \alpha_i^2} \lambda_2 +
\ldots +
\frac{\alpha_n^2}{\sum_{i=1}^n \alpha_i^2} \lambda_n,
\end{equation}
from which it is apparent that the Reyleigh quotient is a
weighted average of the eigenvalues.

Each weight $\alpha_k^2 / \sum_{i=1}^n \alpha_i^2$ takes values
from 0 to 1 and the sum of all weights is 1. Therefore, the 
lowest value of $R_M({\mathbf{x}})$ is obtained when all the
weight is given to the smallest eigenvalue, $\lambda_1$, i.e.
when $\alpha_1 = 1$ and $\alpha_k = 0, k \neq 1$. In other words,
the minimum $R_M({\mathbf{x}})$ is obtained when $\mathbf{x}$ is
equal (up to a scaling factor) to $\mathbf{v}_1$ and then the
corresponding minimum value is $\lambda_1$. This leads to the
following way to express the smallest eigenvalue of a matrix 
$M$:

$$
\lambda_1 = \min_{\mathbf{x}} R_M(\mathbf{x}).
$$

Returning to Eq. \eqref{eq:rq_weighted_average}, if $\alpha_1$
is set to 0, then the minimum value of the Reyleigh quotient is
the second smallest eigenvalue, $\lambda_2$, which is obtained
when all weight is given to $\lambda_2$, i.e. when
$\alpha_2 = 1$ and $\alpha_k = 0, k \neq 2$. Setting $\alpha_1$
to 0 means that only the $\mathbf{x}$ vectors that are
orthogonal to $\mathbf{v}_1$ are considered. This leads to the
following expression for $\lambda_2$:

$$
\lambda_2 = \min_{\mathbf{x}: \mathbf{x} \perp \mathbf{v}_1}
R_M(\mathbf{x}).
$$

Similar expressions can be obtained for the other eigenvalues:

$$
\lambda_3 = \min_{\mathbf{x}: \mathbf{x} \perp 
\mathbf{v}_1, \mathbf{x} \perp \mathbf{v}_2}
R_M(\mathbf{x}),
$$

etc. The $\mathbf{x}$ vector that minimizes each of the above
expressions is the corresponding eigenvector.

## References

1. <a name="ref_01"></a> Luca Trevisan, *Lecture Notes on Graph Partitioning, Expanders and Spectral Methods*, University of California, Berkeley, 2016

