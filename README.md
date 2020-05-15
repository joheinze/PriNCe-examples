# PriNCe-examples

This repository contains examples for the use of the PriNCe propagation code.

Requires the base [PriNCe code](https://github.com/joheinze/PriNCe) and the [PriNCe analysis tools](https://github.com/joheinze/PriNCe-analysis-tools). The latter is optional, since it is only used for plotting measured spectra.

## How to use

1. Install the PriNCe code via `pip install prince-cr`
2. Install `jupyter notebook` or `jupyter lab`
3. Clone this repository `git clone git@github.com:joheinze/PriNCe-examples.git`
4. Launch `jupyter lab/notebook` and visit the notebooks in the folders

Some notes on performance:

The code has two performance demanding parts. The initialization from scratch will preprocess the data tables, perform cross section interpolation and averaging, etc. This part strongly depends on the maximal nuclear mass of the system and the total number of nuclear and particle species. Typicall this process takes ~2-3 minutes on a laptop and does not scale well across multiple cores. The result of the initialization, the "kernels", can be saved and restored to save this initialization time. This is demonstrated by the basic examples.

The second performance constrained part is the integration. This scales across multiple cores and profits from the presence of a GPU.  

## Authors

- *Anatoli Fedynitch*
- *Jonas Heinze*

## Copyright and license

Code released under [the BSD 3-clause license (see LICENSE)](LICENSE).
