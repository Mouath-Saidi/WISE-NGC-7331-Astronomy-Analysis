# WISE and NGC 7331 Astronomy Analysis

An interactive Python analysis combining the **WISE** infrared source catalogue with **THINGS 21-cm HI observations** of NGC 7331. The project explores galaxy luminosity, infrared colours, gas distribution, rotation, and velocity dispersion.

## Project highlights

- Converted WISE W1-W4 absolute magnitudes into luminosities using the Pogson magnitude relation.
- Examined magnitude-luminosity, flux-distance, and inverse-square flux relationships.
- Identified infrared colour trends associated with stellar, dusty, star-forming, and AGN-dominated emission.
- Visualized neutral hydrogen maps for NGC 7331 using Moment 0, Moment 1, and Moment 2 FITS data.
- Applied World Coordinate System projections and NaN-safe plotting.

## Main analysis

- [Astronomy showcase notebook](notebooks/astronomy_analysis.ipynb)
- [WISE catalogue](data/WISE_set1.csv)
- [NGC 7331 HI FITS maps](FITS/)
- [Exported PDF maps](results/)

## Scientific workflow

### WISE infrared analysis

The catalogue contains source identifiers, sky coordinates, W1-W4 magnitudes, and luminosity distances. Absolute magnitudes are converted to band luminosities using:

$$
L = L_\odot \, 10^{(M_\odot-M)/2.5}
$$

The analysis then calculates monochromatic flux, compares luminosity and distance relationships, and examines WISE colour-colour diagnostics.

### NGC 7331 neutral hydrogen analysis

The FITS moment maps provide complementary views of the galaxy:

| Moment | Scientific quantity |
|---|---|
| 0 | Integrated HI intensity; traces the neutral-gas distribution |
| 1 | Intensity-weighted radial velocity; traces rotation |
| 2 | Velocity dispersion; traces broadened internal gas motions |

## Repository structure

```text
.
|-- notebooks/
|   `-- astronomy_analysis.ipynb
|-- data/
|   `-- WISE_set1.csv
|-- FITS/
|   |-- NGC_7331_NA_MOM0_THINGS.FITS
|   |-- NGC_7331_NA_MOM1_THINGS.FITS
|   `-- NGC_7331_NA_MOM2_THINGS.FITS
|-- results/
|   |-- mom1_map.pdf
|   `-- mom2_map.pdf
|-- README.md
`-- requirements.txt
```

## Reproducing the analysis

```bash
python -m pip install -r requirements.txt
jupyter notebook notebooks/astronomy_analysis.ipynb
```

## Dependencies

- Python 3
- NumPy
- Pandas
- Matplotlib
- Astropy
- Jupyter Notebook
