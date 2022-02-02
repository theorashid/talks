<div class="r-stack">
    <img class="fragment fade-out" data-fragment-index="0" src="slides/_mortality/assets/minton_city.png">
    <img class="fragment current-visible" data-fragment-index="0" src="slides/_mortality/assets/grenfell.jpg">
</div>

---
<!-- .slide: style="text-align: left"-->
Model life expectancy for __small areas__ over time in England.

Get the true underlying death rate for the data. This is a __regression__ problem.

---
<!-- .slide: data-background="#343434" -->
<div class="r-stack">
  <img class="fragment fade-out" data-fragment-index="0" src="slides/_mortality/assets/MSOA_ldn1.png">
  <img class="fragment current-visible" data-fragment-index="0" src="slides/_mortality/assets/MSOA_ldn2.png">
</div>

Middle layer Super Output Area (MSOA)

---
sex    | region        | district   | MSOA      | year | age group | deaths | population
------ | ------------- | ---------- | --------- | ---- | --------- | ------ | ----------
female | East Midlands | Leicester  | E02002843 | 2015 | 20-24     | 2      | 138
male   | North West    | Pendle     | E02005252 | 2008 | 50-54     | 5      | 221
female | South West    | Tewkesbury | E02004672 | 2010 | 65-69     | 3      | 175
...    |               |            |           |      |           |        |
<!-- .element style="font-size: 70%"-->
