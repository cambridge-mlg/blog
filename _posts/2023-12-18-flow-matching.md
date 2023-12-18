---
layout:      post
title:       "Flow Matching"
tags:        [diffusion model, normalising flows, generative modelling]
authors:
    - name: Emile Mathieu
      link: www.emilemathieu.fr
    - name: Tor Fjelde
      link: https://retiredparkingguard.com/about.html
    - name: Vincent Dutordoir
      link: https://vdutor.github.io/
comments:    true
image:      /assets/images/flow-matching/flow-matching.png
excerpt: |
    Flow matching (FM) is a new generative modelling paradigm which is rapidly gaining popularity in the deep learning community. Flow matching combines aspects from Continuous Normalising Flows (CNFs) and Diffusion Models (DMs), alleviating key issues both methods have. In this blogpost we’ll cover the main ideas and unique properties of FM models starting from the basics.

---

Flow matching (FM) is a new generative modelling paradigm which is rapidly gaining popularity in the deep learning community. Flow matching combines aspects from Continuous Normalising Flows (CNFs) and Diffusion Models (DMs), alleviating key issues both methods have. In this blogpost we’ll cover the main ideas and unique properties of FM models starting from the basics.
$$
\require{physics}
\require{color}
\newcommand{\hlorange}[1]{\colorbox{orange}{$\displaystyle#1$}}
\newcommand{\hlblue}[1]{\colorbox{blue}{$\displaystyle#1$}}
$$

## Generative modelling

Let's assume we have data samples $x_1, x_2, \ldots, x_n$ from a distribution of interest $q_1(x)$, which density is unknown. We're interested in using these samples to approximate $q_1$ in some sense.  In particular, we want our approximation to allow generation of new samples (approximately) from $q_1$ in an efficient manner. This task is generally referred to as **generative modelling**.

The advancement in generative modelling methods over the past decade has been nothing short of revolutionary. In 2012, Restricted Boltzmann Machines, then the leading generative model, were [just about able to generate MNIST digits](https://physics.bu.edu/~pankajm/ML-Notebooks/HTML/NB17_CXVI_RBM_mnist.html). Today, state-of-the-art methods are capable of generating high-quality [images](https://openai.com/dall-e-3), [audio](https://deepmind.google/discover/blog/transforming-the-future-of-music-creation/) and [language](https://arxiv.org/pdf/2305.14671.pdf), as well as model complex [biological](https://www.nature.com/articles/s41586-023-06415-8) and [physical](https://deepmind.google/discover/blog/nowcasting-the-next-hour-of-rain/) systems. Unsurprisingly, these methods are now venturing into [video generation](https://imagen.research.google/video/).

Adding a figure:
{% include image.html
  name="Figure 1"
  ref="Figure1"
  alt="Caption 1"
  src="flow-matching/marginals.png"
  width=700
%}

We can refer to Figure 1 as [Figure 1](#figure-Figure1).

\begin{equation}
\label{eq:a}
   \hlblue{\phi(x) = \int \frac{1}{\sqrt{2\pi}} \exp(-\frac{1}{2}x^2) \dd{x}}
\end{equation}

We see in \eqref{eq:a} that $a = b$.

\begin{align}
   a &= \hlorange{ \pdv{\phi}{x}} \label{eq:b} \newline
    a &= \hlorange{b} \label{eq:c}
\end{align}

We see in \eqref{eq:b} that $a = b$ and in \eqref{eq:c} that $a = b$.


Some footnotes[^footnote-test].



### References


[^footnote-test]: A footnote.
