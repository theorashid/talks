## Speeding-up spatial modelling

---
<!-- .slide: style="text-align: left"-->
Inference for high dimensional problems is __slow__.

Spatial posterior sites are highly correlated so MCMC __mixing is poor__.

<img class="fragment current-visible" src="slides/_spatial_models/assets/spatVAE_paper.png">

[arxiv.org/abs/2110.10422](https://arxiv.org/abs/2110.10422)<!-- .element style="font-size: 80%"-->

-v-
#### Variational autoencoder (VAE)
![](slides/_spatial_models/assets/VAE.png)

-v-
VAE trained to __encode__ GP (or other spatiotemporal) priors
<!-- .element style="text-align: left"-->

![](slides/_spatial_models/assets/GPVAE_prior_training.png)

-v-
Decoder __recreates__ GP prior when $\mathbf{z} \sim \mathcal{N}(0, 1)$
<!-- .element style="text-align: left"-->

![](slides/_spatial_models/assets/GPVAE_prior_decode.png)

-v-
Decoder recreates GP __posterior__ when we __infer__ $\mathbf{z}$ from the data
<!-- .element style="text-align: left"-->

![](slides/_spatial_models/assets/GPVAE_posterior.png)

---
<!-- .slide: style="text-align: left"-->
With the trained decoder in the model, we only have to infer the vector $\mathbf{z}$ – not a complex spatial structure.

__Faster__ inference.

Sampling __efficiency__ increases.
