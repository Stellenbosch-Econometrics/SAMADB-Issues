# South Africa Macroeconomic Database

<!-- badges -->
[![CRAN status](https://www.r-pkg.org/badges/version/samadb)](https://cran.r-project.org/package=samadb) 
[![cran checks](https://badges.cranchecks.info/worst/samadb.svg)](https://cran.r-project.org/web/checks/check_results_samadb.html)
![downloads per month](http://cranlogs.r-pkg.org/badges/samadb?color=blue)
![downloads](http://cranlogs.r-pkg.org/badges/grand-total/samadb?color=blue)
![pypi](https://img.shields.io/pypi/v/samadb.svg)
![versions](https://img.shields.io/pypi/pyversions/samadb.svg)
![PyPI - Downloads](https://img.shields.io/pypi/dm/samadb)
<!-- end badges -->

The South Africa Macroeconomic Database (SAMADB) is a relational database with >10,000 macroeconomic time series for South Africa, obtained from the South African Reserve Bank (SARB) and Statistics South Africa (STATSSA) and updated on a weekly basis via [EconData](<https://www.econdata.co.za/>) and automated scraping of the [SARB](<https://www.resbank.co.za/en/home/publications/quarterly-bulletin1/download-information-from-xlsx-data-files>) and [STATSSA](<https://www.statssa.gov.za/?page_id=1847>) websites. It is accessible through API packages for [R](https://CRAN.R-project.org/package=samadb), [Python](https://pypi.org/project/samadb/) and [Julia](https://juliahub.com/ui/Search?q=SAMaDB&type=packages). This repo was created to allow you to report issues with the database or any of the APIs. More information about SAMADB is available in the introductory [presentation](https://github.com/Stellenbosch-Econometrics/SA-Nowcast/blob/main/presentation/SAMADB_Nowcasting.pdf). Each API has its own built-in documentation. 

## SAMADB Installation and Usage

### R API

To install from CRAN, use
```r
install.packages("samadb")
```
Then attach the package with
```r
library(samadb)
help("samadb") # Open Documentation 
```

*Notes*: The R API offers the broadest functionality, including the possibility to transpose data and export data to Excel. In the wide format, variable labels are attached to the series as attributes, and can be received using `collapse::vlabels()` or, together with names, using `collapse::namlab()`. Functions return a [data.table](<https://rdatatable.gitlab.io/data.table/>).

***

### Python API

To install from pypi, open a terminal and execute
```
pip install samadb
```
Then import the package with

```python
import samadb as sm
help(sm) # Overview of Package Functions
```

*Notes*: The python package returns [polars](<https://www.pola.rs/>) DataFrame's. These can be converted to [pandas](<https://pandas.pydata.org/>) DataFrame's using the `.to_pandas()` method. The Python API is a bit different than the R API, due to the greater difficulty of dealing with variable labels in Python. It also presently has no options to transpose or export to Excel, which can however be achieved by converting to pandas and using the `.to_excel()` method. 

*** 
### Julia API

To install from the Julia package registry, use
```julia
using Pkg; Pkg.add("SAMaDB")
```
Then import the package with

```julia
import SAMaDB as sm
?sm # Overview of Package Functions
```

*Notes*: The Julia API returns [DataFrame's](<https://dataframes.juliadata.org/stable/>), and is pretty much identical to the Python API i.e. you should access functions using *qualified names* as in Python, e.g. `sm.datasets()`. No functions are exported. 
