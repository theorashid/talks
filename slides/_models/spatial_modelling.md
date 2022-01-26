## Spatial modelling

---
<!-- .slide: data-background="#343434" -->
#### Nested hierarchy
$$
S_{s} \sim \mathcal{N} (S_{d(s)}, \sigma_s)
$$
<img class="fragment fade-in-then-out" src="slides/_parametric_models/assets/LSOA_westminster_nested.png">

-v-
<!-- .slide: data-background="#343434" -->
#### Structured spatial model
$$
S_{s} \sim \text{CAR} (0, \sigma_s^2) + \mathcal{N} (0, \sigma_u^2) 
$$
<img class="fragment fade-in-then-out" src="slides/_parametric_models/assets/LSOA_westminster_BYM.png">

-v-
<!-- .slide: data-background="#343434" -->
#### Gaussian Process
$$
S_{s} \sim \text{GP} ((m(\cdot), k(\cdot, \cdot))
$$
<img class="fragment fade-in-then-out" src="slides/_parametric_models/assets/LSOA_westminster_BYM.png">
