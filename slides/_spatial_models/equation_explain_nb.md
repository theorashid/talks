## Bayesian multilevel model
<!-- .element style="text-transform: capitalize"-->
---
Effect | Index | Dimension | Description
------ | ------|---------- | -----------
age    | a     | 19        | age groups (0, 1-4, 5-9, ..., 80-84, 85+)
space  | s     | 4835      | number of LSOAs
time   | t     | 16        | years 2002-2017
---
`$$
\begin{aligned}
y_{ast} \sim \text{Negative Binomial} (p_{ast}, r) \\
p_{ast} = \frac{r}{r + m_{ast} \cdot P_{ast}} 
\end{aligned}
$$`
-v-
$$
\log (m_{ast}) = \alpha_0 + \beta_0 t +
            \alpha_{1s} + \beta_{2s} t +
            \alpha_{2a} + \beta_{2a} t +
            \xi_{as} + \gamma_{at}
$$

<div class="r-stack">
    <img class="fragment fade-in-then-out" src="slides/_spatial_models/assets/MSOA_CAR.png">
    <img class="fragment fade-in-then-out" src="slides/_spatial_models/assets/age_shape.png">
</div>