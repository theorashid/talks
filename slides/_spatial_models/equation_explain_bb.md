## Bayesian multilevel model

---
effect | index | dimension | description
------ | ------|---------- | -----------
age    | a     | 19        | age groups (0, 1-4, 5-9, ..., 80-84, 85+)
space  | s     | 6791      | number of MSOAs
time   | t     | 18        | years 2002-2019

---
$$
y_{ast} \sim \text{Beta Binomial} (m_{ast}, \theta, N_{ast})
$$

-v-
<!-- .slide: data-background="#343434" -->
$$
\text{logit} (m_{ast}) = \alpha_0 + \beta_0 t +
            \alpha_{1s} + \beta_{2s} t +
            \alpha_{2a} + \beta_{2a} t + 
            \xi_{as} + \nu_{st} + \gamma_{at}
$$
<!-- .element style="font-size: 90%"-->
<div class="r-stack">
    <img class="fragment fade-in-then-out" src="slides/_spatial_models/assets/MSOA_CAR.png">
    <img class="fragment fade-in-then-out" src="slides/_spatial_models/assets/age_shape.png">
</div>
