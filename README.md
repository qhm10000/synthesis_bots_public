# Main workflow code for Synthesis Bots (A.I.C. Group)

## Requirements and installation

### System requirements and dependencies

This code has been used and tested on Windows 10 (UPLC-MS and NMR control PCs) and Windows 11 (development). The package makes use of the following dependencies and was tested with the following versions:

- `dtw-python` (v1.3.1, [ref](https://www.jstatsoft.org/article/view/v031i07))
- `matplotlib` (v3.8.2, [ref](https://doi.org/10.1109/MCSE.2007.55))
- `numpy` (v1.26.3, [ref](https://www.nature.com/articles/s41586-020-2649-2))
- `pandas` (v2.2.0, [ref](https://doi.org/10.5281/zenodo.3509134))
- `pyserial` (v3.5, [ref](https://github.com/pyserial/pyserial/))
- `scipy` (v1.12, [ref](https://doi.org/10.1038/s41592-019-0686-2))
- `pyzmq` (v25.1.2, [ref](https://github.com/zeromq/pyzmq))

which can all be obtained directly from the Python Package Index (PyPI) with `pip` package installer.

### LC-MS System

LC-MS parser requires DLL driver files from Waters, packaged as `masslynx`: [masslynx_sdk](https://github.com/cooper-group-uol-robotics/masslynx_sdk_public) (see on [Zenodo](https://zenodo.org/doi/10.5281/zenodo.11174322)).

### NMR System

The NMR driver requires official Bruker TopSpin 4.3.0 Python API. Assuming the default TopSpin installation folder, you can use:

```
conda create -n synthesis-bots-nmr python=3.12
conda activate synthesis-bots-nmr
python -I -m pip install --find-links 'C:\Bruker\TopSpin4.3.0\python\examples' .[nmr]
```

on a different system you need to replace `'C:\Bruker\TopSpin4.3.0\python\examples'` with a path to wherever the official Bruker TopSpin API can be found.

### Installation

Easiest and recommended approach is to dedicate an isolated conda environment for the package:

```
conda create -n synthesis_bots python>=3.12
conda activate synthesis_bots
```

then - provided all the non-pip dependencies for NMR and UPLC-MS are present, the package can easily be installed with:

```
python -m pip install .
```

On a typical desktop computer with fast internet connection, the installation should take a couple of minutes (depending on how many dependencies have already been satisfied).

## Examples

Examples with minimum input files and expected output can be found on [Zenodo](https://doi.org/10.5281/zenodo.11197260) and include all reproduction instructions:

- Medicinal Chemistry example data and analysis
- Supramolecular Chemistry example data and analysis
- Photocatalysis example data and analysis
- Workflow instrument integration example

The run time for the code examples on a typical desktop computers is minutes.

## References

The exact mass calculator file (to be replaced in the future versions) is taken directly from [pyISOPACh](https://github.com/AberystwythSystemsBiology/pyISOPACh), which has been published under the MIT License.