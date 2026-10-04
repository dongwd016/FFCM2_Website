# FFCM-2 website

Source of the website for the Foundational Fuel Chemistry Model Version 2.0 (FFCM-2), hosted by Prof. Hai Wang's group at <https://web.stanford.edu/group/haiwanglab/FFCM2/>. GitHub Pages builds the latest version of this repository at <https://dongwd016.github.io/FFCM2_Website/>.

FFCM-2 is a reaction model for the combustion of H<sub>2</sub>, CO, CH<sub>2</sub>O, and C<sub>1</sub>-C<sub>4</sub> hydrocarbons (96 species, 1054 reactions). It is based on elementary reaction kinetics and is optimized against 1192 sets of fundamental combustion data (laminar flame speeds, shock-tube ignition delay times, and speciation data from shock tubes and flow reactors), using neural-network response surfaces for uncertainty minimization. The FFCM project is a collaboration between Prof. Hai Wang's group at Stanford University and Dr. Gregory P. Smith of SRI International.

The site documents the trial model, the experimental data and their uncertainty evaluation, the response surfaces, the optimization and uncertainty minimization, the results and validation, model files for download, and applications to real fuels (Jet A, JP-5, JP-10, RP-2, Gevo ATJ, n-dodecane).

## Related publications

- Y. Zhang, W. Dong, A. Nobili, R. F. Johnson, H. Wang, Foundational Fuel Chemistry Model 2 - Can data assimilation yield useful insights in reaction rate constants? *Combustion and Flame* 294 (2026) 115284.
- W. Dong, A. Nobili, H. Wang, Adaptive learning of data assimilated combustion reaction model, *Proceedings of the Combustion Institute* 42 (2026) 106249.
- W. Dong, Y. Zhang, G. P. Smith, H. Wang, Aspects of fundamental reaction kinetics and legacy combustion properties in data-assimilated combustion reaction model development, *Proceedings of the Combustion Institute* 40 (2024) 105410.
- Y. Zhang, W. Dong, L. A. Vandewalle, R. Xu, G. P. Smith, H. Wang, Neural network approach to response surface development for reaction model optimization and uncertainty minimization, *Combustion and Flame* 251 (2023) 112679.

To cite the model itself, see "How to cite" on the website.

## Building the site

The site is built with [Jekyll](https://jekyllrb.com/) and the [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme. Pages are in `docs/`, images and model files in `assets/`, and the site settings in `_config.yml`. The workflow in `.github/workflows/pages.yml` builds and deploys the site on every push to `main`.

To preview locally (Ruby and Bundler required):

```bash
bundle install
bundle exec jekyll serve
# then open http://localhost:4000/FFCM2_Website/
```

Website built and maintained by Wendi Dong. The Just the Docs theme is MIT-licensed (see `LICENSE` and `LICENSE.txt`).
