![](slides/_spatial_models/assets/mortality_model_fit.png)

---
<!-- .slide: data-background="#343434" -->
#### (simplified) model in [NumPyro](num.pyro.ai)
```
def model(space, age, time, population, deaths=None):
    N_s = len(np.unique(space))
    N_age = len(np.unique(age))
    N_t = len(np.unique(time))
    N = len(population)
    
    age_plate = numpyro.plate("age_groups", N_age, dim=-3)
    space_plate = numpyro.plate("space", N_s, dim=-2)
    year_plate = numpyro.plate("year", N_t, dim=-1)

    # hyperparameters
    alpha0 = numpyro.sample("alpha0", dist.Normal(0., 10.))
    sigma_space = numpyro.sample("sigma_space", dist.Uniform(0., 2.))
    sigma_age = numpyro.sample("sigma_age", dist.Uniform(0., 2.))
    sigma_rw = numpyro.sample("sigma_rw", dist.Uniform(0., 2.))
    theta = numpyro.sample("theta", dist.Exponential(.1))

    with space_plate:
        alpha_s = numpyro.sample("alpha_s", dist.Normal(0., sigma_space))

    with age_plate:
        alpha_age_drift = numpyro.sample("alpha_age_drift", dist.Normal(0.,  alpha_age))
        alpha_age = jnp.cumsum(alpha_age_drift, -3)
    
    with year_plate:
        rw_drift = numpyro.sample("rw_drift", dist.Normal(0., sigma_rw))
        rw = jnp.cumsum(rw_drift, -1)
    
    # likelihood
    latent_rate = alpha0 + alpha_s + alpha_age + rw
    with numpyro.plate("N", N):
        mu_logit = latent_rate[space, age, time]
        mu = numpyro.deterministic("mu", expit(mu_logit))
        numpyro.sample(
            "deaths",
            dist.BetaBinomial(mu * theta, (1 - mu) * theta, population),
            obs=deaths
        )
```
<!-- .element style="width: 110%"-->

-v-
<!-- .slide: data-background="#343434" -->
#### Fitting the model
```
nuts_kernel = NUTS(model)
mcmc = MCMC(nuts_kernel, num_samples=10000, num_warmup=1000, num_chains=4)
mcmc.run(rng_key, *data)
```
<!-- .element style="width: 110%"-->
