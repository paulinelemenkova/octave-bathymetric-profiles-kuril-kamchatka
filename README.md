# GNU Octave Bathymetric Profiles — Kuril-Kamchatka Trench

A GNU Octave script that plots stacked cross-section (bathymetric) profiles of a
deep-sea trench from a table of depths sampled along a transect. The figure
overlays ten across-trench profiles of the Kuril-Kamchatka Trench, showing how
the sea-floor depth varies along a 400-km cross-section line, and is used to
compare the geomorphic shape of the trench at successive positions.

## Related publication

This script (octave_bathymetric_profiles_kuril_kamchatka.m) produced the Octave
figure in:

Lemenkova, P. AWK and GNU Octave Programming Languages Integrated with Generic
Mapping Tools for Geomorphological Analysis. GeoScience Engineering 2019, 65(4),
1-22.

- DOI:      https://doi.org/10.35180/gse-2019-0020
- figshare: https://doi.org/10.6084/m9.figshare.11374542
- HAL:      https://hal.science/hal-02425687
- Zenodo:   https://zenodo.org/record/3579575
- SSRN:     https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3505007
- ISSN:     1802-5420

The article integrates three tools - AWK (text/table preprocessing), GNU Octave
(numerical plotting) and GMT (Generic Mapping Tools, cartography). This
repository holds the GNU Octave plotting component.

## Script

### octave_bathymetric_profiles_kuril_kamchatka.m
- Reads a numeric matrix of depths from a CSV with dlmread; column 1 is the
  along-track distance (km) of the 400-km cross-section line and columns 2-11 are
  the depths (m) of ten individual profiles.
- Assigns each column to a depth vector and inspects the workspace (whos).
- Draws a two-panel figure (subplot 2x1): the first panel overlays five profiles
  and the second the remaining five, each profile drawn with a distinct marker
  style, minor grid, fixed axis limits (x in [-200, 200] km, y in [-9000, 200] m)
  and custom ticks.
- Annotates the panels (annotation textarrow / textbox) to mark the trench and
  the Greater Kuril Chain / Kuril Islands, with outside legends.
- Exports the figure to a 300-dpi, best-fit PDF with print (-dpdf -r300 -bestfit).

## Methods and techniques

- Delimited numeric input parsing (dlmread) into a data matrix.
- Multi-series line/marker plotting on a shared cross-section axis.
- Multi-panel figure layout (subplot) with fixed geographic-style axis scaling
  for vertical exaggeration control.
- Publication export to vector PDF at fixed resolution.

## Data

- table_10FINAL.csv: depths (m) for ten across-trench profiles of the
  Kuril-Kamchatka Trench, sampled at equal steps along a 400-km cross-section
  line (first column = distance, remaining columns = per-profile depths).

## Requirements

- GNU Octave (>= 5), or MATLAB (the script uses MATLAB-compatible syntax)
- See Octave_install_packages.m for the package setup used by the author.

## Usage

Place table_10FINAL.csv in the working directory and run in Octave:

    octave octave_bathymetric_profiles_kuril_kamchatka.m

It draws the two-panel profile figure and writes plot_KKTprofiles.pdf.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

If you use this script, please cite:

Lemenkova, P. AWK and GNU Octave Programming Languages Integrated with Generic
Mapping Tools for Geomorphological Analysis. GeoScience Engineering 2019, 65(4),
1-22. https://doi.org/10.35180/gse-2019-0020

## License

See the LICENSE file in this repository.
