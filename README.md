
[![Build
Status](https://travis-ci.org/eribul/coder.svg?branch=master)](https://travis-ci.org/eribul/coder)
[![AppVeyor Build
Status](https://ci.appveyor.com/api/projects/status/github/eribul/coder?branch=master&svg=true)](https://ci.appveyor.com/project/eribul/coder)
[![codecov](https://codecov.io/gh/eribul/coder/branch/master/graph/badge.svg)](https://codecov.io/gh/eribul/coder)

<!-- README.md is generated from README.Rmd. Please edit that file -->

# Note\!

This package is work in progress\! The repository is currently only used
for internal development\! More information will be available soon\!

# Installation

``` r
# install.packages("devtools")
devtools::install_github("eribul/coder")
```

# About the package

The coder package is used to classify items from one dataset, using code
data from a secondary source. It was first developed for medical
comorbidity data based on hospital visits recorded in a national patient
register. Medical conditions were registered using standardized codes
(ICD-10) and individual codes were summarized by weighting all
individual comorbidities for each patient (the Charlson and Elixhauser
comorbidity indices). Only hospital visits recorded within a specified
time frame, compared to individual reference dates from the primary data
source, were recognized as relevant.

The large data sets, as well as the complexity of the classification
schemes make those calculations time consuming. A naïve approach using
bare code comparisons and for-loops in R, took approximately 16 hours to
run on a laptop computer with 16 GB of RAM. We were then able to
reformulate the coding schemes using regular expressions and we
optimized our package using the data.table package. The classification
time were then reduced to a number of seconds. We also compared the
coder package to two packages on CRAN with similar scoop, icd and
comorbidities.icd10. Our package was considerably faster than those.

The package does not only include classification schemes for comorbidity
data. It incorporates a general framework for any case where items can
be classified using standardized codes. It might therefore be relevant
for many tasks involving data management in official statistics using
big data.
