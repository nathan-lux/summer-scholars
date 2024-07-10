# Tuesday July 9
---
tl;dr - my main questions are if Legendre polynomial expansion makes sense given that we are in the small angle approximation and $$\mu \approx 1$$ and also if there is a sensible interpretation to invoking spherical harmonics (for example as a substitution of the Legendre polynomials) in the flat sky case or if there isn't a good notion of what it means to do that.

I've been working more on the flat sky approximation. I'll post some highlights of the calculation so you can see how it's going and then I'll ask a couple questions which might have pretty straightforward answers. In working on this bit, I've sort of walked down a couple paths which have all led to varying amounts of confusion.

**The calculation**

We start with two projected fields $\tilde{A}(\vec{x}_{\perp})=\int F_{A}(x_{\parallel})A(x_{\parallel},\vec{x}_{\perp})) \, dx_{\parallel}$ and a similar field named $\tilde{B}(\vec{x}_{\perp})$. We Fourier transform them in the "perp" plane via a 2D Fourier transform. After this we will have both fields in a handy form and can consider $$\langle \tilde{A}(\vec{l})\tilde{B}^{*}(\vec{l}') \rangle$$ (here $$\vec{l}$$ is the 2D Fourier conjugate to $$\vec{x}_{\perp}$$) as we know

$$
P_{\tilde{A}\tilde{B}}(\vec{l})=\frac{1}{(2\pi)^{2}}\int d^2l'\langle \tilde{A}(\vec{l})\tilde{B}^{*}(\vec{l}) \rangle  
$$

So we can substitute in the Fourier transform into the expectation value and then integrate over $l'$ which yields a delta function on $$x'_{\perp}$$ effectively forcing two integrals to vanish. After that we are left with

$$
P_{\tilde{A}\tilde{B}}(\vec{l})=\int d^{2}x_{\perp}e^{-i \vec{l}\cdot \vec{x}_{\perp}}\int \int dx_{\parallel}dx_{\parallel}'F_{A}(x_{\parallel})F_{B}(x_{\parallel}')\int \frac{d^3k}{(2\pi)^{3}}P_{AB}(k,\hat{k}\cdot \hat{z})e^{i \vec{k}\cdot(\vec{x}-\vec{x}')} 
$$

$$\vec{x}$$ here is the full 3D vector (ie something like $$\langle x_{\parallel},x_{\perp_{1}},x_{\perp_{2}} \rangle$$) and $$\vec{k}$$ is the 3D Fourier conjugate to this vector $\vec{x}$. From here I am sort of split.

**Path One**

On one hand, if I take this and run with it then the next step would be to use the $$\vec{x}_{\perp}$$ integral to create some delta functions which result in $$P_{AB}(k)\to P_{AB}\left( \sqrt{ k_{3}^{2}+\frac{l^{2}}{x_{\parallel}^{2}} } \right)$$ which isn't even accounting for what happens to $$\hat{k}\cdot \hat{z}$$. Further, it seems that the delta functions modify the dot product in a way that sort of obscures its actual meaning as it seems like it isn't exactly $$\cos(\theta)$$ anymore given it is in terms of $$l,k$$, and $$z$$. Running with this path and attempting to expand using a Legendre series expansion gets confusing and it isn't clear to me that the angular dependence is actually being separated out this way.

**Path Two**

The other path I poked was to investigate what happens if I just leave that last integral alone and substitute the power spectrum for its Legendre series expansion. This also led me down a somewhat confused path, though. Immediately one can write that 

$$
P_{AB}(k,\mu)=\sum_{\ell}\mathcal{L}_{\ell}(\mu)P_{AB,\ell}=\sum_{\ell}\mathcal{L}_{\ell}(\mu)\frac{2\ell+1}{2}\int d\mu \;\mathcal{L}_{\ell}(\mu)P_{AB}(k,\mu) 
$$

Where $$\mu=\cos(\theta)=\hat{k}\cdot \hat{z}$$.  My confusion is that if $$\theta$$ is supposed to be the angle between the LOS vector and $$\vec{k}$$ which should be along $$\vec{x}$$ then shouldn't the small angle approximation apply here and we can just say $$\mu \approx 1$$? At which point a lot of the Legendre polynomial expansion stuff seems to lose some meaning for me. Particularly when it comes to trying to simplify the coefficients because the whole setup for the integral is based on $$\mu$$.

**Path Three**

Ignoring option 2 and just trying to substitute the Legendre series expansion back into the original expression, I don't see many options that don't involve using spherical harmonics which I think I was under the assumption we wanted to avoid as we are trying to do the flat sky case so I'm not sure how much sense it makes to invoke the spherical harmonics.

In general I've definitely hit a few bumps on a few different paths but I'll continue to explore them. Apart from this I've been doing some reading on the references you mentioned relating to snapshot geometry and trying to beat the heat as much as humanly possible. Apologies is this is a bit long winded, I think I find it a bit tricky to ask questions in this format without being a little overly verbose.
