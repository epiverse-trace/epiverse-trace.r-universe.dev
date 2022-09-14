# Epiverse-TRACE R-universe

[![Current status of Epiverse-TRACE R-universe](https://epiverse-trace.r-universe.dev/badges/:registry)](https://github.com/r-universe/epiverse-trace)
[![Total number of packages on Epiverse-TRACE R-universe](https://epiverse-trace.r-universe.dev/badges/:total)](https://epiverse-trace.r-universe.dev/)

### Note to @epiverse-trace team members

The file [`packages.json`](packages.json) contains a list of packages that will be automatically built and made available on https://epiverse-trace.r-universe.dev/, including binaries for the relevant platforms.

You can add any 'package-like' repository in [`packages.json`](packages.json) (e.g., R packages but also R research compendia, bookdown projects, etc.). As long as it can be built with `R CMD build`, it can be added here. Please refer to [the official documentation](https://r-universe.dev/help/) to learn how you can build from a specific branch, specific subfolder or any other non-standard case.

Thanks to R-universe, you can now provide your users with an easy way to install the development version of your packages or projects that are not hosted on CRAN. Instead of recommending `drat` or:

```r
remotes::install_github("epiverse-trace/yourproject")
```

you can now either instruct your users to run:

```r
install.packages(
  "yourproject", 
  repos = c("https://epiverse-trace.r-universe.dev", "https://cloud.r-project.org")
)
```

or to add the `epiverse-trace` universe to their `.Rprofile`:

```r
options(
  repos = c(
    "epiverse-trace" = "https://epiverse-trace.r-universe.dev",
    "CRAN" = "https://cloud.r-project.org"
  )
)
```

and after a restart, run the regular:

```r
install.packages("yourproject")
```

Please note that as opposed to `remotes` (or `devtools`), installs via R-universe will not automatically detect every new commit as a new version. To make a change available via `update.packages("yourproject")`, you need to increment the version number of your package.
