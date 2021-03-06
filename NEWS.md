# nasapower 1.0.6

## Minor changes

- Adds support for WS2M_MIN, WS2M_MAX and WS2M_RANGE in AG community

## Bug fixes
  
- Fixes bug where previous release did not support WS2M from AG community due to
a local typo

# nasapower 1.0.5

## Minor changes

- "Fixes" [Issue 32](https://github.com/ropensci/nasapower/issues/32) where WS2M
is not available through `nasapower` until the POWER team can properly address
how pre-query validation should be performed

# nasapower 1.0.4

## Minor changes

- Corrects an instance where vignette example executed on CRAN but should not

- Adds link to POWER website in error message when query fails

- Documentation .Rd files are now more readable with better formatting

# nasapower 1.0.3

## Minor changes

- Adds citation information for JOSS paper, http://joss.theoj.org/papers/10.21105/joss.01035

## Documentation changes

- Flesh out examples using `naspower` data with `raster` to create spatial objects for systems with low-RAM where the functionality may not work as expected

- Standardise formatting of vignette subheadings

- Spell check vignette

## Bug fixes

- Fixes tests to not run on CRAN so that errors aren't reported when API is unavailable

# nasapower 1.0.2

## Minor changes

- Updates documentation examples

- Provides nicer method of printing data in R console

- Updates tests for better coverage and removes non-functional tests

- Removes `dplyr` as an Import

## Bug fixes

- Corrects issue where `if()` was called with a vector of length 2 or more

- Corrects logical operators `&&` and `||` where they should be `&` or `|`

- Removes extra code in `create_icasa()` and `create_met()` that performed
a duplicated check of `latlon` values

- Removes unnecessary checks for `latlon` in `get_power()`

--------------------------------------------------------------------------------

# nasapower 1.0.1

## Minor changes

- Provides corrections to documentation formatting as per CRAN volunteers'
requests

- Provides edits and clarifications in DESCRIPTION's Description and Title about
the package's uses and capabilities

--------------------------------------------------------------------------------

# nasapower 1.0.0 (unreleased)

## Major changes

- _nasapower_ is now a part of [rOpenSci](https://ropensci.org/) after 
[peer-review of the code](https://github.com/ropensci/onboarding/issues/155)!

- Provides access to all three communities, AG, SSE and and SB, not just AG

- Uses new 'POWER' 'API' to download new 1/2 x 1/2 degree data

- Adds function `get_power()` to get weather data and optionally metadata as
well

- Adds function `create_met()` to create 'APSIM' met objects from 'POWER' data

- Adsd function `create_icasa()` to create a text file of weather data for use
in 'DSSAT' crop modelling

- Internally, replaces _httr_ package with _crul_

### Deprecated functions

- The `get_cell` and `get_region` functions are deprecated in favour of
`get_power()`. The new POWER interface allows for the specification of single
points or regional areas. Global coverage may be queryed for Climatology. See
the help for `?get_power()` for more details.

--------------------------------------------------------------------------------

# nasapower 0.1.4

### Bug Fixes

- Fixes bug related to date columns where `MONTH`, `DAY` and `YYYY-MM-DD` were
incorrectly reported in final data frame. This did not affect the weather data,
`YEAR` or `DOY` columns.

--------------------------------------------------------------------------------

# nasapower 0.1.3

### Bug fixes

- Fix bug where lon/lat values were improperly assigned internally due to row
names not being ordered correctly in `get_region()`

- Fix bug reports link in DESCRIPTION file

- Correct vignette where it had said, "both of which will which will download"

- Correct documentation for `get_region()`, which incorrectly stated that it
downloaded data for a 1 x 1 degree cell

### Minor improvements

- Optimise arguments used in `utils::read.table()` to ingest weather data in the
`get_cell()` and `get_region()` functions more quickly

- NEWS now formatted more nicely for easier reading

- Add statement about possible performance and memory usage when using
`get_region()` in the vignette

- Add an example of converting the data frame to a spatial object using
_raster_ to create a `raster::brick()`

- Specify in documentation that a range of days to years can be specified for
download

## Minor changes

- `get_region()` and `get_cell()` now default to download all weather vars

- Add a check to see if POWER website is responding before making request for
data. If not, stop and return error message to user.

--------------------------------------------------------------------------------

# nasapower 0.1.2

### Bug fixes

- Fixes bug where only first date is reported when using `get_region()` with
multiple dates. https://github.com/ropensci/nasapower/issues/1

### Minor improvements

- Enhanced documentation

- Superfluous function, `.onLoad()`, removed from zzz.R

- Tidied up startup message

- Clean up vignette

- Build vignette faster

- Remove DATE from DESCRIPTION

--------------------------------------------------------------------------------

# nasapower 0.1.1

### Minor improvements

- Fix issues in documentation, typos, incorrect links, etc.

--------------------------------------------------------------------------------

# nasapower 0.1.0

### New features

* Add new functionality to download regions in addition to single cells

* Add static documentation website, <https://ropensci.github.io/nasapower/>

* Add startup message

### Minor improvements

* Better documentation

--------------------------------------------------------------------------------

# nasapower 0.0.2

### New features

* Added citation file

--------------------------------------------------------------------------------

# nasapower 0.0.1

* Added a `NEWS.md` file to track changes to the package.

* First release, no changes to report yet
