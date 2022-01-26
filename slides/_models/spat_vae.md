## Speeding-up spatial modelling

---
SpatVAE paper
Inference for big dimensions is slow. Spatial is highly correlated so poor MCMC mixing

---
<!-- .slide: data-background="#343434" -->
GP (or any spatial) priors

-v-
<!-- .slide: data-background="#343434" -->
Variational autoencoder

-v-
Variational autoencoder learning GP priors

-v-
<!-- .slide: data-background="#343434" -->
decoder only spits out GP priors when given random noise

-v-
<!-- .slide: data-background="#343434" -->
decoder only spits out GP posterior when optimised __z__

---
Only have to infer a vector – not a full spatial structure.

Speed-ups. Efficiency increase.
